### Guia Definitivo de Algoritmos de Pesquisa/Busca — Foco CEBRASPE

Nas provas da banca **CEBRASPE**, a pauta de **Algoritmos de Pesquisa (Busca)** é cobrada com foco na **análise de complexidade computacional** (Notação Big-O), **requisitos prévios de ordenação**, **mecanismos de funcionamento interno** e comparação entre abordagens sequenciais e baseadas em estruturas de dados hierárquicas.

### 1. Pesquisa Linear (ou Sequencial)

- **Funcionamento:** Percorre a estrutura (vetor, lista) elemento por elemento, a partir da primeira posição até encontrar o valor desejado ou atingir o final.
    
- **Requisito:** **Não exige** que os dados estejam ordenados.
    
- **Complexidade Computacional:**
    
    - **Melhor Caso:** $O(1)$ (o elemento buscado é o primeiro da lista).
        
    - **Caso Médio:** $O(n)$ (o elemento está no meio da lista).
        
    - **Pior Caso:** $O(n)$ (o elemento é o último ou não está presente na lista).
        
- **Foco CEBRASPE:** É a escolha mais simples e a única aplicável a listas/vetores não ordenados ou estruturas encadeadas simples sem índice.
    

### 2. Pesquisa Binária (Binary Search)

- **Funcionamento:** Aplica a estratégia de **Divisão e Conquista**. Compara o elemento do meio da estrutura com o valor buscado:
    
    - Se forem iguais, a busca é finalizada.
        
    - Se o valor buscado for menor, a busca continua apenas na metade esquerda.
        
    - Se for maior, a busca continua apenas na metade direita.
        
- **Requisito Obrigatório:** Exige **obrigatoriamente** que o conjunto de dados esteja **ordenado** e permita **acesso direto/aleatório** aos elementos (como um array/vetor).
    
- **Complexidade Computacional:**
    
    - **Melhor Caso:** $O(1)$ (o elemento está exatamente no meio na primeira tentativa).
        
    - **Caso Médio:** $O(\log n)$.
        
    - **Pior Caso:** $O(\log n)$.
        

### 3. Pesquisa em Árvores de Busca (BST e Árvores Balanceadas)

#### **A) Árvores Binárias de Busca (BST - Binary Search Tree)**

- **Propriedade:** Para qualquer nó, todos os nós da sua subárvore esquerda possuem valores menores, e todos da subárvore direita possuem valores maiores.
    
- **Complexidade de Pesquisa:**
    
    - **Caso Médio (Árvore Balanceada):** $O(\log n)$.
        
    - **Pior Caso (Árvore Degenerada/Desbalanceada):** $O(n)$ — ocorre quando os elementos são inseridos em ordem e a árvore se comporta como uma lista encadeada simples.
        

#### **B) Árvores Autobalanceadas (AVL e Red-Black)**

- **Funcionamento:** Aplicam rotações automáticas após inserções/remoções para manter a altura da árvore proporcional a $O(\log n)$.
    
- **Foco CEBRASPE:** Garantem que o pior caso de pesquisa seja **sempre $O(\log n)$**, eliminando a degradação para $O(n)$ observada nas BSTs simples.
    

### 4. Tabela Comparativa de Complexidade de Busca

|**Algoritmo / Estrutura**|**Pré-requisito**|**Melhor Caso**|**Caso Médio**|**Pior Caso**|
|---|---|---|---|---|
|**Pesquisa Sequencial**|Nenhum|$O(1)$|$O(n)$|$O(n)$|
|**Pesquisa Binária**|Dados Ordenados em Array|$O(1)$|$O(\log n)$|$O(\log n)$|
|**Árvore Binária (BST)**|Estrutura de BST válida|$O(1)$|$O(\log n)$|$O(n)$|
|**Árvore AVL / Red-Black**|Árvore Balanceada|$O(1)$|$O(\log n)$|$O(\log n)$|
|**Tabela Hash**|Função Hash|$O(1)$|$O(1)$|$O(n)$|

### 5. Visão CEBRASPE: Padrões de Itens (Certo/Errado)

#### ⚠️ Armadilhas Recorrentes da Banca

1. **Aplicação da Pesquisa Binária em Listas Encadeadas:**
    
    - _Pegadinha:_ Afirmar que a pesquisa binária atinge tempo $O(\log n)$ em uma lista encadeada simples (_Singly Linked List_) ordenada.
        
    - _Gabarito:_ **ERRADO.** Como listas encadeadas não oferecem acesso direto ao elemento central em tempo $O(1)$ (exigem caminhamento nó a nó), a busca binária perde sua eficiência prática nesse tipo de estrutura.
        
2. **Exigência de Ordenação:**
    
    - _Pegadinha:_ Afirmar que a busca binária pode ser aplicada em qualquer vetor não ordenado desde que se conheça a primeira e a última posição.
        
    - _Gabarito:_ **ERRADO.** Sem a ordenação prévia dos dados, o algoritmo da busca binária não pode descartar metades do vetor.
        
3. **Pior Caso em BSTs:**
    
    - O CEBRASPE costuma cobrar se uma Árvore Binária de Busca simples pode degradar para $O(n)$. A resposta é **SIM**, no caso de inserções em ordem crescente ou decrescente que formam uma estrutura pendente (degenerada).
        

### 💡 Resumo Tático de Revisão

- **Dados Não Ordenados:** Apenas Pesquisa Sequencial ($O(n)$) ou Tabela Hash ($O(1)$ médio).
    
- **Dados Ordenados em Array:** Pesquisa Binária ($O(\log n)$).
    
- **Busca Binária:** Divide o espaço de busca pela metade a cada passo ($O(\log n)$).
    
- **Garantia de Pior Caso $O(\log n)$ em Árvores:** Exige balanceamento (AVL ou Red-Black).