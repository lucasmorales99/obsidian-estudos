#db 

A **TCL (Transaction Control Language)** é a sublinguagem do SQL responsável pelo **gerenciamento de transações** no banco de dados.

Ela garante a integridade e a consistência das operações que envolvem modificações de dados (`INSERT`, `UPDATE`, `DELETE`), funcionando sob o princípio de "tudo ou nada" (propriedade de **Atomicidade** das propriedades ACID).

# Guia de Estudo: TCL (Transaction Control Language)

Uma **transação** é um conjunto de comandos SQL executados como uma única unidade lógica de trabalho. A TCL permite confirmar ou cancelar essas operações antes que elas se tornem definitivas no sistema.

## 1. Principais Comandos TCL

### A. `COMMIT`

Confirma e salva permanentemente todas as alterações realizadas pela transação atual no banco de dados.

- **Efeito:** As modificações ficam visíveis para todos os outros usuários/sessões e **não podem mais ser desfeitas** por um `ROLLBACK`.
    
- **Exemplo:**
    

SQL

```
BEGIN TRANSACTION;

UPDATE Conta_Bancaria SET saldo = saldo - 100 WHERE id_conta = 1;
UPDATE Conta_Bancaria SET saldo = saldo + 100 WHERE id_conta = 2;

-- Salva as alterações de forma definitiva
COMMIT;
```

### B. `ROLLBACK`

Desfaz todas as alterações realizadas durante a transação atual que ainda não foram salvas com `COMMIT`.

- **Efeito:** O banco de dados retorna ao estado exato em que estava antes do início da transação.
    
- **Exemplo:**
    

SQL

```
BEGIN TRANSACTION;

DELETE FROM Funcionario WHERE id_depto = 10;

-- Identificou um erro? Cancela a operação e recupera os dados deletados
ROLLBACK;
```

### C. `SAVEPOINT`

Cria um "ponto de restauração" intermediário dentro de uma transação. Permite desfazer apenas parte das operações executadas sem precisar cancelar a transação inteira.

- **Sintaxe Básica:**
    

SQL

```
SAVEPOINT nome_do_ponto;
ROLLBACK TO nome_do_ponto;
```

- **Exemplo Prático:**
    

SQL

```
BEGIN TRANSACTION;

INSERT INTO Pedido (id, cliente) VALUES (101, 'Maria');
SAVEPOINT ponto_pedido; -- Ponto de salvamento 1

INSERT INTO Item_Pedido (pedido_id, produto) VALUES (101, 'Notebook');
-- Ocorreu um erro ao inserir o segundo item:
INSERT INTO Item_Pedido (pedido_id, produto) VALUES (101, 'ProdutoInexistente'); 

-- Desfaz apenas os itens adicionados após o SAVEPOINT, mantendo o Pedido
ROLLBACK TO ponto_pedido;

-- Finaliza confirmando apenas a gravação do Pedido original
COMMIT;
```

### D. `SET TRANSACTION`

Define propriedades e características para a transação atual, como o nível de isolamento de concorrência ou o modo de acesso (somente leitura ou leitura/escrita).

- **Exemplo:**
    

SQL

```
-- Define a transação apenas para consulta de relatórios (evita bloqueios desnecessários)
SET TRANSACTION READ ONLY;
```

## 2. A Propriedade ACID das Transações

A TCL existe para garantir as propriedades **ACID** do banco de dados:

|**Sigla**|**Propriedade**|**Papel da TCL**|
|---|---|---|
|**A**|**Atomicidade**|Garante que a transação ocorra por inteiro ou não ocorra nada (`COMMIT` / `ROLLBACK`).|
|**C**|**Consistência**|Leva o banco de um estado válido a outro estado válido após o `COMMIT`.|
|**I**|**Isolamento**|Controla a visibilidade de transações concorrentes (`SET TRANSACTION`).|
|**D**|**Durabilidade**|Garante que dados confirmados com `COMMIT` não sejam perdidos, mesmo em falhas.|

## 3. Resumo Geral de Sublinguagens SQL

| **Sublinguagem** | **Função Principal**                             | **Comandos de Exemplo**               |
| ---------------- | ------------------------------------------------ | ------------------------------------- |
| **DDL**          | Define e altera a estrutura das tabelas/esquemas | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` |
| **DML**          | Manipula os dados contidos nas tabelas           | `INSERT`, `UPDATE`, `DELETE`          |
| **DQL**          | Consulta e recupera informações                  | `SELECT`                              |
| **DCL**          | Controla acessos e privilégios de usuários       | `GRANT`, `REVOKE`                     |
| **TCL**          | Gerencia transações e consistência dos dados     | `COMMIT`, `ROLLBACK`, `SAVEPOINT`     |