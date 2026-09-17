#algebraeFuncoes
# 📚 GUIA DE ESTUDOS: EQUAÇÕES E INEQUAÇÕES DE 1º E 2º GRAUS E FUNÇÕES

## 1. Equações e Inequações do 1º Grau

Uma equação ou inequação do 1º grau trata de relações de proporcionalidade e equivalência direta entre incógnitas (variáveis) de expoente $1$.

### 1.1. Equação do 1º Grau

- **Forma Geral:** $ax + b = 0$, com $a \neq 0$.
    
- **A Lógica da Balança:** Uma igualdade funciona como uma balança em equilíbrio. Qualquer operação aritmética (soma, subtração, multiplicação, divisão) feita de um lado da igualdade **deve** ser feita do outro lado.
    
- **Isolando a Incógnita:**
    
    1. Agrupe os termos com $x$ de um lado e os termos constantes (números) do outro.
        
    2. Simplifique os termos semelhantes.
        
    3. $x = -\frac{b}{a}$.
        

> **Exemplo Prático:**
> 
> $$3x - 12 = 0 \implies 3x = 12 \implies x = \frac{12}{3} \implies x = 4$$

### 1.2. Inequações do 1º Grau

- **Forma Geral:** $ax + b > 0$, $ax + b \ge 0$, $ax + b < 0$ ou $ax + b \le 0$.
    
- **Cuidado com a Pegadinha do Sinal (A Regra do $-1$):**
    
    Ao multiplicar ou dividir uma inequação por um número negativo, a **orientação do sinal de desigualdade se inverte**.
    
    - _Por que isso acontece?_ Pense na reta numérica: $3 > 2$. Se multiplicarmos por $-1$, temos $-3$ e $-2$. O número $-2$ está mais próximo de zero, logo é maior que $-3$ (portanto, $-3 < -2$).
        
- **Exemplo Prático:**
    
    $$-2x + 6 > 0 \implies -2x > -6 \quad (\text{multiplica por } -1)$$
    
    $$2x < 6 \implies x < 3$$
    

## 2. Equações e Inequações do 2º Grau

As equações e inequações do 2º grau descrevem comportamentos nos quais o crescimento ou decrescimento de uma grandeza ocorre de forma acelerada ou parabólica (variável com expoente $2$).

### 2.1. Equação do 2º Grau

- **Forma Geral:** $ax^2 + bx + c = 0$, com $a \neq 0$.
    
- **Fórmula de Bhaskara & Discriminante ($\Delta$):**
    
    $$\Delta = b^2 - 4ac$$
    
    $$x = \frac{-b \pm \sqrt{\Delta}}{2a}$$
    
- **Comportamento das Raízes segundo o $\Delta$:**
    
    - $\Delta > 0$: Possui **duas raízes reais e distintas** ($x_1 \neq x_2$).
        
    - $\Delta = 0$: Possui **duas raízes reais e iguais** ($x_1 = x_2$).
        
    - $\Delta < 0$: **Não possui raízes reais** em $\mathbb{R}$.
        
- **Relações de Girard (Soma e Produto):**
    
    Muitas vezes, em provas de raciocínio lógico, você ganha tempo encontrando as raízes mentalmente:
    
    - **Soma ($S$):** $x_1 + x_2 = -\frac{b}{a}$
        
    - **Produto ($P$):** $x_1 \cdot x_2 = \frac{c}{a}$
        

### 2.2. Inequações do 2º Grau e Estudo do Sinal

Para resolver uma inequação do 2º grau (ex: $ax^2 + bx + c > 0$), siga esta lógica:

1. Encontre as raízes da equação correspondente ($ax^2 + bx + c = 0$).
    
2. Faça o esboço da parábola baseando-se no sinal do coeficiente $a$:
    
    - $a > 0$: Parábola com **concavidade para cima** $\left(\bigcup\right)$.
        
    - $a < 0$: Parábola com **concavidade para baixo** $\left(\bigcap\right)$.
        
3. Analise as regiões positivas (acima do eixo $x$) e negativas (abaixo do eixo $x$).
    

> **Exemplo Prático:** $x^2 - 5x + 6 \le 0$
> 
> - Raízes (via Soma/Produto): $S = 5, P = 6 \implies x_1 = 2, x_2 = 3$.
>     
> - Como $a = 1 > 0$, a parábola sorri $\left(\bigcup\right)$.
>     
> - O trecho negativo ($\le 0$) fica **entre** as raízes.
>     
> - **Conjunto Solução:** $S = \{x \in \mathbb{R} \mid 2 \le x \le 3\}$ ou $[2, 3]$.
>     

## 3. Funções e Gráficos

Uma **função** é uma regra matemática que associa cada elemento de um conjunto de entrada (Domínio - $x$) a um único elemento de um conjunto de saída (Contradomínio/Imagem - $y$ ou $f(x)$).

### 3.1. Função Afim (1º Grau)

- **Lei de Formação:** $f(x) = ax + b$
    
- **Coeficiente Aumentativo/Inclinado ($a$ - Taxa de Variação):**
    
    - $a > 0$: Função **Crescente**.
        
    - $a < 0$: Função **Decrescente**.
        
- **Coeficiente Linear ($b$ - Ponto Inicial):** É o ponto exato onde a reta corta o eixo $y$ (onde $x = 0$).
    
- **Gráfico:** Sempre uma **reta**.
    
- **Zero/Raiz da Função:** O ponto onde a reta corta o eixo $x$ ($f(x) = 0 \implies x = -\frac{b}{a}$).
    

### 3.2. Função Quadrática (2º Grau)

- **Lei de Formação:** $f(x) = ax^2 + bx + c$
    
- **Gráfico:** Uma **parábola**.
    
- **Ponto de Interseção com o Eixo $y$:** $(0, c)$.
    
- **Vértice da Parábola $V(x_v, y_v)$:** O ponto de máximo ou de mínimo da função.
    
    - $x_v = -\frac{b}{2a}$ (ponto do eixo $x$ onde ocorre o valor máximo/mínimo).
        
    - $y_v = -\frac{\Delta}{4a}$ (o valor máximo ou mínimo da função no eixo $y$).
        

```
        a > 0 (Mínimo)                   a < 0 (Máximo)
             \   /                            ___
              \ /                            /   \
               V  <-- Vértice (Mínimo)      V     V <-- Vértice (Máximo)
```

## 📊 Quadro Comparativo Sintético

|**Conceito**|**1º Grau / Afim**|**2º Grau / Quadrática**|
|---|---|---|
|**Forma Padrão**|$ax + b = 0$ / $f(x) = ax + b$|$ax^2 + bx + c = 0$ / $f(x) = ax^2 + bx + c$|
|**Gráfico**|Reta contínua|Parábola|
|**Número de Raízes**|No máximo 1 raiz real|Ates de 2 raízes reais (depende do $\Delta$)|
|**Ponto Crítico**|Não possui (crescimento/decrescimento constante)|Vértice $V(x_v, y_v)$ (Ponto de Máximo ou Mínimo)|
|**Método Principal**|Isolamento da variável|Fórmula de Bhaskara ou Soma/Produto|

## 💡 Dicas de Professor para Provas de Raciocínio Lógico

1. **Problemas de "Ponto de Encontro" ou "Lucro Máximo":**
    
    - Se a questão pede para comparar dois planos/serviços e saber a partir de quando um compensa mais que o outro, monte uma **inequação do 1º grau** ou iguale as **funções do 1º grau**.
        
    - Se a questão pede "valor máximo", "lucro máximo" ou "custo mínimo", você está lidando com o **vértice da função quadrática**:
        
        - Pediu a **quantidade** para o máximo/mínimo? Calcule o $x_v = -\frac{b}{2a}$.
            
        - Pediu o **valor** máximo/mínimo obtido? Calcule o $y_v = -\frac{\Delta}{4a}$.
            
2. **Atenção aos Conjuntos de Validade:** Lembre-se sempre das restrições de domínio reais: não existe divisão por zero e nem raiz quadrada real de número negativo.