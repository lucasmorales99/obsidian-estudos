#db  #ACID

### Aula 1: O que é uma Transação?

Uma **transação** é uma sequência de operações SQL (como `INSERT`, `UPDATE`, `DELETE`) executadas como se fossem uma **única unidade lógica de trabalho**.

A regra do jogo é a seguinte: ou **todas** as operações da transação são salvas com sucesso no banco de dados, ou **nenhuma** delas é aplicada. Não existe meio-termo ou salvamento parcial.

#### O Exemplo Clássico: Transferência Bancária

Pense em uma transferência bancária de R$ 100 da conta da **Ana** para a conta do **Bruno**. Esse processo exige duas operações distintas no banco:

SQL

```
BEGIN TRANSACTION; -- Início do bloco transacional

-- Operação 1: Tira 100 da Ana
UPDATE Conta SET saldo = saldo - 100 WHERE titular = 'Ana';

-- Operação 2: Adiciona 100 no Bruno
UPDATE Conta SET saldo = saldo + 100 WHERE titular = 'Bruno';

COMMIT; -- Confirma a transação inteira
```

O que aconteceria se o servidor caísse ou a energia acabasse **exatamente após a Operação 1**? Se não houvesse o conceito de transação, a Ana perderia R$ 100 e o Bruno não receberia nada — o dinheiro sumiria!

É para resolver esse tipo de catástrofe que usamos comandos TCL (`COMMIT`, `ROLLBACK`, `SAVEPOINT`) protegidos pelas **propriedades ACID**.

### Aula 2: As Propriedades ACID

O acrônimo **ACID** representa os quatro requisitos de segurança que todo banco de dados relacional confiável (como PostgreSQL, Oracle ou MySQL) deve garantir:

```
 ┌─────────────────────────────────────────────────────────┐
 │                     PROPRIEDADES ACID                   │
 ├──────────────┬──────────────────────────────────────────┤
 │ A - Atomicidade │ Tudo ou nada!                          │
 │ C - Consistência│ Do estado válido A para o estado válido B│
 │ I - Isolamento  │ Transações paralelas não se atropelam │
 │ D - Durabilidade│ Commit é pra sempre (mesmo com queda) │
 └──────────────┴──────────────────────────────────────────┘
```

#### 1. ==**A**tomicidade== (_Atomicity_) — "**Tudo ou Nada**"

- **Conceito:** A transação é indivisível (como um átomo na visão clássica). Se qualquer instrução falhar no meio do caminho, o banco executa um ==**`ROLLBACK`**== automático e desfaz absolutamente tudo o que foi feito naquela sessão.
    
- **Exemplo:** Voltando ao exemplo bancário: se a Operação 2 falhar (por exemplo, a conta do Bruno foi cancelada), o saldo da Ana retorna aos R$ 100 originais como se a transação nunca tivesse existido.
    

#### 2. ==**C**onsistência== (_Consistency_) — "**Respeito às Regras**"

- **Conceito:** A transação só pode ==mover== o banco de dados de um estado ==válido== a outro estado ==válido==. Todas as restrições de integridade (_Constraints_ como `PRIMARY KEY`, `FOREIGN KEY`, `CHECK` e `NOT NULL`) devem ser estritamente satisfeitas antes que o `COMMIT` seja aceito.
    
- **Exemplo:** Se a tabela `Conta` tem uma restrição `CHECK (saldo >= 0)` e o saldo da Ana é de R$ 50, a tentativa de retirar R$ 100 violará a consistência. A transação falhará e será desfeita.
    

#### 3. ==**I**solamento== (_Isolation_) — "**Sem Interferência Concorrente**"

- **Conceito:** Garante que a execução de ==múltiplas transações== **concorrentes** ocorra de forma transparente, como se cada uma estivesse rodando ==sozinha== no banco de dados. O que uma transação altera só fica visível para outras sessões após a ==confirmação== (==`COMMIT`==).
    
- **Exemplo:** Se o banco executa um relatório financeiro lendo a tabela `Conta` no exato momento em que a transferência da Ana está em andamento (antes do `COMMIT`), o relatório verá os saldos antigos (intactos). Isso evita a chamada **Leitura Suja** (_Dirty Read_).
    

#### 4. ==**D**urabilidade== (_Durability_) — "**Dado Gravado é Dado Salvo**"

- **Conceito:** Uma vez que o banco respondeu que o **`COMMIT`** foi concluído, as ==alterações tornam-se permanentes==. Elas não serão perdidas, mesmo em caso de pane geral na máquina, falta de energia ou travamento do sistema operacional.
    
- **Como funciona por baixo dos panos:** Os bancos usam uma técnica chamada ==_Write-Ahead Logging_ (WAL)==. Antes de alterar a tabela em si, a operação é gravada em um arquivo de log em disco persistente. Em caso de queda, o banco lê esse log na reinicialização e reconstrói o estado correto.
    

### Aula 3: Níveis de Isolamento (Tópico Avançado)

O padrão SQL define 4 níveis de isolamento para equilibrar a segurança (consistência) e a velocidade do banco de dados (concorrência):

|**Nível de Isolamento**|**Evita Leitura Suja?**|**Evita Leitura Não-Repetível?**|**Evita Leitura Fantasma?**|
|---|---|---|---|
|**Read Uncommitted**|❌ Não|❌ Não|❌ Não|
|**Read Committed**|✅ Sim|❌ Não|❌ Não|
|**Repeatable Read**|✅ Sim|✅ Sim|❌ Não|
|**Serializable**|✅ Sim|✅ Sim|✅ Sim|

- ==**Read Uncommitted==:** O nível mais fraco. Permite ler dados de transações que ainda nem deram `COMMIT`.
    
- ==**Read Committed:**== O padrão na maioria dos SGBDs. Você só lê o que já foi confirmado.
    
- ==**Repeatable Read==:** Garante que se você ler a mesma linha duas vezes na mesma transação, verá exatamente os mesmos valores.
    
- ==**Serializable:**== O mais seguro e lento. Executa as transações em fila (serialmente), evitando qualquer anomalia de concorrência.
    

### Resumo para Provas e Prática Profissional

- **Comandos TCL:** `COMMIT` (salva definitivo), `ROLLBACK` (cancela tudo), `SAVEPOINT` (marca ponto de retorno parcial).
    
- **Sigla ACID:** **A**tomicidade (==tudo ou nada==), **C**onsistência (==respeita regras/constraints==), **I**solamento (==transações isoladas==), **D**urabilidade (==persistência pós-commit==).
    
- **ACID vs. BASE:** Sistemas relacionais operam com ACID. Sistemas distribuídos/NoSQL frequentemente usam **BASE** (_Basically Available, Soft-state, Eventual consistency_), flexibilizando a consistência imediata em prol da alta disponibilidade.