
Este guia abrange as **Formas Normais** utilizadas no processo de **Normalização de Dados** em bancos de dados relacionais.

A normalização visa organizar as estruturas de tabelas para **eliminar a redundância de dados** e **evitar anomalias de inserção, alteração e exclusão**.

### 1. Visão Geral das Formas Normais

A normalização é um processo progressivo: para estar em uma forma normal superior, o banco de dados obrigatoriamente deve atender a todos os requisitos das formas normais anteriores.

```
1FN ──► 2FN ──► 3FN ──► BCNF (FNBC) ──► 4FN ──► 5FN
```

### 2. Detalhamento das Formas Normais

#### A. Primeira Forma Normal (1FN) – Atributos Atômicos

- **Objetivo:** Garantir a atomicidade dos valores nas colunas e a inexistência de grupos repetitivos.
    
- **Regras:**
    
    1. Todos os atributos devem conter apenas **valores atômicos** (indivisíveis).
        
    2. Não devem existir **atributos multivalorados** (ex.: múltiplos telefones em um mesmo campo).
        
    3. Não devem existir **atributos compostos** (ex.: endereço contendo rua, número e CEP na mesma coluna).
        
    4. Não devem existir **grupos/colunas repetitivas** (ex.: `Telefone1`, `Telefone2`, `Telefone3`).
        
- **Como Resolver:** Mover os dados repetitivos ou multivalorados para uma nova tabela, relacionando-a com a tabela principal via Chave Estrangeira (FK).
    

#### B. Segunda Forma Normal (2FN) – Dependência Funcional Total

- **Pré-requisito:** Estar na **1FN**.
    
- **Objetivo:** Eliminar **dependências parciais**.
    
- **Regras:**
    
    - Todos os atributos não-chave devem depender de **toda** a Chave Primária (PK), e não apenas de parte dela.
        
    - _Atenção:_ A 2FN só é relevante para tabelas que possuem **Chaves Primárias Compostas** (formadas por duas ou mais colunas). Se a PK for simples (única coluna), a tabela automaticamente já atende à 2FN se estiver na 1FN.
        
- **Como Resolver:** Decompor a tabela, isolando os atributos que dependem apenas de parte da chave composta em uma nova tabela.
    

#### C. Terceira Forma Normal (3FN) – Dependência Transitiva

- **Pré-requisito:** Estar na **2FN**.
    
- **Objetivo:** Eliminar **dependências transitivas**.
    
- **Regras:**
    
    - Nenhum atributo não-chave deve depender de outro atributo não-chave.
        
    - Em termos formais: para toda dependência funcional $X \rightarrow Y$, $X$ deve ser uma chave candidata ou superchave, ou $Y$ deve fazer parte de uma chave.
        
    - _Exemplo Clássico:_ Na tabela `Funcionario(ID, Nome, CEP, Cidade)`, o campo `Cidade` depende do `CEP` (não-chave), que por sua vez depende do `ID` (PK). Existe uma dependência transitiva entre `ID` $\rightarrow$ `CEP` $\rightarrow$ `Cidade`.
        
- **Como Resolver:** Remover o atributo derivado/transitivo e criar uma tabela própria para a entidade intermediária (ex.: criar a tabela `Endereco(CEP, Cidade)` e manter apenas `CEP` como FK na tabela `Funcionario`).
    

#### D. Forma Normal de Boyce-Codd (BCNF / FNBC)

- **Pré-requisito:** Estar na **3FN**.
    
- **Objetivo:** Resolver anomalias em tabelas com múltiplas chaves candidatas sobrepostas.
    
- **Regras:**
    
    - É uma versão mais estrita da 3FN.
        
    - Para **toda** dependência funcional da forma $X \rightarrow Y$, $X$ **obrigatoriamente deve ser uma superchave** (ou chave candidata).
        
    - Se existir uma regra em que um atributo determine outro, esse determinante precisa ser uma chave.
        

#### E. Quarta Forma Normal (4FN) – Dependência Multivalorada

- **Pré-requisito:** Estar na **BCNF**.
    
- **Objetivo:** Eliminar **dependências multivaloradas (DMV)** independentes em uma mesma tabela.
    
- **Regras:**
    
    - Ocorre quando uma tabela possui atributos independentes de cardinalidade "muitos" para uma mesma chave.
        
    - _Exemplo:_ Uma tabela `Professor(ID, Disciplina, Idioma)` onde um professor leciona várias disciplinas e fala vários idiomas de forma independente, gerando combinações desnecessárias.
        
- **Como Resolver:** Dividir a tabela em duas: `Professor_Disciplina(ID, Disciplina)` e `Professor_Idioma(ID, Idioma)`.
    

#### F. Quinta Forma Normal (5FN) – Dependência de Junção

- **Pré-requisito:** Estar na **4FN**.
    
- **Objetivo:** Garantir que a tabela não possa ser decomposta em tabelas menores e reconstruída via junção (_join_) sem a perda ou criação de tuplas falsas (anomalia de junção).
    

### 3. Tabela Comparativa de Resumo para Provas e Revisão

|**Forma Normal**|**Requisito Principal**|**O que Elimina?**|
|---|---|---|
|**1FN**|Atributos atômicos e sem grupos repetitivos|Campos multivalorados e compostos|
|**2FN**|Estar na 1FN + Dependência funcional total da PK|Dependências parciais de chaves compostas|
|**3FN**|Estar na 2FN + Atributos não-chave dependem apenas da PK|Dependências transitivas (não-chave $\rightarrow$ não-chave)|
|**BCNF**|Estar na 3FN + Todo determinante $X \rightarrow Y$ é superchave|Anomalias de chaves candidatas sobrepostas|
|**4FN**|Estar na BCNF + Sem dependências multivaloradas|Fatos multivalorados independentes na mesma tabela|
|**5FN**|Estar na 4FN + Reconstrução sem perdas via junção|Anomalias de dependência de junção|

### 4. Normalização vs. Desnormalização

- **Normalização:** Prioriza a **integridade**, **consistência** e eliminação de redundâncias, ideal para ambientes transacionais (OLTP).
    
- **Desnormalização:** Processo intencional de introduzir redundância controlada (ex.: unificar tabelas ou duplicar colunas) para reduzir o número de junções (_joins_) e **otimizar a performance de leitura**, muito utilizado em sistemas analíticos e Data Warehouses (OLAP).