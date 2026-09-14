#db 
# Guia de Estudos: Álgebra Relacional

A **Álgebra Relacional** é uma linguagem de consulta procedural e teórica que utiliza operações para manipular e combinar relações (tabelas) e produzir novas relações como resultado. Ela serve como base fundamental para a otimização de consultas e a execução do SQL em Sistemas Gerenciadores de Bancos de Dados (SGBDR).

## 1. Operações Unárias (Unimodais)

Operações que atuam sobre **uma única relação** (tabela).

### A. Seleção ($\sigma$)

- **O que faz:** Filtra as **linhas** (tuplas) de uma relação que satisfazem a uma condição lógica predefinida.
    
- **Símbolo:** $\sigma_{\text{condição}}(R)$
    
- **Equivalente em SQL:** Cláusula `WHERE`
    
- **Exemplo:** Selecionar funcionários com salário maior que 5000 na tabela _Funcionario_.
    
    - $\sigma_{\text{salario} > 5000}(\text{Funcionario})$
        

### B. Projeção ($\pi$)

- **O que faz:** Selecionar e filtra as **colunas** (atributos) desejadas de uma relação, removendo duplicatas do resultado.
    
- **Símbolo:** $\pi_{\text{atributo1, atributo2}}(R)$
    
- **Equivalente em SQL:** Cláusula `SELECT`
    
- **Exemplo:** Projetar apenas o nome e o e-mail dos funcionários.
    
    - $\pi_{\text{nome, email}}(\text{Funcionario})$
        

### C. Renomeação ($\rho$)

- **O que faz:** Altera o nome da relação, de seus atributos, ou de ambos (útil para consultas auto-referenciadas ou evitar ambiguidades).
    
- **Símbolo:** $\rho_{S(A1, A2, ...)}(R)$ ou $\rho_{S}(R)$
    
- **Equivalente em SQL:** Cláusula `AS`
    

## 2. Operações Fundamentais de Conjuntos (Binárias)

Operações que atuam sobre **duas relações**. Para União, Interseção e Diferença, as tabelas devem ser **compatíveis quanto à união** (terem o mesmo número de atributos e tipos de dados correspondentes no mesmo domínio).

### A. União ($\cup$)

- **O que faz:** Combina todas as tuplas das relações $R$ e $S$, eliminando as duplicadas.
    
- **Símbolo:** $R \cup S$
    
- **Equivalente em SQL:** `UNION`
    

### B. Diferença ($\setminus$ ou $-$)

- **O que faz:** Retorna as tuplas que estão na relação $R$, mas **não** estão na relação $S$.
    
- **Símbolo:** $R - S$
    
- **Equivalente em SQL:** `EXCEPT` ou `MINUS`
    

### C. Produto Cartesiano ($\times$)

- **O que faz:** Combina **todas as linhas** de $R$ com **todas as linhas** de $S$. Se $R$ tem $n$ linhas e $S$ tem $m$ linhas, o resultado terá $n \times m$ linhas. **Não exige** compatibilidade de união.
    
- **Símbolo:** $R \times S$
    
- **Equivalente em SQL:** `CROSS JOIN` (ou múltiplos nomes de tabelas na cláusula `FROM` sem `WHERE`).
    

## 3. Operações Derivadas e Junções

### A. Interseção ($\cap$)

- **O que faz:** Retorna apenas as tuplas presentes **em ambas** as relações $R$ e $S$.
    
- **Símbolo:** $R \cap S$
    
- **Relação com Operações Básicas:** Pode ser expressa como $R - (R - S)$.
    
- **Equivalente em SQL:** `INTERSECT`
    

### B. Junção Theta ($\bowtie_{\theta}$) e Equijunção

- **O que faz:** Combina o Produto Cartesiano com uma Seleção baseada em um predicado/condição $\theta$.
    
- **Fórmula:** $R \bowtie_{\theta} S = \sigma_{\theta}(R \times S)$
    
- **Equijunção:** Quando o operador de comparação $\theta$ utiliza apenas a igualdade ($=$).
    

### C. Junção Natural ($\bowtie$)

- **O que faz:** Realiza a junção entre $R$ e $S$ combinando linhas que possuem **valores iguais em todos os atributos com o mesmo nome**, eliminando as colunas duplicadas no resultado final.
    
- **Símbolo:** $R \bowtie S$
    
- **Equivalente em SQL:** `NATURAL JOIN` or `INNER JOIN ... ON ...`
    

### D. Junções Externas (Outer Joins)

Preservam as linhas que não encontram correspondência na outra tabela, preenchendo as colunas faltantes com `NULL`:

- **Junção Esquerda ($\Leftbowtie$):** Mantém todas as tuplas da relação à esquerda (`LEFT JOIN`).
    
- **Junção Direita ($\Rightbowtie$):** Mantém todas as tuplas da relação à direita (`RIGHT JOIN`).
    
- **Junção Completa ($\Fullouterjoin$ ou $\mathbb{\bowtie}$):** Mantém todas as tuplas de ambas as relações (`FULL OUTER JOIN`).
    

## 4. Tabela de Mapeamento: Álgebra Relacional vs. SQL

|**Álgebra Relacional**|**Operador / Símbolo**|**Cláusula SQL / Conceito**|
|---|---|---|
|**Seleção**|$\sigma_{\text{condição}}(R)$|`WHERE`|
|**Projeção**|$\pi_{\text{atributos}}(R)$|`SELECT`|
|**Renomeação**|$\rho_{S}(R)$|`AS`|
|**União**|$R \cup S$|`UNION`|
|**Interseção**|$R \cap S$|`INTERSECT`|
|**Diferença**|$R - S$|`EXCEPT` / `MINUS`|
|**Produto Cartesiano**|$R \times S$|`CROSS JOIN`|
|**Junção Natural**|$R \bowtie S$|`NATURAL JOIN` / `INNER JOIN`|
|**Junção Esquerda**|$R \Leftbowtie S$|`LEFT OUTER JOIN`|

## 5. Dicas para Resolução de Questões e Exercícios

1. **Ordem de Execução das Operações:**
    
    - Em expressões compostas, resolva primeiro as operações internas entre parênteses.
        
    - Costuma-se aplicar Seleções ($\sigma$) e Projeções ($\pi$) o mais cedo possível para diminuir o tamanho dos conjuntos intermediários antes de realizar junções ($\bowtie$) ou produtos cartesianos ($\times$).
        
2. **Identificação da Operação:**
    
    - Filtrar **linhas/registros** especificando condições $\rightarrow$ **Seleção** ($\sigma$).
        
    - Escolher **colunas/campos** $\rightarrow$ **Projeção** ($\pi$).
        
3. **Compatibilidade de União:** Se uma questão perguntar se é possível fazer a União, Interseção ou Diferença entre duas tabelas, verifique se elas têm a mesma **aridade** (número de colunas) e tipos compatíveis.