#db  #dcl

# Guia de Estudo: DCL (Data Control Language)

As alterações feitas via comandos DCL costumam ser aplicadas de forma imediata na tabela do sistema de privilégios do SGBD.

## 1. Os Dois Comandos Principais da DCL

### A. `GRANT` (Conceder)

Atribui privilégios de acesso a usuários ou a papéis (_roles_) do sistema.

- **Sintaxe Básica:**
    

SQL

```
GRANT tipo_de_privilegio ON nome_do_objeto TO usuario_ou_papel;
```

- **Exemplos Práticos:**
    
    - **Permissão de Leitura:**
        
        SQL
        
        ```
        -- Concede permissão apenas de consultar a tabela 'Funcionario' para o usuário 'analista'
        GRANT SELECT ON Funcionario TO analista_dados;
        ```
        
    - **Múltiplas Permissões:**
        
        SQL
        
        ```
        -- Concede inserção e alteração na tabela 'Pedido' para o usuário 'vendedor'
        GRANT INSERT, UPDATE ON Pedido TO vendedor_moraes;
        ```
        
    - **Acesso Total a uma Tabela:**
        
        SQL
        
        ```
        -- Concede TODOS os privilégios na tabela 'Cliente' para um perfil
        GRANT ALL PRIVILEGES ON Cliente TO gerente_geral;
        ```
        
    - **Opção de Repassar Permissão (`WITH GRANT OPTION`):**
        
        SQL
        
        ```
        -- Permite que o usuário receba o privilégio e TAMBÉM possa concedê-lo a outros
        GRANT SELECT ON Funcionario TO coordenador WITH GRANT OPTION;
        ```
        

### B. `REVOKE` (Revogar / Remover)

Remove privilégios que foram concedidos anteriormente a um usuário ou papel.

- **Sintaxe Básica:**
    

SQL

```
REVOKE tipo_de_privilegio ON nome_do_objeto FROM usuario_ou_papel;
```

- **Exemplos Práticos:**
    
    - **Remover permissão de modificação:**
        
        SQL
        
        ```
        -- Remove o direito de atualizar e deletar dados da tabela 'Funcionario'
        REVOKE UPDATE, DELETE ON Funcionario FROM analista_dados;
        ```
        
    - **Remover todas as permissões de uma tabela:**
        
        SQL
        
        ```
        REVOKE ALL PRIVILEGES ON Cliente FROM ex_funcionario;
        ```
        
    - **Revogar em Cascata (`CASCADE`):**
        
        SQL
        
        ```
        -- Se o usuário 'coordenador' concedeu acessos para outros, revoga dele E dos outros
        REVOKE SELECT ON Funcionario FROM coordenador CASCADE;
        ```
        

## 2. Tipos de Privilégios no Banco de Dados

Os privilégios dividem-se em duas categorias principais:

### A. Privilégios do Sistema (_System Privileges_)

Autorizam ações globais que impactam o banco de dados como um todo:

- `CREATE TABLE`: Permite criar novas tabelas.
    
- `CREATE SESSION`: Permite conectar-se ao banco de dados.
    
- `CREATE USER`: Permite criar novos usuários no SGBD.
    

### B. Privilégios de Objetos (_Object Privileges_)

Autorizam ações específicas em objetos (tabelas, visões, procedimentos, etc.):

- `SELECT`, `INSERT`, `UPDATE`, `DELETE`: Permitem manipular/consultar registros.
    
- `EXECUTE`: Permite executar _Stored Procedures_ ou _Functions_.
    
- `REFERENCES`: Permite criar uma Chave Estrangeira (`FOREIGN KEY`) apontando para a tabela.
    

## 3. Gerenciamento Prático com Papéis (_Roles_)

Em vez de conceder permissões usuário por usuário, a boa prática de segurança utiliza **Roles** (grupos de privilégios agrupados por função):

SQL

```
-- 1. Criar um papel para o setor financeiro
CREATE ROLE perfil_financeiro;

-- 2. Conceder privilégios ao papel (DCL)
GRANT SELECT, INSERT, UPDATE ON Contas_A_Pagar TO perfil_financeiro;

-- 3. Atribuir o papel aos usuários
GRANT perfil_financeiro TO joao_financeiro, maria_financeiro;
```

## 4. Comparativo Completo do Ecossistema SQL

| **Sublinguagem** | **Significado**              | **Comandos Principais**               | **Foco**               |
| ---------------- | ---------------------------- | ------------------------------------- | ---------------------- |
| **DDL**          | Data Definition Language     | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Estrutura (_Schema_)   |
| **DML**          | Data Manipulation Language   | `INSERT`, `UPDATE`, `DELETE`          | Dados (Conteúdo)       |
| **DQL**          | Data Query Language          | `SELECT`                              | Consultas / Leitura    |
| **DCL**          | Data Control Language        | `GRANT`, `REVOKE`                     | Permissões / Segurança |
| **TCL**          | Transaction Control Language | `COMMIT`, `ROLLBACK`, `SAVEPOINT`     | Controle de Transações |

