#logica #RacíocioLogico 

==**1. Divisão Diretamente Proporcional**==

Dividir um número $N$ em partes $x, y, z$ diretamente proporcionais a $a, b, c$ significa que as partes aumentam ou diminuem na mesma razão dos valores de referência.

- **Constante de Proporcionalidade ($k$):**
    
    $$k = \frac{N}{a + b + c}$$
    
- **Cálculo das partes:**
    
    - $x = a \cdot k$
        
    - $y = b \cdot k$
        
    - $z = c \cdot k$
        

==**2. Divisão Inversamente Proporcional**==

Dividir um número $N$ em partes $x, y, z$ inversamente proporcionais aos valores $a, b, c$ equivale a fazer uma divisão **diretamente proporcional aos seus inversos** ($\frac{1}{a}, \frac{1}{b}, \frac{1}{c}$).

- **Constante de Proporcionalidade ($k$):**
    
    $$k = \frac{N}{\frac{1}{a} + \frac{1}{b} + \frac{1}{c}}$$
    
- **Cálculo das partes:**
    
    - $x = \frac{k}{a}$
        
    - $y = \frac{k}{b}$
        
    - $z = \frac{k}{c}$
        

==**3. Divisão Proporcional Composta**==

Ocorre quando a divisão depende de dois ou mais fatores simultaneamente (por exemplo, diretamente proporcional à idade e inversamente proporcional ao número de faltas).

- **Regra Prática:** Multiplique os fatores de cada grupo para criar um único índice de referência e resolva como uma divisão direta simples.
    
    - Índice $1 = a_1 \cdot b_1$
        
    - Índice $2 = a_2 \cdot b_2$
        
    - Constante $k = \frac{N}{(a_1 \cdot b_1) + (a_2 \cdot b_2)}$
        

**Resumo Metodológico**

|**Tipo de Divisão**|**Relação Matemática**|**Como Associar com a Constante k**|
|---|---|---|
|**Direta**|Quanto maior o valor de referência, maior a parte.|Somar os números dados e igualar ao total ($a \cdot k + b \cdot k = N$).|
|**Inversa**|Quanto maior o valor de referência, menor a parte.|Somar os inversos dos números e igualar ao total ($\frac{k}{a} + \frac{k}{b} = N$).|
|**Composta**|Combina mais de um critério de divisão.|Multiplicar os critérios de cada parte e somar os produtos ($a_1 b_1 k + a_2 b_2 k = N$).|

**Passo a Passo para Resolução Rápidas em Provas**

1. Identifique o tipo de proporção (direta, inversa ou mista).
    
2. Substitua os valores das partes em função de $k$.
    
3. Somar todas as partes para formar uma equação do 1º grau igual ao valor total $N$.
    
4. Encontre o valor da constante $k$ e multiplique-o pelo fator correspondente da parte pedida no enunciado.