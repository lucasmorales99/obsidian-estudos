Olá, futuro(a) servidor(a)! Seja muito bem-vindo(a) a esta aula focada no subitem **11.4 do edital: Leis de De Morgan**, dentro da **Lógica Sentencial (ou Proposicional)**, preparada sob medida para a banca **CEBRASPE**.

Nas provas do CEBRASPE no formato **"Certo ou Errado"**, a cobrança sobre as Leis de De Morgan foca principalmente na **negação de proposições compostas** (conectivos **E** e **OU**) e na **reescrita textual equivalente**. O examinador adora criar frases longas e tentar confundir o candidato trocando a negação dos termos ou mantendo o conectivo original incorretamente.

### 📚 GUIA DE LÓGICA PROPOSICIONAL: LEIS DE DE MORGAN (FOCO CEBRASPE)

As Leis de De Morgan estabelecem como devemos fazer a **negação lógica** de uma conjunção ($P \land Q$) ou de uma disjunção ($P \lor Q$).

#### 1. AS DUAS LEIS DE DE MORGAN (ESTRUTURA FORMAL)

##### **1ª Lei: Negação da Conjunção ($\land$ - conectivo "E")**

Para negar uma proposição composta pelo conectivo **"E"**:

1. Nega-se a primeira proposição ($\neg P$).
    
2. Nega-se a segunda proposição ($\neg Q$).
    
3. **Troca-se o "E" ($\land$) pelo "OU" ($\lor$)**.
    

$$\neg (P \land Q) \equiv \neg P \lor \neg Q$$

> **Regra prática:** _"Nega tudo e troca o E pelo OU."_

- **Exemplo Simples:**
    
    - **Proposição ($P \land Q$):** "O auditor analisou o processo **E** assinou o parecer."
        
    - **Negação ($\neg P \lor \neg Q$):** "O auditor **não** analisou o processo **OU não** assinou o parecer."
        

##### **2ª Lei: Negação da Disjunção ($\lor$ - conectivo "OU")**

Para negar uma proposição composta pelo conectivo **"OU"**:

1. Nega-se a primeira proposição ($\neg P$).
    
2. Nega-se a segunda proposição ($\neg Q$).
    
3. **Troca-se o "OU" ($\lor$) pelo "E" ($\land$)**.
    

$$\neg (P \lor Q) \equiv \neg P \land \neg Q$$

> **Regra prática:** _"Nega tudo e troca o OU pelo E."_

- **Exemplo Simples:**
    
    - **Proposição ($P \lor Q$):** "João é fiscal **OU** Maria é perita."
        
    - **Negação ($\neg P \land \neg Q$):** "João **não** é fiscal **E** Maria **não** é perita."
        

#### 2. ARMADILHAS CLÁSSICAS DO CEBRASPE

##### **A) A Pegadinha da "Negação Parcial"**

O CEBRASPE troca o conectivo (de "E" para "OU"), mas **esquece de negar uma das partes** ou nega apenas o verbo principal da frase.

- _Enunciado:_ A negação de "O relatório foi lido e aprovado" é "O relatório não foi lido ou foi aprovado".
    
- _Análise:_ **ERRADO.** Faltou negar a segunda parte ("não foi aprovado").
    

##### **B) A Pegadinha de Manter o Conectivo Original**

A banca nega ambas as proposições simples, mas **mantém o mesmo conectivo** (nega "E" usando "E", ou nega "OU" usando "OU").

- _Enunciado:_ A negação de "Paulo estuda ou trabalha" é "Paulo não estuda e não trabalha".
    
- _Análise:_ **CERTO.** A banca negou ambas e trocou "OU" por "E". (Se mantivesse "ou", estaria errado).
    

##### **C) Atentar para a Negação de Verbos Negativos**

Quando uma das proposições simples já contém uma negação (ex: "não"), a negação da negação torna a proposição **afirmativa** ($\neg(\neg P) \equiv P$).

- _Proposição:_ "O candidato não foi aprovado e a prova foi anulada."
    
- _Negação:_ "O candidato foi aprovado **OU** a prova **não** foi anulada."
    

#### 3. TABELA DE EQUIVALÊNCIAS DAS LEIS DE DE MORGAN

|**Proposição Original**|**Conectivo Principal**|**Negação Válida (Lei de Morgan)**|**Mudança do Conectivo**|
|---|---|---|---|
|$P \land Q$ ("P e Q")|Conjunção ($\land$)|$\neg P \lor \neg Q$ ("não P ou não Q")|**E** vira **OU**|
|$P \lor Q$ ("P ou Q")|Disjunção ($\lor$)|$\neg P \land \neg Q$ ("não P e não Q")|**OU** vira **E**|

#### 4. MODELOS DE QUESTÕES NO ESTILO CEBRASPE ("CERTO OU ERRADO")

##### **Modelo 1: Negação da Conjunção ("E")**

- **Item:** A negação da proposição _"O servidor protocolou o documento e enviou o e-mail"_ é expressa corretamente por _"O servidor não protocolou o documento ou não enviou o e-mail"_.
    
- **Análise:**
    
    - Proposição original: $P \land Q$
        
    - Aplicação da 1ª Lei de De Morgan: $\neg P \lor \neg Q$
        
    - A frase nega $P$ ("não protocolou"), troca "E" por "OU", e nega $Q$ ("não enviou").
        
- **Gabarito:** **CERTO.**
    

##### **Modelo 2: Pegadinha com Conectivo Incorreto**

- **Item:** A negação lógica da afirmação _"O candidato domina a matéria ou possui experiência prévia"_ é _"O candidato não domina a matéria ou não possui experiência prévia"_.
    
- **Análise:**
    
    - Proposição original: $P \lor Q$
        
    - Aplicação da 2ª Lei de De Morgan: $\neg P \land \neg Q$
        
    - O item manteve o conectivo "OU" em vez de trocar por "E".
        
- **Gabarito:** **ERRADO.** (O correto seria _"O candidato não domina a matéria **E** não possui experiência prévia"_).
    

##### **Modelo 3: Negação de Proposição com Termos Negativos**

- **Item:** A negação da sentença _"A senha não expirou e o acesso foi liberado"_ é equivalente a _"A senha expirou ou o acesso não foi liberado"_.
    
- **Análise:**
    
    - Proposição original: $\neg P \land Q$
        
    - Aplicação de De Morgan: $\neg(\neg P) \lor \neg Q \equiv P \lor \neg Q$
        
    - A negação de "não expirou" é "expirou", o conectivo "E" muda para "OU", e a negação de "foi liberado" é "não foi liberado".
        
- **Gabarito:** **CERTO.**