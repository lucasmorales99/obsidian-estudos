Olá, futuro(a) servidor(a)! Seja muito bem-vindo(a) a mais esta aula essencial de Raciocínio Lógico-Matemático. Como seu professor, elaborei este guia focado exclusivamente no subitem **11.3 do edital: Equivalências Lógicas**, dentro do tópico de **Lógica Sentencial (ou Proposicional)**, estruturado para atender ao perfil de cobrança da banca **CEBRASPE**.

PDF+ 3

Nas provas do CEBRASPE no formato **"Certo ou Errado"**, a cobrança de equivalências não exige demonstrações algébricas longas. A banca foca na **reescrita de proposições compostas mantendo o mesmo valor lógico** e na **identificação rápida de regras clássicas de transformação**.

### 📚 GUIA DE LÓGICA PROPOSICIONAL: EQUIVALÊNCIAS LÓGICAS (FOCO CEBRASPE)

Duas proposições compostas são **equivalentes** (≡ ou ⇔) quando possuem exatamente a mesma tabela-verdade, ou seja, assumem os mesmos valores lógicos (V ou F) para quaisquer valorações de suas proposições simples.

#### 1. AS EQUIVALÊNCIAS DA CONDICIONAL (P→Q) — O "CARRO-CHEFE" DA BANCA

A proposição condicional **"Se P, então Q"** (P→Q) é a estrutura mais cobrada pelo CEBRASPE. Ela possui **duas equivalências fundamentais** que você precisa dominar:

##### **A) Transposição / Contrapositiva (Regra "Inverte e Nega")**

Para reescrever uma condicional usando a contrapositiva:

1. Inverte-se a ordem das proposições (o consequente Q vira antecedente e o antecedente P vira consequente).
    
2. Nega-se ambas as proposições.
    

P→Q≡¬Q→¬P

> **Regra prática:** _"Volta negando tudo."_

- **Exemplo:**
    
    - **Original (P→Q):** "Se o servidor estuda, então ele passa no concurso."
        
    - **Equivalente (¬Q→¬P):** "Se o servidor **não** passa no concurso, então ele **não** estuda."
        

##### **B) Equivalência da Condicional em Disjunção (Regra "NEAMAR" / "NEGA OU MANTÉM")**

Transforma uma estrutura de condicional ("Se... então") em uma disjunção inclusiva ("OU"):

1. Nega-se a primeira parte (¬P).
    
2. **Troca-se o "Se... então" pelo "OU" (∨)**.
    
3. Mantém-se a segunda parte sem alterar (Q).
    

P→Q≡¬P∨Q

> **Regra prática:** _"Nega a primeira, troca pelo OU, e mantém a segunda."_

- **Exemplo:**
    
    - **Original (P→Q):** "Se o auditor analisa o processo, então o parecer é emitido."
        
    - **Equivalente (¬P∨Q):** "O auditor **não** analisa o processo **OU** o parecer é emitido."
        

#### 2. EQUIVALÊNCIAS DA BICONDICIONAL (P↔Q) E DA DISJUNÇÃO EXCLUSIVA (P∨​Q)

##### **A) Bicondicional (P↔Q)**

A proposição "P se e somente se Q" significa que P implica Q **e** Q implica P simultaneamente:

P↔Q≡(P→Q)∧(Q→P)

- **Outra equivalência válida:** Negação de ambas as partes mantém a bicondicional:
    
    P↔Q≡¬P↔¬Q
    

##### **B) Disjunção Exclusiva (P∨​Q)**

A disjunção exclusiva ("Ou P ou Q") é equivalente à **negação da bicondicional**:

P∨​Q≡¬(P↔Q)

#### 3. OUTRAS PROPRIEDADES DE EQUIVALÊNCIA ÚTEIS

- **Dupla Negação (Involução):** ¬(¬P)≡P
    
- **Comutativa:**
    
    - P∧Q≡Q∧P
        
    - P∨Q≡Q∨P
        
    - P↔Q≡Q↔P
        
- **Idempotente:**
    
    - P∧P≡P
        
    - P∨P≡P
        

#### 4. ARMADILHAS CLÁSSICAS DO CEBRASPE

##### **A) A Falsa Inversão Simples (Recíproca Incorreta)**

A banca inverte o antecedente e o consequente **sem negar** as partes e afirma ser uma equivalência.

- _Enunciado:_ A proposição "Se chove, então a rua molha" é equivalente a "Se a rua molha, então chove".
    
- _Análise:_ **ERRADO.** P→Q **não é equivalente** a Q→P.
    

##### **B) A Falsa Negação Direta (Inversa Incorreta)**

A banca nega ambas as partes **sem inverter** a posição delas.

- _Enunciado:_ A proposição "Se corro, fico cansado" é equivalente a "Se não corro, não fico cansado".
    
- _Análise:_ **ERRADO.** P→Q **não é equivalente** a ¬P→¬Q.
    

##### **C) Confundir Equivalência de P→Q com a Leis de De Morgan**

Lembre-se: As Leis de De Morgan servem para **negar** "E" (∧) e "OU" (∨). Já para **reescrever de forma equivalente** uma condicional, usa-se a Contrapositiva (¬Q→¬P) ou o NEAMAR (¬P∨Q).

#### 5. QUADRO RESUMO DE EQUIVALÊNCIAS RECORRENTES DA BANCA

|Proposição Original|Conectivo|Forma Equivalente 1|Forma Equivalente 2|
|---|---|---|---|
|**P→Q**|Condicional|**¬Q→¬P** (Contrapositiva)|**¬P∨Q** (Disjunção / NEAMAR)|
|**P∨Q**|Disjunção|**¬P→Q** (Condicional)|**¬Q→P** (Condicional)|
|**P↔Q**|Bicondicional|**(P→Q)∧(Q→P)**|**¬P↔¬Q**|
|**P∨​Q**|Disj. Exclusiva|**¬(P↔Q)**|**(P∨Q)∧¬(P∧Q)**|

#### 6. MODELOS DE QUESTÕES NO ESTILO CEBRASPE ("CERTO OU ERRADO")

##### **Modelo 1: Equivalência pela Contrapositiva (¬Q→¬P)**

- **Item:** A proposição _"Se o relatório for entregue no prazo, então o projeto será aprovado"_ é logicamente equivalente à proposição _"Se o projeto não for aprovado, então o relatório não foi entregue no prazo"_.
    
- **Análise:**
    
    - Proposição original: P→Q
        
    - Aplicação da contrapositiva: ¬Q→¬P
        
    - A banca invertia a ordem e negou ambas as partes ("não aprovado" → "não entregue").
        
- **Gabarito:** **CERTO.**
    

##### **Modelo 2: Equivalência pelo NEAMAR (¬P∨Q)**

- **Item:** Dizer que _"Se o fiscal realiza a vistoria, a irregularidade é notificada"_ é logicamente equivalente a dizer que _"O fiscal não realiza a vistoria ou a irregularidade é notificada"_.
    
- **Análise:**
    
    - Proposição original: P→Q
        
    - Aplicação da regra do "OU": Nega a primeira (¬P: "fiscal não realiza"), troca "Se... então" por "OU", e mantém a segunda (Q: "irregularidade é notificada").
        
- **Gabarito:** **CERTO.**
    

##### **Modelo 3: Pegadinha da Inversão Simples**

- **Item:** A proposição _"Se o candidato estuda bastante, ele obtém bom desempenho"_ é equivalente à proposição _"Se o candidato obteve bom desempenho, então ele estudou bastante"_.
    
- **Análise:**
    
    - Proposição original: P→Q
        
    - O item apenas trocou de posição (Q→P) sem aplicar as negações. A simples comutativa não se aplica diretamente à condicional desta forma.
        
- **Gabarito:** **ERRADO.**
