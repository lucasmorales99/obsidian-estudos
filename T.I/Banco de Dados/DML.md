#db #dml

A **DML (Data Manipulation Language)** é a sublinguagem do SQL utilizada para interagir diretamente com os **dados** contidos dentro das tabelas, permitindo inserir, consultar, atualizar e excluir registros.

# Guia de Estudo: DML (Data Manipulation Language)

Enquanto a DDL lida com a estrutura das tabelas, a DML lida com o **conteúdo** armazenado no banco de dados. As operações DML são controladas por transações (podem ser confirmadas com `COMMIT` ou desfeitas com `ROLLBACK`).

## 1. Principais Comandos DML

### A. `INSERT`

Insere novos registros em uma tabela existente.

- **Inserção Específica:**
    

SQL

```
INSERT INTO Funcionario (id_func, nome, salario, id_depto)
VALUES (1, 'Maria Silva', 5500.00, 10);
```

- **Inserção Múltipla:**
    

SQL

```
INSERT INTO Funcionario (id_func, nome, salario, id_depto)
VALUES 
    (2, 'João Souza', 4200.00, 10),
    (3, 'Ana Lima', 6100.00, 20);
```

- **Inserção via Consulta (`INSERT INTO ... SELECT`):**
    

SQL

```
INSERT INTO Funcionario_Bkp (id_func, nome)
SELECT id_func, nome FROM Funcionario WHERE id_depto = 10;
```

### B. `UPDATE`

Altera valores de registros já existentes na tabela.

> **Regra de Ouro:** Sempre utilize a cláusula `WHERE` para evitar atualizar **todos** os registros da tabela acidentalmente.

- **Exemplo:**
    

SQL

```
UPDATE Funcionario
SET salario = salario * 1.10, id_depto = 20
WHERE id_func = 1;
```

### C. `DELETE`

Remove registros específicos ou todos os registros de uma tabela.

- **Exemplo com Condição:**
    

SQL

```
DELETE FROM Funcionario
WHERE id_func = 3;
```

- **Diferença fundamental entre `DELETE` e `TRUNCATE`:**
    
    - **`DELETE` (DML):** Remove linha por linha, pode ser desfeito via `ROLLBACK`, aciona _triggers_ e permite filtrar com a cláusula `WHERE`.
        
    - **`TRUNCATE` (DDL):** Esvazia a tabela por completo desalocando memória, é extremamente rápido e não aceita a cláusula `WHERE`.
        

### D. `MERGE` (ou `UPSERT`)

Usado para realizar atualizações ou inserções em uma única operação condicional (insere se o registro não existir; atualiza se já existir).

SQL

```
MERGE INTO Funcionario f
USING Novos_Funcionarios n
ON (f.id_func = n.id_func)
WHEN MATCHED THEN
    UPDATE SET f.salario = n.salario
WHEN NOT MATCHED THEN
    INSERT (id_func, nome, salario) 
    VALUES (n.id_func, n.nome, n.salario);
```

## 2. DQL: A Consulta de Dados (`SELECT`)

Muitas classificações técnicas e editais agrupam o comando `SELECT` dentro da categoria DML (embora por vezes seja isolado como **DQL - Data Query Language**).

- **Estrutura Básica e Ordem de Execução do `SELECT`:**
    

|**Ordem de Escrita no Código**|**Ordem de Execução Interna pelo Banco**|**Função**|
|---|---|---|
|1. `SELECT`|1. `FROM` / `JOIN`|Identifica a origem das tabelas|
|2. `FROM`|2. `WHERE`|Filtra as linhas brutas|
|3. `WHERE`|3. `GROUP BY`|Agrupa os dados|
|4. `GROUP BY`|4. `HAVING`|Filtra os grupos agregados|
|5. `HAVING`|5. `SELECT`|Projeta as colunas na tela|
|6. `ORDER BY`|6. `ORDER BY`|Ordena o resultado final|

## 3. Resumo Visual para Provas e Revisões

```
         ┌── INSERT  ──> Adiciona novos dados
         │
DML ────┼── UPDATE  ──> Modifica dados existentes
         │
         ├── DELETE  ──> Remove dados específicos
         │
         └── SELECT* ──> Consulta dados armazenados
```

*O comando `SELECT` é tratado como DML ou DQL conforme a banca/métrica.