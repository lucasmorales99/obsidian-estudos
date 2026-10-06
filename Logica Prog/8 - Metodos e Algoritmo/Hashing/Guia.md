### Guia Definitivo de Hashing — Foco CEBRASPE

Nas provas do **CEBRASPE**, a pauta de **Hashing** (Tabelas Hash, Funções de Espalhamento e Tratamento de Colisões) é cobrada com foco em **desempenho computacional** (Notação Big-O), **propriedades matemáticas**, **algoritmos de resolução de conflitos** e **mecanismos de segurança/integridade**.

### 1. Conceito e Funcionamento da Tabela Hash (_Hash Table_)

A Tabela Hash é uma estrutura de dados projetada para realizar buscas, inserções e remoções de dados em tempo constante **O(1) no caso médio**.

- **Função Hash / Espalhamento:** É a função matemática h(k) que mapeia uma chave k (de tamanho arbitrário ou universo grande) para um índice (posição) do array da tabela (de tamanho m).
    
- **Custo Computacional (Análise de Complexidade):**
    
    - **Caso Médio (Sem colisões excessivas):** Busca, Inserção e Remoção ocorrem em **O(1)**.
        
    - **Pior Caso (Com colisões severas / Má distribuição):** Degradam para **O(n)**, onde a estrutura se comporta como uma lista encadeada simples.
        

### 2. Tratamento de Colisões (A Pauta Mais Cobrada!)

Uma **colisão** ocorre quando duas chaves distintas k1​ e k2​ produzem o mesmo índice na tabela: h(k1​)=h(k2​). Como duas informações não podem ocupar o mesmo slot físico, a banca exige o conhecimento exato dos métodos de resolução:

#### **A) Endereçamento Aberto (Open Addressing)**

Todos os elementos são armazenados na **própria tabela**. Não há ponteiros para estruturas externas. Quando ocorre uma colisão, o algoritmo procura por outro slot livre seguindo uma sondagem (_probing_):

1. **Sondagem Linear (_Linear Probing_):**
    
    - Procura a próxima posição livre sequencialmente: h(k,i)=(h′(k)+i)modm.
        
    - **Problema:** Propenso ao **Agrupamento Primário** (_Primary Clustering_), no qual sequências longas de posições ocupadas começam a se formar, aumentando o tempo de busca.
        
2. **Sondagem Quadrática (_Quadratic Probing_):**
    
    - Usa uma função quadrática da tentativa: h(k,i)=(h′(k)+c1​i+c2​i2)modm.
        
    - **Vantagem/Problema:** Evita o agrupamento primário, mas pode gerar **Agrupamento Secundário** (_Secondary Clustering_).
        
3. **Dispersão Dupla (_Double Hashing_):**
    
    - Utiliza uma segunda função hash para calcular o salto de busca: h(k,i)=(h1​(k)+i⋅h2​(k))modm.
        
    - É um dos métodos de endereçamento aberto de **melhor desempenho**, diminuindo os agrupamentos.
        

#### **B) Encadeamento Separado / Fechado (_Separate Chaining_)**

Cada posição (slot) da tabela contém uma referência para uma estrutura de dados secundária (geralmente uma **Lista Encadeada**).

- **Mecanismo:** Em caso de colisão, o novo item é simplesmente inserido no início ou fim da lista daquela posição.
    
- **Comportamento:** A tabela pode armazenar mais elementos do que o seu tamanho físico (n>m). Se todas as chaves colidirem para o mesmo slot, a busca atinge a complexidade **O(n)**.
    

### 3. Fator de Carga (_Load Factor_)

- **Definição:** Representado por α=mn​, onde n é o número de elementos armazenados e m é o número de posições (tamanho) da tabela Hash.
    
- **No Endereçamento Aberto:** O fator de carga α **nunca pode ser maior que 1** (α≤1).
    
- **No Encadeamento Separado:** O fator de carga α **pode ser maior que 1** (α>1).
    

### 4. Hashing no Contexto de Criptografia e Segurança

Quando a questão do CEBRASPE puxa o Hashing para o contexto de **Segurança da Informação e Criptografia**, as propriedades cobradas mudam de escopo:

- **Unidirecionalidade (Sentido Único):** É computacionalmente inviável reverter o resumo gerado (_digest_) para o valor de entrada.
    
- **Tamanho Fixo:** O resumo gerado possui **tamanho fixo**, independentemente do tamanho da entrada.
    
- **Propriedade Garantida:** O Hashing em segurança garante a **Integridade** dos dados.
    
- **Resistência à Colisão:** Nenhuma função hash criptográfica ideal deve permitir encontrar duas entradas diferentes x=y tal que h(x)=h(y).
    
- **Principais Algoritmos:**
    
    - **Obsoletos/Inseguros:** MD5 (128 bits) e SHA-1 (160 bits).
        
    - **Padrão Seguro:** Família SHA-2 (SHA-256) e SHA-3.
        

### 5. Visão CEBRASPE: Padrões de Itens (Certo/Errado)

#### ⚠️ Armadilhas Recorrentes da Banca

1. **Desempenho Garantido:**
    
    - _Pegadinha:_ Afirmar que a Tabela Hash garante tempo de busca O(1) em **todos os casos**.
        
    - _Gabarito:_ **ERRADO.** No pior caso (alta taxa de colisão), a complexidade de busca degrada para **O(n)**.
        
2. **Endereçamento Aberto x Encadeamento:**
    
    - O CEBRASPE costuma trocar os conceitos: afirmar que o endereçamento aberto utiliza listas encadeadas externas. Lembre-se: no **Endereçamento Aberto**, todas as chaves ficam **dentro** do próprio vetor/tabela.
        
3. **Redimensionamento (_Rehashing_):**
    
    - Quando o fator de carga atinge um limite, a tabela precisa dobrar de tamanho e realocar todas as chaves existentes usando a nova função hash, operação com custo O(n).
        

### 💡 Resumo Tático de Revisão

- **Caso Médio de Busca/Inserção:** O(1).
    
- **Pior Caso:** O(n) (quando ocorrem colisões excessivas).
    
- **Endereçamento Aberto:** Dados ficam dentro do array (Sondagem Linear, Quadrática, Double Hashing).
    
- **Encadeamento Separado:** Usa listas encadeadas externas nos slots.
    
- **Fator de Carga (α=n/m):** Mede a ocupação da tabela.
    
- **Hash em Segurança:** Unidirecional, saída de tamanho fixo, garante **Integridade**.