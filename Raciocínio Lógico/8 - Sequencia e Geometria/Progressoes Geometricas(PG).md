### 📚 GUIA DE ESTUDOS: PROGRESSÕES GEOMÉTRICAS (PG) — BANCA CEBRASPE

### 1. CONCEITO E ESTRUTURA DE UMA PG

Uma **Progressão Geométrica (PG)** é uma sequência numérica na qual cada termo, a partir do segundo, é igual ao termo anterior multiplicado por uma constante chamada **razão ($q$)**.

$$\text{PG: } (a_1, a_2, a_3, \dots, a_n, \dots)$$

- **Cálculo da Razão ($q$):**
    
    $$q = \frac{a_n}{a_{n-1}} \quad (\text{divisão de qualquer termo pelo seu antecedente})$$
    
- **Classificação em Função da Razão ($q$) e do Termo Inicial ($a_1$):**
    
    - **Crescente:** $a_1 > 0$ e $q > 1$ (ex: $2, 6, 18, \dots$) ou $a_1 < 0$ e $0 < q < 1$.
        
    - **Decrescente:** $a_1 > 0$ e $0 < q < 1$ (ex: $100, 50, 25, \dots$) ou $a_1 < 0$ e $q > 1$.
        
    - **Constante:** $q = 1$ (ex: $5, 5, 5, \dots$).
        
    - **Alternada (ou Oscilante):** $q < 0$, fazendo os sinais dos termos se alternarem entre positivo e negativo (ex: $3, -6, 12, -24, \dots$).
        

### 2. FERRAMENTAS MATEMÁTICAS ESSENCIAIS

#### 2.1. Termo Geral da PG

Para calcular qualquer termo $a_n$ conhecendo o primeiro termo $a_1$ e a razão $q$:

$$a_n = a_1 \cdot q^{n - 1}$$

- **Estratégia Avançada do Professor:**
    
    Você não precisa depender do $a_1$. Para relacionar dois termos genéricos $a_k$ e $a_n$, utilize:
    
    $$a_n = a_k \cdot q^{n - k}$$
    
    - _Exemplo:_ $a_{8} = a_3 \cdot q^5$. Se você possui $a_3$ e $a_8$, descobre a razão $q$ sem precisar encontrar $a_1$.
        

#### 2.2. Soma dos $n$ Primeiros Termos (PG Finita)

Quando precisamos somar um número finito $n$ de termos de uma PG ($q \neq 1$):

$$S_n = \frac{a_1(q^n - 1)}{q - 1}$$

#### 2.3. Soma de uma PG Infinita Convergente

Quando a sequência é infinita e a razão está estritamente entre $-1$ e $1$ (ou seja, $-1 < q < 1$ ou $\vert{}q\vert{} < 1$), os termos vão se aproximando de zero. A soma de todos esses infinitos termos converge para um valor fixo:

$$S_\infty = \frac{a_1}{1 - q}$$

- **Foco CEBRASPE:** Questões com processos infinitos (divisões sucessivas de áreas, frações que reduzem pela metade a cada etapa ou dízimas periódicas) são resolvidas com esta fórmula.
    

#### 2.4. Propriedade do Termo Médio

Em três termos consecutivos $(a, b, c)$ de uma PG de termos positivos, o termo central é a **média geométrica** dos vizinhos:

$$b^2 = a \cdot c \implies b = \sqrt{a \cdot c}$$

### 📊 RESUMO OPERACIONAL DE FÓRMULAS DE PG

|**Conceito**|**Fórmula / Relação**|**Aplicação Prática**|
|---|---|---|
|**Razão ($q$)**|$q = \frac{a_2}{a_1}$|Determinar a taxa multiplicativa de crescimento ou redução.|
|**Termo Geral**|$a_n = a_1 \cdot q^{n - 1}$|Calcular valores futuros, contágios ou termos distantes.|
|**Relação entre Termos**|$a_n = a_k \cdot q^{n - k}$|Acelerar o cálculo da razão $q$ sem precisar de $a_1$.|
|**Soma Finita ($S_n$)**|$S_n = \frac{a_1(q^n - 1)}{q - 1}$|Obter o total acumulado em períodos finitos.|
|**Soma Infinita ($S_\infty$)**|$S_\infty = \frac{a_1}{1 - q} \quad (-1 < q < 1)$|Processos de divisão contínua ou somas infinitas de frações.|
|**Média Geométrica**|$b = \sqrt{a \cdot c}$|Resolver problemas envolvendo 3 termos consecutivos.|

### 💡 DICAS E ESTRATÉGIAS DE PROVA (ESTILO CEBRASPE)

1. **Relação entre PG e Porcentagem/Fatores Multiplicativos:**
    
    - O CEBRASPE costuma mascarar PGs como aumentos ou descontos percentuais sucessivos.
        
    - Se um valor aumenta $10\%$ a cada período, a razão da PG é $q = 1 + 0,10 = 1,10$.
        
    - Se um valor desvaloriza $20\%$ ao ano, a razão é $q = 1 - 0,20 = 0,80$.
        
2. **Diferença de Comportamento: PA (Linear) vs. PG (Exponencial):**
    
    - **PA:** Crescimento/decrescimento por **soma constante** (comportamento de Função Afim / 1º Grau).
        
    - **PG:** Crescimento/decrescimento por **multiplicação constante** (comportamento de Função Exponencial).
        
3. **Estratégia do "Exemplo Concreto":**
    
    - Em itens teóricos de _Certo/Errado_ sobre propriedades de PG (ex: _"Dada uma PG com razão $q > 1$, o quadrado de qualquer termo é..."_), atribua números simples (como $a_1 = 2$ e $q = 2$) para testar o item rapidamente antes de tentar provar algebricamente.
        
4. **Geratriz de Dízima Periódica via PG Infinita:**
    
    - Uma dízima periódica simples como $0,333\dots$ pode ser vista como a soma infinita $\frac{3}{10} + \frac{3}{100} + \frac{3}{1000} + \dots$, em que $a_1 = \frac{3}{10}$ e $q = \frac{1}{10}$. Aplicando $S_\infty = \frac{a_1}{1 - q}$, obtém-se a fração geratriz $\frac{1}{3}$.