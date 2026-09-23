### 📚 GUIA DE ESTUDOS: PROGRESSÕES ARITMÉTICAS (PA) — BANCA CEBRASPE

### 1. CONCEITO E ESTRUTURA DE UMA PA

Uma Progressão Aritmética é uma sequência numérica em que cada termo, a partir do segundo, é obtido somando-se ao termo anterior uma constante chamada **razão** ($r$).

$$\text{PA: } (a_1, a_2, a_3, \dots, a_n, \dots)$$

- **Cálculo da Razão ($r$):**
    
    $$r = a_n - a_{n-1} \quad (\text{diferença entre qualquer termo e seu antecedente})$$
    
- **Classificação quanto à razão:**
    
    - **Crescente:** $r > 0$
        
    - **Decrescente:** $r < 0$
        
    - **Constante (ou Estacionária):** $r = 0$
        

### 2. FERRAMENTAS MATEMÁTICAS ESSENCIAIS

#### 2.1. Termo Geral da PA

A fórmula clássica permite encontrar qualquer termo $a_n$ a partir do primeiro termo $a_1$:

$$a_n = a_1 + (n - 1) \cdot r$$

- **Visão Prática do Professor (Avançada):**
    
    Não fique preso apenas ao $a_1$. É muito comum precisar relacionar dois termos genéricos $a_k$ e $a_n$. Use a relação direta:
    
    $$a_n = a_k + (n - k) \cdot r$$
    
    - _Exemplo:_ $a_{15} = a_5 + 10r$. Se você tem $a_5$ e $a_{15}$, encontra a razão $r$ em segundos sem precisar calcular $a_1$.
        

#### 2.2. Soma dos $n$ Primeiros Termos ($S_n$)

Para calcular a soma de todos os termos de uma PA finita:

$$S_n = \frac{(a_1 + a_n) \cdot n}{2}$$

- **Dica de Interpretação:** A soma nada mais é do que a média aritmética entre o primeiro e o último termo multiplicada pela quantidade de termos ($n$).
    

#### 2.3. Propriedades Estratégicas

1. **Média Aritmética do Termo Central:** Em três termos consecutivos $(a, b, c)$ de uma PA, o termo do meio é a média aritmética dos outros dois:
    
    $$b = \frac{a + c}{2}$$
    
2. **Termos Equidistantes dos Extremos:** Em uma PA finita, a soma de dois termos equidistantes dos extremos é constante e igual à soma dos próprios extremos ($a_1 + a_n = a_2 + a_{n-1} = \dots$).
    

### 📊 RESUMO OPERACIONAL DE FÓRMULAS

|**Conceito**|**Fórmula / Relação**|**Aplicação Típica**|
|---|---|---|
|**Razão ($r$)**|$r = a_2 - a_1$|Identificar o padrão de crescimento/decrescimento.|
|**Termo Geral**|$a_n = a_1 + (n - 1) \cdot r$|Encontrar a posição $n$ ou a quantidade de elementos.|
|**Relação entre Termos**|$a_n = a_k + (n - k) \cdot r$|Acelerar contas quando $a_1$ não for fornecido.|
|**Soma da PA ($S_n$)**|$S_n = \frac{(a_1 + a_n) \cdot n}{2}$|Determinar acumulados (total investido, total produzido).|
|**Termo Médio**|$b = \frac{a + c}{2}$|Resolver problemas com 3 termos desconhecidos.|

### 💡 DICAS E ESTRATÉGIAS DE PROVA (ESTILO CEBRASPE)

1. **Notação Prática para 3 Termos Desconhecidos em PA:**
    
    Se uma questão enunciar que _"três números em PA somam X"_, evite escrever $(a_1, a_1 + r, a_1 + 2r)$. Escreva os três termos como:
    
    $$(x - r, \; x, \; x + r)$$
    
    Ao somá-los, o $+r$ e o $-r$ se anulam: $(x - r) + x + (x + r) = 3x$. Isso permite achar o termo central $x$ imediatamente!
    
2. **Interpretação da PA como Função do 1º Grau:** O CEBRASPE adora misturar PA com **Funções Afins**. Lembre-se: o termo geral $a_n = a_1 + (n - 1)r$ pode ser reescrito como:
    
    $$a(n) = r \cdot n + (a_1 - r)$$
    
    Ou seja, o comportamento de uma PA é estritamente **linear**, onde a razão $r$ faz o papel do coeficiente angular (taxa de variação).
    
3. **Estratégia do "Caso Concreto" para Julgamento de Itens:**
    
    Em itens conceituais do tipo _"Para qualquer PA em que $r > 2$, a soma dos 10 primeiros termos será par"_, crie um exemplo numérico simples (ex: $a_1 = 1$, $r = 3$) para testar a afirmativa rapidamente. Se o exemplo furar a afirmação, você desmente o item sem precisar de provas algébricas longas.
    
4. **Atenção ao Valor de $n$ (A Armadilha da Contagem):**
    
    Ao calcular prazos ou parcelas (ex: _"do início de março até o fim de dezembro"_), conte com atenção o número exato de termos $n$. Errar o número de períodos por 1 unidade ($n-1$ em vez de $n$) é a causa de erro em grande parte dos itens de PA do CEBRASPE.