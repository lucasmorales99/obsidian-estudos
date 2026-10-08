Olá, futuro(a) servidor(a)! Seja muito bem-vindo(a) a esta aula focada no subitem **11.2 do edital: Tabelas-verdade**, dentro da **Lógica Sentencial (ou Proposicional)**, preparada sob medida para a banca **CEBRASPE**.

Nas provas do CEBRASPE no formato **"Certo ou Errado"**, o conhecimento de tabelas-verdade é testado na determinação do **valor lógico de proposições compostas** (Verdadeiro ou Falso), no cálculo do **número de linhas de uma tabela** ($2^n$), e na identificação de **Tautologias, Contradições e Contingências**.

### 📚 GUIA DE LÓGICA PROPOSICIONAL: TABELAS-VERDADE (FOCO CEBRASPE)

Uma **tabela-verdade** é um dispositivo gráfico utilizado em Lógica Proposicional para determinar o valor lógico de uma proposição composta com base nos valores de suas proposições simples componentes.

#### 1. NÚMERO DE LINHAS DE UMA TABELA-VERDADE

O número de linhas de uma tabela-verdade depende exclusivamente do número de proposições simples distintas ($n$) que compõem a proposição.

$$\text{Número de linhas} = 2^n$$

- $n = 1 \implies 2^1 = 2$ linhas
    
- $n = 2 \implies 2^2 = 4$ linhas
    
- $n = 3 \implies 2^3 = 8$ linhas
    
- $n = 4 \implies 2^4 = 16$ linhas
    

> **Pegadinha da Banca:** A repetição de uma proposição simples não altera $n$. Em $P \land (Q \rightarrow P)$, temos apenas duas proposições distintas ($P$ e $Q$), resultando em $2^2 = 4$ linhas.

#### 2. TABELA-VERDADE DOS CONECTIVOS LÓGICOS ESSENCIAIS

Para gabaritar qualquer questão de tabela-verdade do CEBRASPE, você precisa ter decoradas as regras fundamentais de cada conectivo:

|**Conectivo**|**Nome**|**Símbolo**|**Regra de Ouro (Mnemônico)**|
|---|---|---|---|
|**E**|Conjunção|$\land$|Só é **V** se **AMBAS** forem **V**.|
|**OU**|Disjunção Inclusiva|$\lor$|Só é **F** se **AMBAS** forem **F**.|
|**OU... OU**|Disjunção Exclusiva|$\underline{\lor}$|Só é **V** se os valores forem **DIFERENTES**.|
|**SE... ENTÃO**|Condicional|$\rightarrow$|Só é **F** no caso **V $\rightarrow$ F** ("Vera Fischer").|
|**SE E SOMENTE SE**|Bicondicional|$\leftrightarrow$|Só é **V** se os valores forem **IGUAIS**.|

##### Tabela-Verdade Resumida:

|**P**|**Q**|**Conjunção (P∧Q)**|**Disjunção (P∨Q)**|**Disj. Exclusiva (P∨​Q)**|**Condicional (P→Q)**|**Bicondicional (P↔Q)**|
|---|---|---|---|---|---|---|
|**V**|**V**|**V**|**V**|**F**|**V**|**V**|
|**V**|**F**|**F**|**V**|**V**|**F**|**F**|
|**F**|**V**|**F**|**V**|**V**|**V**|**F**|
|**F**|**F**|**F**|**F**|**F**|**V**|**V**|

#### 3. CLASSIFICAÇÃO DAS PROPOSIÇÕES COMPOSTAS

Após construir ou analisar a última coluna de uma tabela-verdade, a estrutura é classificada como:

1. **Tautologia:** Quando o valor lógico da proposição composta é **sempre Verdadeiro (V)**, independentemente dos valores lógicos das proposições simples.
    
    - _Exemplo clássico:_ $P \lor \neg P$ ("Hoje é segunda-feira OU hoje não é segunda-feira").
        
2. **Contradição:** Quando o valor lógico da proposição composta é **sempre Falso (F)**, independentemente dos valores das proposições simples.
    
    - _Exemplo clássico:_ $P \land \neg P$ ("Hoje é segunda-feira E hoje não é segunda-feira").
        
3. **Contingência:** Quando a coluna final apresenta **pelo menos um V e pelo menos um F** (não é nem tautologia nem contradição).
    

#### 4. ARMADILHAS CLÁSSICAS DO CEBRASPE

##### **A) A Falsa Ideia de Construir Toda a Tabela**

Em provas com restrição de tempo, a banca costuma pedir se uma proposição complexa é V ou F para uma atribuição específica. **Não monte a tabela inteira!** Apenas substitua os valores fornecidos diretamente na estrutura.

##### **B) A Condicional com Antecedente Falso**

Lembre-se: em uma proposição condicional $P \rightarrow Q$, se o antecedente ($P$) for **Falso**, a condicional será **Verdadeira**, independentemente do valor de $Q$ ($F \rightarrow V$ é **V** e $F \rightarrow F$ é **V**).

##### **C) Contagem de Linhas em Enunciados Extensos**

O CEBRASPE gosta de apresentar proposições compostas expressas em linguagem natural com várias frases simples para o candidato contar quantas linhas tem a tabela-verdade.

- **Exemplo:** _"A tabela-verdade da proposição 'Se o auditor examinou o relatório e a equipe validou os dados, então a transferência foi liberada ou o processo foi arquivado' possui 16 linhas."_
    
- **Análise:** $n = 4$ proposições simples distintas $\implies 2^4 = 16$ linhas. **CERTO.**
    

#### 5. MODELOS DE QUESTÕES NO ESTILO CEBRASPE ("CERTO OU ERRADO")

##### **Modelo 1: Número de Linhas**

- **Item:** A quantidade de linhas da tabela-verdade correspondente à proposição composta $(P \land Q) \rightarrow (R \lor P)$ é igual a 8.
    
- **Análise:**
    
    - Identificação das proposições simples distintas: $P$, $Q$ e $R$ (3 proposições).
        
    - $2^3 = 8$ linhas.
        
- **Gabarito:** **CERTO.**
    

##### **Modelo 2: Valoração Lógica Direta**

- **Item:** Se a proposição $P$ for Verdadeira e a proposição $Q$ for Falsa, então o valor lógico da proposição $(P \rightarrow Q) \leftrightarrow (\neg P \lor Q)$ é Verdadeiro.
    
- **Análise:**
    
    - Substituindo os valores: $P = \text{V}$ e $Q = \text{F}$.
        
    - Lado esquerdo: $P \rightarrow Q \implies \text{V} \rightarrow \text{F} = \mathbf{F}$.
        
    - Lado direito: $\neg P \lor Q \implies \text{F} \lor \text{F} = \mathbf{F}$.
        
    - Proposição central (Bicondicional): $\text{F} \leftrightarrow \text{F} = \mathbf{V}$.
        
- **Gabarito:** **CERTO.**
    

##### **Modelo 3: Identificação de Tautologia**

- **Item:** A proposição $(P \land Q) \rightarrow P$ é uma tautologia.
    
- **Análise:**
    
    - Para uma condicional ser Falsa, teríamos que ter o caso $\text{V} \rightarrow \text{F}$.
        
    - Para o antecedente $(P \land Q)$ ser Verdadeiro, $P$ e $Q$ precisam ser ambos Verdadeiros ($P = \text{V}$).
        
    - Mas se $P = \text{V}$, o consequente $P$ é Verdadeiro, tornando a condicional $\text{V} \rightarrow \text{V} = \text{V}$.
        
    - Como é impossível obter resultado Falso, a proposição é **sempre Verdadeira** (Tautologia).
        
- **Gabarito:** **CERTO.**