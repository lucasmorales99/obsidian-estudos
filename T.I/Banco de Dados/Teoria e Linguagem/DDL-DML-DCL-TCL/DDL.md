#DB
DDL significa ==**Data Definition Language** (Linguagem de Definição de Dados)== e é a parte do [SQL](https://www.datacamp.com/pt/tutorial/sql-ddl-commands) usada para criar, alterar e apagar a **estrutura** de um banco de dados.
Ela lida com os **objetos** do banco (como tabelas, índices e visões), e não com as linhas de informação de dentro deles.

Principais Comandos DDL

- **`CREATE`**: Cria um novo objeto no banco de dados (por exemplo, uma nova tabela ou um índice).

- **`ALTER`**: Modifica a estrutura de um objeto que já existe (como adicionar ou apagar uma coluna de uma tabela).

- **`DROP`**: Apaga um objeto inteiro do banco de dados.

- **`TRUNCATE`**: Esvazia todos os dados de uma tabela de uma vez, mas mantém a estrutura dela pronta para uso. [[1](https://www.treinaweb.com.br/blog/principais-comandos-sql), [2](https://dev.to/mpfdev/entendendo-a-relacao-entre-sql-dml-e-ddl-fundamentos-de-banco-de-dados-23bi)]





# Guia de Estudo: DDL (Data Definition Language)

A **DDL** lida com a **estrutura do banco de dados** (o _schema_), e não com os dados inseridos nas tabelas.

> **Nota importante:** Na maioria dos SGBDs (como Oracle, PostgreSQL, MySQL), comandos DDL executam um **COMMIT implícito**. Isso significa que suas alterações de estrutura são salvas de forma permanente imediatamente.

## 1. Principais Comandos DDL

### A. `CREATE`

Utilizado para criar novas estruturas no banco de dados (tabelas, índices, visões, esquemas, etc.).

- **Sintaxe Básica (`CREATE TABLE`):**
    

SQL

```
CREATE TABLE Funcionario (
    id_func INT NOT NULL,
    nome VARCHAR(100) NOT NULL,
    cpf VARCHAR(11) UNIQUE,
    salario DECIMAL(10, 2),
    data_admissao DATE DEFAULT CURRENT_DATE,
    id_depto INT,
    
    -- Definindo Chaves e Restrições (Constraints)
    CONSTRAINT pk_funcionario PRIMARY KEY (id_func),
    CONSTRAINT fk_func_depto FOREIGN KEY (id_depto) REFERENCES Departamento(id_depto)
);
```

### B. `ALTER`

Modifica a estrutura de um objeto já existente no banco de dados (adicionar, remover ou alterar colunas e restrições).

- **Adicionar uma coluna:**
    

SQL

```
ALTER TABLE Funcionario 
ADD email VARCHAR(150);
```

- **Modificar o tipo/propriedade de uma coluna:**
    

SQL

```
-- Exemplo no PostgreSQL / MySQL
ALTER TABLE Funcionario 
MODIFY COLUMN email VARCHAR(200);

-- Exemplo no Oracle
ALTER TABLE Funcionario 
MODIFY email VARCHAR2(200);
```

- **Remover uma coluna:**
    

SQL

```
ALTER TABLE Funcionario 
DROP COLUMN email;
```

- **Adicionar uma Restrição (Constraint):**
    

SQL

```
ALTER TABLE Funcionario 
ADD CONSTRAINT chk_salario CHECK (salario >= 0);
```

### C. `DROP`

Remove completamente um objeto e toda a sua estrutura do banco de dados (ação irreversível na maioria dos casos).

SQL

```
-- Remove a tabela e todos os seus dados
DROP TABLE Funcionario;

-- Remove a tabela e apaga automaticamente todas as restrições de FK associadas a ela
DROP TABLE Departamento CASCADE CONSTRAINTS;
```

### D. `TRUNCATE`

Esvazia uma tabela inteira, removendo **todas as suas linhas**, mas **mantendo a estrutura** (colunas, tipos e constraints) intacta.

SQL

```
TRUNCATE TABLE Funcionario;
```

> **`DELETE` (DML) vs. `TRUNCATE` (DDL):**
> 
> - `DELETE`: É um comando DML (Data Manipulation Language). Apaga linha por linha, pode ser desfeito via `ROLLBACK` e aciona _Triggers_.
>     
> - `TRUNCATE`: É um comando DDL. Desaloca as páginas de memória de uma só vez, é extremamente mais rápido, não dispara _Triggers_ de deleção e reinicia sequências auto-incrementais.
>     

### E. `RENAME`

Renomeia um objeto existente (tabela, coluna, etc.).

SQL

```
-- Renomeando uma tabela
RENAME Funcionario TO Colaborador;
```

## 2. Tipos de Restrições (_Constraints_)

As restrições garantem a integridade dos dados diretamente no nível de definição de tabelas (Modelo Lógico/Físico):

|**Constraint**|**Descrição**|
|---|---|
|**`PRIMARY KEY` (PK)**|Identifica unicamente cada registro da tabela. Não permite valores `NULL` nem duplicados.|
|**`FOREIGN KEY` (FK)**|Garante a integridade referencial com a chave primária de outra tabela.|
|**`NOT NULL`**|Impede que a coluna aceite valores nulos/vazios.|
|**`UNIQUE`**|Garante que todos os valores em uma coluna sejam distintos entre si (permite um valor `NULL`).|
|**`CHECK`**|Valida se os valores inseridos na coluna atendem a uma condição lógica predefinida.|
|**`DEFAULT`**|Define um valor padrão caso nenhum seja fornecido durante a inserção.|

## 3. Resumo de Outros Objetos Criados via DDL

Além de tabelas (`TABLE`), a DDL é usada para gerenciar outros objetos do SGBD:

- **Visões (`VIEW`):** Tabelas virtuais baseadas em consultas `SELECT`.
    
    SQL
    
    ```
    CREATE VIEW vw_funcionarios_ativos AS 
    SELECT nome, email FROM Funcionario WHERE ativo = 1;
    ```
    
- **Índices (`INDEX`):** Estruturas que otimizam a velocidade de busca/consultas no banco de dados.
    
    SQL
    
    ```
    CREATE INDEX idx_func_nome ON Funcionario(nome);
    ```
    
- **Sequências (`SEQUENCE`):** Geradores de números sequenciais (muito utilizados no Oracle e PostgreSQL para simular auto-incremento).
    
    SQL
    
    ```
    CREATE SEQUENCE seq_func_id START WITH 1 INCREMENT BY 1;
    ```
    

## 4. Comparativo Rápido para Revisão/Provas

- **DDL (Data Definition Language):** Mexe na **estrutura/esquema** (`CREATE`, `ALTER`, `DROP`, `TRUNCATE`, `RENAME`).
    
- **DML (Data Manipulation Language):** Mexe nos **dados** (`INSERT`, `UPDATE`, `DELETE`).
    
- **DQL (Data Query Language):** Consulta os **dados** (`SELECT`).