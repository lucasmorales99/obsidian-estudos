#db  #integridadeEDesenpenho 

### Aula 1: O que são Índices?

Pense num **índice** de banco de dados exatamente como o índice remissivo no final de um livro didático pesado.

Se eu pedir para você encontrar a palavra _"Transação"_ em um livro de 1.000 páginas sem índice, você terá que ler página por página, da primeira à última. No banco de dados, chamamos isso de **Full Table Scan** (Varredura Completa da Tabela). É extremamente lento.

Com o índice, você vai direto à letra "T", descobre que "Transação" está na página 412 e abre direto lá. Isso é uma **busca indexada**.

#### Principais Tipos de Estruturas de Índices:

1. **Árvores B / B-Tree (B+Tree):**
    
    - **Como funciona:** É o tipo padrão da maioria dos bancos (Oracle, PostgreSQL, MySQL). Ela organiza os dados em uma estrutura de árvore equilibrada.
        
    - **Para que serve:** Excelente para buscas exatas (`=`) e buscas por intervalo (`BETWEEN`, `>`, `<`).
        
    - _Exemplo:_ Buscar funcionários com salário entre R$ 5.000 e R$ 10.000.
        
2. **Bitmap (Matriz de Bits):**
    
    - **Como funciona:** Associa bits (`0` ou `1`) para indicar a presença de um valor.
        
    - **Para que serve:** Ideal para colunas com **baixa cardinalidade** (poucos valores distintos, como `Sexo`, `Estado Civil` ou `Status_Ativo`). Muito utilizado em Data Warehouses (OLAP).
        
    - _Exemplo:_ Filtrar clientes por `Sexo = 'F'` E `Estado_Civil = 'Solteiro'`.
        
3. **Hash Index:**
    
    - **Como funciona:** Usa uma função matemática para mapear a chave direto para o endereço físico do dado.
        
    - **Para que serve:** Busca ultra-rápida de igualdade exata (`=`). **Não funciona** para buscas por intervalo (`>`).
        

### Aula 2: O Custo Oculto dos Índices (Aviso do Professor)

Índice não é "mágica gratuita". Cada índice criado exige espaço em disco e **custa processamento nas operações de escrita**.

- **No `SELECT` (DQL):** O índice **acelera** a leitura.
    
- **No `INSERT`, `UPDATE`, `DELETE` (DML):** O índice **desacelera** a escrita. Toda vez que você insere uma linha na tabela, o banco precisa atualizar a tabela E a estrutura de todos os índices atrelados a ela.
    

> **Regra de Ouro:** Não crie índices em todas as colunas! Crie apenas nas colunas frequentemente utilizadas em cláusulas `WHERE`, `JOIN` (Chaves Estrangeiras) e `ORDER BY`.

### Aula 3: Otimização de Consultas (Query Optimization)

Quando você envia um comando SQL, o banco não o executa cegamente. O **Otimizador de Consultas** (com base em estatísticas da tabela) analisa dezenas de caminhos possíveis e escolhe o **Plano de Execução** mais barato em termos de I/O (leitura de disco) e CPU.

#### Exemplo Prático de Otimização

Imagine a seguinte consulta em um banco de dados de um E-commerce:

SQL

```
-- CONSULTA LENTA (SMELL CODE)
SELECT id_pedido, data_pedido 
FROM Pedido 
WHERE YEAR(data_pedido) = 2026;
```

**Por que essa consulta é LENTA (mesmo se houver índice em `data_pedido`)?**

Quando você aplica uma função (`YEAR()`) sobre uma coluna indexada, o banco perde a capacidade de usar a busca por árvore do índice. Ele é obrigado a varrer a tabela inteira chamando a função para cada linha (**Full Table Scan**).

**Como Otimizar (Escrevendo de forma sargable):**

SQL

```
-- CONSULTA OTIMIZADA
SELECT id_pedido, data_pedido 
FROM Pedido 
WHERE data_pedido >= '2026-01-01' AND data_pedido <= '2026-12-31';
```

_Resultado:_ Agora o otimizador consegue fazer um **Index Range Scan** (busca direta por intervalo no índice), executando em milissegundos.

### Resumo para Provas e Prática Profissional

- **Full Table Scan (Leitura Total):** O banco lê o disco inteiro. Péssimo em tabelas grandes.
    
- **Index Scan / Seek (Busca por Índice):** O banco acessa a estrutura do índice e vai direto ao bloco de dados no disco.
    
- **Índices Compostos:** Criados sobre duas ou mais colunas (ex: `WHERE estado = 'SP' AND cidade = 'Campinas'`). Lembre-se: a ordem das colunas no índice importa!
    
- **EXPLAIN / EXPLAIN PLAN:** O comando que você usa no SQL para visualizar o Plano de Execução do banco e ver se o seu índice está realmente sendo utilizado.
- 