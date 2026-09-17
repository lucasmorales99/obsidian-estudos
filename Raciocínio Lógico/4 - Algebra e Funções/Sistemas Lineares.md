#algebraeFuncoes

Olá! Seja muito bem-vindo a esta aula focada exclusivamente em **Sistemas Lineares** para Raciocínio Lógico-Matemático.

Como professor, montei este guia para ajudá-lo a dominar desde a montagem das equações até a interpretação geométrica dos resultados e os métodos de resolução mais céleres em provas.

# 📚 GUIA DE ESTUDOS: SISTEMAS LINEARES

## 1. O Conceito Fundamental

Um **Sistema Linear** é um conjunto de duas ou mais equações do 1º grau que possuem as mesmas variáveis (incógnitas). Resolver um sistema significa encontrar valores para essas variáveis que **satisfaçam todas as equações ao mesmo tempo**.

A forma padrão de um sistema $2 \times 2$ (duas equações e duas incógnitas) é:

$$\begin{cases} a_1 x + b_1 y = c_1 \\ a_2 x + b_2 y = c_2 \end{cases}$$

## 2. Classificação Lógica e Interpretação Geométrica

Em Raciocínio Lógico, classificar um sistema é analisar a quantidade de soluções que ele pode ter. Graficamente, cada equação de 1º grau representa uma **reta**.
![[Pasted image 20260916202502.png]]

- **Sistema Possível e Determinado (SPD):**
    
    - **Soluções:** Possui **uma única solução** $(x, y)$.
        
    - **Visão Geométrica:** As retas são **concorrentes** (se cruzam em um único ponto).
        
    - **Condição:** $\frac{a_1}{a_2} \neq \frac{b_1}{b_2}$
        
- **Sistema Possível e Indeterminado (SPI):**
    
    - **Soluções:** Possui **infinitas soluções**.
        
    - **Visão Geométrica:** As retas são **coincidentes** (uma está sobre a outra).
        
    - **Condição:** $\frac{a_1}{a_2} = \frac{b_1}{b_2} = \frac{c_1}{c_2}$
        
- **Sistema Impossível (SI):**
    
    - **Soluções:** **Não possui nenhuma solução**.
        
    - **Visão Geométrica:** As retas são **paralelas** (nunca se cruzam).
        
    - **Condição:** $\frac{a_1}{a_2} = \frac{b_1}{b_2} \neq \frac{c_1}{c_2}$
        

## 3. Métodos Práticos de Resolução

### 3.1. Método da Adição (O mais rápido)

Consiste em somar as duas equações membro a membro para eliminar uma das incógnitas.

1. Multiplique uma (ou ambas) as equações por um número para que os coeficientes de uma das variáveis sejam opostos (ex: $2y$ e $-2y$).
    
2. Some as equações e resolva para a variável restante.
    

> **Exemplo:**
> 
> $$\begin{cases} x + y = 10 \\ x - y = 4 \end{cases}$$
> 
> Somando as duas equações: $(x + x) + (y - y) = 10 + 4 \implies 2x = 14 \implies x = 7$.
> 
> Substituindo $x$: $7 + y = 10 \implies y = 3$.
> 
> **Conjunto Solução:** $S = \{(7, 3)\}$ (Sistema SPD).

### 3.2. Método da Substituição

Consiste em isolar uma variável em uma das equações e substituí-la na outra.

1. Isole $x$ na 1ª equação: $x = 10 - y$.
    
2. Substitua na 2ª equação: $(10 - y) - y = 4 \implies 10 - 2y = 4 \implies 2y = 6 \implies y = 3$.
    

## 📊 Tabela Resumo de Classificação

|**Tipo de Sistema**|**Número de Soluções**|**Relação dos Coeficientes**|**Comportamento das Retas**|
|---|---|---|---|
|**SPD** (Determinado)|**1** única solução|$\frac{a_1}{a_2} \neq \frac{b_1}{b_2}$|Concorrentes (cruzam-se em 1 ponto)|
|**SPI** (Indeterminado)|**Infinitas** soluções|$\frac{a_1}{a_2} = \frac{b_1}{b_2} = \frac{c_1}{c_2}$|Coincidentes (mesma reta)|
|**SI** (Impossível)|**Zero** soluções|$\frac{a_1}{a_2} = \frac{b_1}{b_2} \neq \frac{c_1}{c_2}$|Paralelas (nunca se cruzam)|

## 💡 Dicas de Professor para Interpretação em Provas

1. **Modelagem de Problemas Escritos:**
    
    - Traduza textos para equações identificando as variáveis.
        
    - _Exemplo clássico:_ "A soma de carros ($x$) e motos ($y$) no estacionamento é 20, e o total de rodas é 64."
        
    - **Equação de quantidade de veículos:** $x + y = 20$
        
    - **Equação de quantidade de rodas:** $4x + 2y = 64$
        
2. **Teste das Alternativas (Atalho em Provas Objetivas):**
    
    - Se a questão for de escolha múltipla e pedir os valores de $x$ e $y$, muitas vezes é mais rápido **substituir os pares ordenados das alternativas diretamente nas equações do sistema** para ver qual satisfaz ambas do que resolver o sistema do zero.
        

Quer praticar algum problema específico de modelagem em sistemas lineares para fixar o conteúdo?