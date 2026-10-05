#paradigmaDeProgramacao #ProgEstrutura #logProg
### Guia Definitivo de Programação Estruturada — Foco CEBRASPE

A banca **CEBRASPE** cobra o paradigma de **Programação Estruturada** focando na sua base teórica formal (Teorema da Programação Estruturada), nos seus blocos de controle de fluxo e na comparação direta com outros paradigmas (como o orientado a objetos ou procedimental puro).

PDF

### 1. O Teorema da Programação Estruturada (Böhm-Jacopini)

O fundamento teórico mais cobrado pelo CEBRASPE é o **Teorema de Böhm-Jacopini** (1966), que estabelece que **qualquer algoritmo computável** pode ser escrito utilizando apenas três estruturas de controle fundamentais:

PDF

1. **Sequência:** Execução de instruções em ordem linear, passo a passo (uma após a outra).
    
    PDF
    
2. **Seleção (ou Decisão/Desvio):** Escolha de caminhos de execução com base em uma condição lógica (`if-else`, `switch-case` / `escolha-caso`).
    
    PDF
    
3. **Repetição (ou Laço/Iteração):** Execução repetida de um bloco de código enquanto uma condição for verdadeira ou até atingir um limite (`while`, `do-while`, `for` / `enquanto`, `para`).
    
    PDF
    

#### ⚠️ A Regra do Ponto Único de Entrada e Saída

Na definição estrita da programação estruturada, **todo bloco, função ou subprograma deve ter exatamente um único ponto de entrada e um único ponto de saída**.

- **Aplicações em Prova:** A banca costuma colocar itens afirmando que o uso desenfreado de instruções de salto incondicional, como o `GOTO`, violava esse princípio ao poluir o fluxo do código (criando o chamado _"Spaghetti Code"_).
    

### 2. Elementos Principais e Técnicas de Construção

#### **A) Abordagem Top-Down (Refinamento Sucessivo)**

- **Conceito:** Método de projeto que divide um problema grande e complexo em subproblemas menores e mais simples, resolvendo-os de forma hierárquica.
    
- **Foco CEBRASPE:** A decomposição _Top-Down_ é diretamente associada à **Modularização** (divisão de programas em rotinas, funções ou procedimentos).
    
    PDF
    

#### **B) Modularização (Funções e Procedimentos)**

- **Procedimento:** Subprograma que executa um bloco de instruções e **não retorna** valor ao chamador.
    
- **Função:** Subprograma que executa tarefas e **retorna obrigatoriamente** um valor ao ponto de chamada.
    
- **Escopo de Variáveis:**
    
    - **Locais:** Visíveis e acessíveis apenas dentro do bloco/função onde foram declaradas.
        
        PDF
        
    - **Globais:** Visíveis por todo o programa. _Nota de Prova:_ O uso excessivo de variáveis globais fere o princípio de encapsulamento estruturado e aumenta o acoplamento.
        
        PDF
        

#### **C) Mecanismos de Passagem de Parâmetros**

- **Por Valor:** Uma cópia do dado é passada para a função. Alterações feitas na variável dentro da função **não afetam** a variável original.
    
- **Por Referência (ou Endereço):** O endereço de memória é passado. Alterações feitas dentro da função **modificam diretamente** a variável original no escopo chamador.
    
    PDF
    

### 3. Programação Estruturada vs. Outros Paradigmas

O CEBRASPE adora fazer questões conceituais comparando paradigmas:

|Aspecto|Programação Estruturada|Programação Orientada a Objetos (POO)|
|---|---|---|
|**Foco Principal**|Algoritmos e **Procedimentos/Ações**|**Dados/Entidades** e seus comportamentos<br><br>PDF|
|**Unidade Básica**|Funções, Procedimentos e Módulos<br><br>PDF|Classes e Objetos<br><br>PDF|
|**Organização**|Separação entre dados e funções/ações|Agrupamento de dados (atributos) e ações (métodos) na mesma estrutura<br><br>PDF|
|**Reuso de Código**|Chamadas de funções/bibliotecas<br><br>PDF|Herança, Polimorfismo e Composição|

### 4. Visão CEBRASPE: Pegadinhas e Padrões de Itens (Certo/Errado)

1. **Uso de Comandos de Interrupção (`break`, `continue`, `return` antecipado):**
    
    - _Pegadinha:_ O CEBRASPE pode afirmar que o uso de `break` ou `continue` "invalida" a programação estruturada.
        
    - _Realidade:_ Embora o rigor teórico prefira fluxo contínuo sem saltos, linguagens modernas estruturadas admitem o uso dessas instruções de controle de fluxo de desvio sem descaracterizar o paradigma.
        
        PDF
        
2. **Recursividade no Paradigma Estruturado:**
    
    - Uma função que chama a si mesma (recursão) **é perfeitamente compatível** e muito utilizada no paradigma estruturado (e funcional).
        
        PDF
        
3. **Inexistência de Objetos:**
    
    - Dizer que a programação estruturada utiliza _conceitos de herança ou polimorfismo_ torna o item **INCORRETO** (esses recursos pertencem exclusivamente à POO).
        

### 💡 Resumo Tático de Revisão

- **3 Estruturas Certa/Obrigatórias:** Sequência, Seleção (Decisão) e Repetição (Laço).
    
    PDF
    
- **Böhm-Jacopini:** Teorema que provou que `GOTO` não é necessário para nenhum algoritmo computável.
    
    PDF
    
- **Desenvolvimento Top-Down:** Do geral/complexo para o específico/simples via modularização.
    
- **Passagem por Valor x Referência:** Valor = cópia (não altera original); Referência = endereço de memória (altera original).
    
    PDF