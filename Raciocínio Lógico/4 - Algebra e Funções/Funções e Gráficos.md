#algebraeFuncoes

Olá! Seja muito bem-vindo a este módulo de estudos dedicado exclusivamente ao tópico **Funções e Gráficos** no Raciocínio Lógico-Matemático.

Como seu professor, foquei este guia na compreensão conceitual e na interpretação gráfica do comportamento das funções (1º e 2º Grau), essenciais para resolver questões de provas com agilidade.

# 📚 GUIA DE ESTUDOS: FUNÇÕES E GRÁFICOS (1º E 2º GRAU)

## 1. O Conceito Fundamental de Função

Uma **função** $f$ é uma relação de dependência entre duas variáveis, $x$ (variável independente) e $y$ (variável dependente), escrita na forma $y = f(x)$.

- **Domínio ($x$):** O conjunto dos valores de entrada (o "causa").
    
- **Imagem ($y$ ou $f(x)$):** O conjunto dos valores de saída gerados (o "efeito").
    

## 2. Função Afim (1º Grau) e seu Gráfico

A Função do 1º grau descreve fenômenos de **crescimento ou decrescimento constante** (taxa de variação fixa).

### 2.1. Lei de Formação

$$f(x) = ax + b \quad \text{com } a \neq 0$$

- **$a$ (Coeficiente Angular / Taxa de Variação):** Mede a inclinação da reta.
    
    - Se $a > 0$: A função é **crescente** (à medida que $x$ aumenta, $y$ aumenta).
        
    - Se $a < 0$: A função é **decrescente** (à medida que $x$ aumenta, $y$ diminui).
        
- **$b$ (Coeficiente Linear / Termo Independente):** É o ponto inicial onde a reta **intersecta o eixo $y$** (ou seja, quando $x = 0$, $y = b$).
    

### 2.2. O Gráfico da Função Afim

O gráfico de qualquer função do 1º grau é sempre uma **reta contínua**.

- **Ponto no Eixo $y$:** Ocorre em $(0, b)$.
    
- **Zero ou Raiz da Função (Ponto no Eixo $x$):** É o valor de $x$ que torna $f(x) = 0$.
    
    $$ax + b = 0 \implies x = -\frac{b}{a}$$
    
    O gráfico intersecta o eixo $x$ no ponto $\left(-\frac{b}{a}, 0\right)$.
    

```
   a > 0 (Crescente)              a < 0 (Decrescente)
        y                              y
        |   /                          | \
        |  /                           |  \
   (0,b)| /                       (0,b)|   \
--------+------------ x        --------+------------ x
  (-b/a)|                        (-b/a)|
        |                              |
```

## 3. Função Quadrática (2º Grau) e seu Gráfico

A Função do 2º grau descreve comportamentos em que a variação acelera, forma trajetórias parabólicas ou envolve pontos de **máximo** e **mínimo** (como lucro máximo ou custo mínimo).

### 3.1. Lei de Formação

$$f(x) = ax^2 + bx + c \quad \text{com } a \neq 0$$

- **$a$ (Coeficiente Principal):** Define a **concavidade** da parábola:
    
    - Se $a > 0$: Concavidade voltada para **cima** $\left(\bigcup\right)$ $\rightarrow$ a função possui um ponto de **mínimo**.
        
    - Se $a < 0$: Concavidade voltada para **baixo** $\left(\bigcap\right)$ $\rightarrow$ a função possui um ponto de **máximo**.
        
- **$c$ (Termo Independente):** É o ponto onde a parábola **corta o eixo $y$**, no ponto $(0, c)$.
    

### 3.2. O Gráfico e as Raízes (Eixo $x$)

O gráfico da função do 2º grau é uma **parábola**. O número de vezes que ela intersecta o eixo $x$ depende do discriminante $\Delta = b^2 - 4ac$:

- $\Delta > 0$: A parábola corta o eixo $x$ em **dois pontos distintos** ($x_1$ e $x_2$).
    
- $\Delta = 0$: A parábola apenas **tangencia** o eixo $x$ em um único ponto ($x_1 = x_2$).
    
- $\Delta < 0$: A parábola **não corta** o eixo $x$ (não existem raízes reais).
    

### 3.3. O Vértice da Parábola $V(x_v, y_v)$

O vértice é o ponto mais importante no estudo gráfico da função do 2º grau, pois representa o **ponto de virada** (máximo ou mínimo).

- **$x_v$ (Eixo x do Vértice):** Indica a **posição / quantidade** na qual ocorre o valor máximo ou mínimo.
    
    $$x_v = -\frac{b}{2a}$$
    
- **$y_v$ (Eixo y do Vértice):** Indica o **valor** do resultado máximo ou mínimo atingido pela função.
    
    $$y_v = -\frac{\Delta}{4a}$$
    

```
        a > 0 (Possui Mínimo)            a < 0 (Possui Máximo)
             \   /                            ___
              \ /                            /   \
               V  <-- Vértice (Mínimo)      V     V <-- Vértice (Máximo)
```

## 📊 Quadro Comparativo Gráfico

|**Característica**|**Função do 1º Grau (Afim)**|**Função do 2º Grau (Quadrática)**|
|---|---|---|
|**Formato Gráfico**|Reta|Parábola|
|**Interseção no eixo $y$**|Ponto $(0, b)$|Ponto $(0, c)$|
|**Interseção no eixo $x$**|Ponto da raiz: $x = -\frac{b}{a}$|Ates de 2 pontos (depende do $\Delta$)|
|**Comportamento**|Sempre crescente ou sempre decrescente|Muda de direção no Vértice $V$|
|**Ponto Extremo**|Não possui|Possui ponto de Máximo ($a<0$) ou Mínimo ($a>0$)|

## 💡 Dicas do Professor para Interpretação de Questões em Provas

1. **Como diferenciar o $x_v$ do $y_v$ em um problema de otimização?**
    
    - Se a questão pergunta _"Qual a **quantidade** de produtos para obter o lucro máximo?"_: encontre o **$x_v$**.
        
    - Se a questão pergunta _"Qual é o **lucro máximo** obtido?"_: encontre o **$y_v$** (ou calcule $f(x_v)$).
        
2. **Aproximação por substituição simples:**
    
    - Para testar se um gráfico corresponde a uma função dada, substitua $x = 0$ na função. O valor de $y$ encontrado **deve** coincidir com o ponto onde o gráfico corta o eixo $y$.