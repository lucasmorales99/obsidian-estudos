#TI
### Tipos de Dados Simples (Primitivos)

Armazenam **apenas um único valor** por vez em um espaço dedicado na memória. Quando um novo valor é atribuído, o anterior é substituído.
- **Inteiro:** Números inteiros, sem parte fracionária ou decimal (positivos, negativos ou zero).
    
    - _Exemplos:_ `-15`, `0`, `42`
        
    - _Uso típico:_ Contadores, idade, quantidade de itens.
        
- **Real (Ponto Flutuante / Float / Double):** Números que possuem parte fracionária ou decimal.
    
    - _Exemplos:_ `3.14`, `-0.5`, `199.99`
        
    - _Uso típico:_ Preços, altura, notas de provas, medições científicas.
        
- **Caractere (Char) e Cadeia de Caracteres (String):**
    
    - **Char:** Representa um único caractere (letra, símbolo ou número como texto). Exemplo: `'A'`, `'%'`.
        
    - **String:** Uma sequência/cadeia de caracteres agrupados para formar texto. Exemplo: `"Morales"`, `"Engenharia de Computação"`.
        
    - _Uso típico:_ Nomes, descrições, endereços de e-mail.
        
- **Lógico (Booleano):** Representa um estado de verdade baseado na álgebra booleana. Aceita apenas dois valores possíveis: **Verdadeiro** (`true`/`1`) ou **Falso** (`false`/`0`).
    
    - _Uso típico:_ Flags, status de autenticação (`is_logged_in`), validações de condições.

### Tipos de Dados Estruturados (Compostos / Homogêneos)

Agrupam **múltiplos valores do mesmo tipo** sob um único nome de variável, organizados na memória através de índices numéricos.

| **Estrutura**                       | **Dimensões** | **Organização**                                                                          | **Exemplo Visual / Conceitual**                                  |
| ----------------------------------- | ------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Vetor** (Array Unidimensional)    | 1D            | Sequência linear contínua. Acessado por um único índice `v[i]`.                          | Uma lista de compras ou notas de um aluno: `[7.5, 8.0, 9.5]`     |
| **Matriz** (Array Multidimensional) | 2D (ou mais)  | Tabela organizada em **linhas e colunas**. Acessada por dois índices `m[linha][coluna]`. | Um tabuleiro de xadrez, uma planilha ou os pixels de uma imagem. |
#### Principais Características dos Arrays:

1. **Homogeneidade:** Todos os elementos armazenados dentro do array precisam obrigatoriamente ser do mesmo tipo primitivo (ex: um vetor só de inteiros).
    
2. **Acesso Indexado:** Cada elemento possui uma posição fixa. Na maioria das linguagens (como C, Java, JavaScript, PHP), o primeiro elemento fica na **posição 0**.
    
3. **Alocação Sequencial:** Os dados ficam dispostos de forma contígua no bloco de memória do sistema.

