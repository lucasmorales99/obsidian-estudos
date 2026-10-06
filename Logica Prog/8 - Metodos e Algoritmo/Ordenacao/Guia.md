### Guia Definitivo de Algoritmos de Ordenação — Foco CEBRASPE

Nas provas de TI do **CEBRASPE**, a pauta de **Métodos de Ordenação** (Sorting Algorithms) é cobrada com foco na **análise de complexidade computacional** (Notação Big-O no melhor, médio e pior caso), **estabilidade**, **mecanismo de funcionamento** (Divisão e Conquista vs. Trocas Simples) e **custo de memória extra**.

### 1. Classificação dos Algoritmos de Ordenação

O CEBRASPE adora cobrar propriedades conceituais que diferenciam os algoritmos:

- **Estabilidade:** Um algoritmo é **estável** se mantém a ordem relativa original de elementos que possuem chaves com valores iguais.
    
- **In-place (Ordenação In-loco):** O algoritmo requer uma quantidade irrisória de memória auxiliar para executar a ordenação (complexidade de espaço $O(1)$).
    

### 2. Tabela Comparativa de Complexidade (Memorização para Prova)

|**Algoritmo**|**Melhor Caso**|**Caso Médio**|**Pior Caso**|**Memória Extra**|**Estável?**|
|---|---|---|---|---|---|
|**Bubble Sort**|$O(n)$|$O(n^2)$|$O(n^2)$|$O(1)$|**Sim**|
|**Insertion Sort**|$O(n)$|$O(n^2)$|$O(n^2)$|$O(1)$|**Sim**|
|**Selection Sort**|$O(n^2)$|$O(n^2)$|$O(n^2)$|$O(1)$|**Não**|
|**Merge Sort**|$O(n \log n)$|$O(n \log n)$|$O(n \log n)$|$O(n)$|**Sim**|
|**Quick Sort**|$O(n \log n)$|$O(n \log n)$|$O(n^2)$|$O(\log n)$|**Não**|
|**Heap Sort**|$O(n \log n)$|$O(n \log n)$|$O(n \log n)$|$O(1)$|**Não**|

### 3. Detalhamento dos Algoritmos Mais Cobrados

#### **A) Merge Sort (Ordenação por Intercalação)**

- **Estratégia:** Paradigma de **Divisão e Conquista**. Divide recursivamente o vetor ao meio até ter subvetores unitários e depois os intercala de forma ordenada.
    
- **Foco CEBRASPE:**
    
    - Desempenho altamente previsível: sempre atinge **$O(n \log n)$** em qualquer cenário (melhor, médio ou pior).
        
    - **Desvantagem:** Não é _in-place_; necessita de um vetor auxiliar proporcional ao tamanho da entrada, resultando em complexidade de espaço **$O(n)$**.
        
    - É um algoritmo **estável**.
        

#### **B) Quick Sort (Ordenação Rápida)**

- **Estratégia:** Paradigma de **Divisão e Conquista**. Seleciona um **pivô** e particiona o vetor de modo que elementos menores que o pivô fiquem à esquerda e os maiores à direita.
    
- **Foco CEBRASPE:**
    
    - **Pior Caso — $O(n^2)$:** Ocorre quando o pivô escolhido é repetidamente o menor ou o maior elemento (ex.: vetor já ordenado ou inversamente ordenado com escolha ingênua do primeiro/último elemento como pivô).
        
    - No caso médio, seu desempenho é excelente: **$O(n \log n)$**.
        
    - Não é um algoritmo estável em sua implementação tradicional.
        

#### **C) Heap Sort (Ordenação por Árvore Heap)**

- **Estratégia:** Constrói uma estrutura de dados **Heap Máximo** (onde a raiz é sempre o maior elemento) e extrai a raiz repetidamente para o final do vetor.
    
- **Foco CEBRASPE:**
    
    - Garante complexidade **$O(n \log n)$** no pior caso (diferente do Quick Sort) **e** é um algoritmo _in-place_ (diferente do Merge Sort).
        
    - **Não é estável**.
        

#### **D) Insertion Sort (Ordenação por Inserção)**

- **Estratégia:** Constrói a lista ordenada final um item de cada vez, como ao organizar cartas de um baralho na mão.
    
- **Foco CEBRASPE:**
    
    - **Melhor Caso — $O(n)$:** Altamente eficiente para vetores que já estão **quase ordenados** ou de tamanho muito pequeno.
        

#### **E) Selection Sort (Ordenação por Seleção)**

- **Estratégia:** Encontra o menor elemento do vetor e o troca com o elemento da primeira posição, repetindo o processo para as posições seguintes.
    
- **Foco CEBRASPE:** Faz o menor número de trocas físicas de memória, porém seu custo de comparações é **sempre $O(n^2)$**, independente da ordenação inicial dos dados.
    

### 4. Visão CEBRASPE: Padrões de Itens (Certo/Errado)

#### ⚠️ Armadilhas Recorrentes da Banca

1. **Invariabilidade do Merge Sort:**
    
    - _Item típico:_ Afirmar que o comportamento do Merge Sort se degrada para $O(n^2)$ quando os dados estão inversamente ordenados.
        
    - _Gabarito:_ **ERRADO.** O Merge Sort executa em $O(n \log n)$ em todas as condições de entrada.
        
2. **Pior Caso do Quick Sort:**
    
    - _Item típico:_ O Quick Sort garante tempo de execução $O(n \log n)$ em todas as situações, independentemente do pivô escolhido.
        
    - _Gabarito:_ **ERRADO.** A má escolha do pivô em conjuntos já ordenados gera o pior caso $O(n^2)$.
        
3. **Uso de Memória Auxiliar:**
    
    - O CEBRASPE costuma trocar as características de memória do Merge Sort e do Heap Sort. Lembre-se: o **Heap Sort** ordena _in-place_ sem precisar de um array auxiliar de tamanho $n$.
        

### 💡 Resumo Tático de Revisão

- **Sempre $O(n \log n)$:** Merge Sort e Heap Sort.
    
- **Média $O(n \log n)$, mas Pior Caso $O(n^2)$:** Quick Sort.
    
- **Eficiente para Dados Quase Ordenados:** Insertion Sort — $O(n)$ no melhor caso.
    
- **Melhor combinação de $O(n \log n)$ no pior caso + In-place:** Heap Sort.
    
- **Precisa de Espaço Extra $O(n)$:** Merge Sort.