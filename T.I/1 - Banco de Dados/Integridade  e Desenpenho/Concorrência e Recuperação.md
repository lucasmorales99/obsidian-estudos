#integridadeEDesenpenho #db 

### Parte 1: Controle de Concorrência

O ==**Controle de Concorrência**== garante que múltiplas transações rodando em paralelo não corruptam os dados ou gerem resultados inconsistentes.

#### 1. Os Problemas da Concorrência Descontrolada (==Anomalias==)

Se dois usuários tentarem alterar o mesmo registro no mesmo milissegundo sem controle, três problemas graves acontecem:

- **Perda de Atualização ==(_Lost Update_)==:** Duas transações leem o mesmo dado. A Transação A altera e grava. Logo em seguida, a Transação B altera com base no dado antigo e grava por cima, sobrescrevendo e "apagando" o trabalho da Transação A.
    
- **Leitura Suja ==(_Dirty Read_)==:** A Transação A altera um registro, mas **não deu COMMIT ainda**. A Transação B lê esse dado alterado. Em seguida, a Transação A dá `ROLLBACK`. A Transação B trabalhou com um dado "fantasma" que nunca existiu oficialmente.
    
- **Leitura Não-Repetível ==(_Unrepeatable Read_)==:** A Transação A lê uma linha. A Transação B altera ou deleta essa linha e dá `COMMIT`. A Transação A lê a mesma linha de novo e vê dados totalmente diferentes.
    

#### 2. Mecanismos de Solução: Bloqueios (==Locks==)

Para conter as anomalias, o banco aplica **travas (Locks)** nas linhas ou tabelas.

- **Bloqueio Compartilhado (Shared Lock / Read Lock - S):** Usado para **==leitura==**. Várias transações podem ter um _Lock S_ na mesma linha simultaneamente.
    
- **Bloqueio Exclusivo (Exclusive Lock / Write Lock - X):** Usado para **==escrita==** (`UPDATE`, `DELETE`, `INSERT`). Apenas **uma** transação pode segurar esse bloqueio por vez, impedindo qualquer outra de ler ou escrever.
    

##### Protocolo de Bloqueio em Duas Fases (2PL - ==Two-Phase Locking==)

Para garantir a propriedade de **Isolamento** do ACID, os bancos usam o protocolo **2PL**, dividido em duas etapas:

1. **Fase de Crescimento (_Growing Phase_):** A transação só ==adquire== novas travas e ==não libera== nenhuma.
    
2. **Fase de Encolhimento (_Shrinking Phase_):** A transação ==começa a liberar== as travas e ==não== ==pode solicitar== mais ==nenhuma==.
    

```
       [Adquire Trava 1] ──► [Adquire Trava 2] ──► [Ponto Máximo] ──► [Libera Trava 1] ──► [Libera Trava 2]
       └─────────────── Fase de Crescimento ────────────────┘     └────────────── Fase de Encolhimento ─────────────┘
```

##### O Efeito Colateral: ==Deadlock== (Impasse)

Se a ==Transação 1 trava== o _Recurso A_ e espera o _Recurso B_, enquanto a Transação 2 trava o _Recurso B_ e espera o _Recurso A_, o sistema para em um **Deadlock**. O banco de dados identifica o ciclo e mata uma das transações ==forcando um `ROLLBACK`.==

### Parte 2: Técnicas de Recuperação (==Recovery==)

O módulo de **Recuperação** garante a **Atomicidade** e a **Durabilidade** do ACID. Se o servidor perder a energia no meio de uma operação, como o banco volta a ficar saudável?

#### 1. ==Write-Ahead Logging== (WAL)

É a regra de **ouro** dos bancos de dados relacionais: Nenhuma alteração de dados vai para o disco definitivo (tabela) sem que a ação tenha sido gravada primeiro em um arquivo sequencial de Log no disco.

O ==log armazena entradas== como:

- `<T1, START>` (Início da transação)
    
- `<T1, ValorAntigo, ValorNovo VariavelX,>`
    
- `<T1, COMMIT>` ou `<T1, ABORT>`
    

#### 2. O Algoritmo de Recuperação: ==UNDO e REDO==

Quando o servidor reinicia após um travamento (_crash_), a engine de recuperação lê o arquivo WAL do último **Checkpoint** (ponto de salvamento seguro na memória) até o final e aplica a regra:

```
                          ┌── Houve COMMIT / CHECKPOINT? ──► Alica REDO  (Refazer a alteração)
   Registros no WAL ─────┤
                          └── NÃO houve COMMIT? ──────────► Aplica UNDO  (Desfazer a alteração)
```

- ==**REDO (Refazer)==:** Se no arquivo de log existe a marcação `<T1, COMMIT>`, mas os dados reais ainda não tinham subido para o disco no momento do crash, o banco executa novamente as alterações gravadas no log.
    
- ==**UNDO (Desfazer)==:** Se no arquivo de log existe a alteração `<T2, VariavelX...>`, mas **não existe** a confirmação `<T2, COMMIT>` (ou seja, a transação ficou pela metade), o banco pega o _ValorAntigo_ gravado no log e desfaz a operação para restaurar a consistência do banco.
    

### Exemplo Prático Integrado

Imagine um caixa eletrônico atualizando o valor de uma conta de R$ 500 para R$ 400:

1. **Concorrência:** O banco coloca um **Bloqueio Exclusivo (Lock X)** no registro da conta para garantir que ninguém leia o valor antigo enquanto a transação ocorre.
    
2. **Log em Disco (WAL):** O banco escreve no Log: `<T1, 400 500, Conta_123,>`.
    
3. **Falta de Energia:** A luz acaba **antes** do envio da confirmação de sucesso ao cliente.
    
4. **Religando o Servidor:** O banco lê o arquivo WAL. Ao perceber que a transação `T1` não tem um registro `<T1, COMMIT>`, o mecanismo de **Recuperação** executa uma ação de **UNDO**, devolvendo o valor da conta para R$ 500.
    

### Resumo Visual para Revisões e Provas

| **Conceito**                 | **Função Principal**                                                   | **Mecanismo / Ferramenta**                                           |
| ---------------------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Controle de Concorrência** | Evita interferência entre transações em execução simultânea.           | Locks (Compartilhado/Exclusivo), 2PL e MVCC.                         |
| **Deadlock**                 | Impasse onde duas transações esperam o recurso travado pela outra.     | Detectado por algoritmo de grafos; resolvido via `ROLLBACK` forçado. |
| **WAL (Write-Ahead Log)**    | ==Registrar ações no log em disco antes de gravar nas tabelas.==       | Arquivo de log sequencial em disco.                                  |
| **REDO**                     | Refazer alterações de transações confirmadas (`COMMIT`).               | Leitura de log pós-crash.                                            |
| **UNDO**                     | Desfazer alterações de transações incompletas (sem `COMMIT`)[cite: 1]. | Restauração de valores legados via arquivo de log[cite: 1].          |