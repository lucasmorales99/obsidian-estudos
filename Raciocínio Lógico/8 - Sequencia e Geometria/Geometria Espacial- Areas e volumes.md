### 📚 GUIA DE ESTUDOS: SEQUÊNCIAS E GEOMETRIA ESPACIAL (CEBRASPE)

### 1. SEQUÊNCIAS: PROGRESSÃO ARITMÉTICA (PA) E GEOMÉTRICA (PG)

No estilo CEBRASPE, as questões de PA e PG raramente pedem aplicação direta de fórmula. A banca cobra a **interpretação de padrões**, a aplicação do elemento genérico e problemas contextualizados (como parcelamentos, depreciação de bens ou contágios).

#### 1.1. Progressão Aritmética (PA)

A variação entre os termos consecutivos é dada pela **soma de uma razão constante** ($r$).

- **Termo Geral:** $a_n = a_1 + (n - 1) \cdot r$
    
    - _Uso prático:_ Para achar qualquer termo, basta saber o primeiro e a razão. Exemplo: $a_{10} = a_1 + 9r$.
        
- **Soma dos $n$ primeiros termos:** $S_n = \frac{(a_1 + a_n) \cdot n}{2}$
    
- **Propriedade Média:** Em três termos consecutivos $(a, b, c)$, o termo central é a média aritmética dos vizinhos: $b = \frac{a + c}{2}$.
    

#### 1.2. Progressão Geométrica (PG)

A variação entre os termos consecutivos é dada pela **multiplicação por uma razão constante** ($q$).

- **Termo Geral:** $a_n = a_1 \cdot q^{n - 1}$
    
- **Soma dos $n$ primeiros termos (PG Finita):** $S_n = \frac{a_1 (q^n - 1)}{q - 1} \quad (q \neq 1)$
    
- **Soma Infinita (PG Convergente, $-1 < q < 1$):** $S_\infty = \frac{a_1}{1 - q}$
    
    - _Foco CEBRASPE:_ Questões com somas de frações infinitas ou frações que diminuem pela metade usam essa fórmula.
        

### 2. GEOMETRIA ESPACIAL: ÁREAS E VOLUMES

Para o CEBRASPE, o domínio de unidades de medida (conversão de $\text{m}^3$ para litros) e o cálculo de áreas totais e volumes de sólidos geométricos clássicos são vitais.

#### 2.1. Relações Fundamentais de Conversão

A banca adora misturar volume geométrico com capacidade:

- **$1 \text{ m}^3 = 1.000 \text{ Litros}$**
    
- **$1 \text{ dm}^3 = 1 \text{ Litro}$**
    
- **$1 \text{ cm}^3 = 1 \text{ mL}$**
    

#### 2.2. Os Principais Sólidos e suas Fórmulas

##### 1. Prismas e Paralelepípedos

Sólidos com duas bases paralelas e iguais.

- **Volume:** $V = A_{\text{base}} \cdot h$
    
- **Paralelepípedo Retângular (dimensões $a, b, c$):**
    
    - **Volume:** $V = a \cdot b \cdot c$
        
    - **Área Total:** $A_T = 2(ab + ac + bc)$
        
    - **Diagonal:** $D = \sqrt{a^2 + b^2 + c^2}$
        
- **Cubo (aresta $a$):**
    
    - **Volume:** $V = a^3$ | **Área Total:** $A_T = 6a^2$ | **Diagonal:** $D = a\sqrt{3}$
        

##### 2. Cilindro Circular Reto

Pense em uma lata ou cano. A base é um círculo de raio $r$.

- **Área da Base:** $A_b = \pi \cdot r^2$
    
- **Área Lateral:** $A_L = 2\pi r \cdot h$ (comprimento da circunferência $\times$ altura)
    
- **Área Total:** $A_T = 2\pi r(r + h)$
    
- **Volume:** $V = A_b \cdot h = \pi \cdot r^2 \cdot h$
    

##### 3. Pirâmide e Cone (Sólidos com "Ponta")

Sólidos que afunilam até um vértice superior. **Lembre-se da regra do "dividido por 3"**.

- **Volume Geral:** $V = \frac{1}{3} \cdot A_{\text{base}} \cdot h$
    
- **Cone Circular Reto (base circular):**
    
    - **Volume:** $V = \frac{1}{3} \cdot \pi r^2 \cdot h$
        
    - **Relação da Geratriz ($g$):** $g^2 = h^2 + r^2$ (Teorema de Pitágoras no triângulo interno)
        
    - **Área Lateral:** $A_L = \pi \cdot r \cdot g$
        

##### 4. Esfera

Sólido perfeitamente simétrico de raio $R$.

- **Área da Superfície:** $A = 4\pi R^2$
    
- **Volume:** $V = \frac{4}{3}\pi R^3$
    

### 📊 QUADRO SÍNTESE DE VOLUMES E ÁREAS

|**Sólido Geométrico**|**Área da Base (Ab​)**|**Área Total (AT​)**|**Volume (V)**|
|---|---|---|---|
|**Cubo** ($a$)|$a^2$|$6a^2$|$a^3$|
|**Paralelepípedo** ($a,b,c$)|$a \cdot b$|$2(ab + ac + bc)$|$a \cdot b \cdot c$|
|**Cilindro** ($r, h$)|$\pi r^2$|$2\pi r(r + h)$|$\pi r^2 h$|
|**Cone** ($r, h, g$)|$\pi r^2$|$\pi r(r + g)$|$\frac{1}{3} \pi r^2 h$|
|**Pirâmide**|Depende do polígono|$A_b + A_L$|$\frac{1}{3} A_b \cdot h$|
|**Esfera** ($R$)|—|$4\pi R^2$|$\frac{4}{3} \pi R^3$|

### 💡 DICAS DE PROFESSOR PARA PROVAS DA BANCA CEBRASPE

1. **Aproximação de $\pi$:** O CEBRASPE normalmente indica no enunciado se deve usar $\pi = 3$, $\pi = 3,1$ ou $\pi = 3,14$. Se o item for no formato _Certo/Errado_ e disser _"o volume é superior a X"_, faça estimativas arredondando $\pi = 3$ para ganhar tempo.
    
2. **Cuidado com a altura vs. geratriz no Cone/Pirâmide:** Um erro clássico cobrado pela banca é usar a geratriz (ou apótema) no lugar da altura $h$ na fórmula do volume. A altura é **perpendicular à base**.
    
3. **Escala e Razão entre Volumes:**
    
    - Se a razão de semelhança/escala linear entre dois sólidos semelhantes é $k$:
        
    - A razão entre suas **áreas** é $k^2$.
        
    - A razão entre seus **volumes** é $k^3$.
        
4. **Resolução de itens de PA/PG por "Casos Concretos":** Em itens teóricos da banca sobre sequências, atribua valores simples para os primeiros termos para validar se a afirmativa proposta é falsa antes de tentar demonstrações algébricas complexas.