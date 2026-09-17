#frameworks

Atenção, turma! Peguem as canetas e abram os cadernos. Dando continuidade ao nosso **Guia de Tecnologia**, a aula de hoje é dedicada à biblioteca mais popular do ecossistema JavaScript para criação de interfaces: o **React**!

Anotem aí: assim como vimos nas aulas sobre o ecossistema de _Front-End_, o React é uma das tecnologias mais cobradas em seleções técnicas e provas de tecnologia pela sua eficiência e pelo seu modelo mental focado em componentes reativos.

### 🎓 Aula: Framework, Biblioteca e Padrões do React

#### 1. React é um Framework ou uma Biblioteca?

Este é um ponto clássico de pegadinha em provas e entrevistas:

- **Biblioteca (Library):** Oficialmente, o React **não é um framework completo**, mas sim uma **biblioteca JavaScript para construção de interfaces de usuário (UI)**. Ele foca exclusivamente na camada de visualização (_View_).
    
- **Frameworks do Ecossistema React:** Para transformar o React em uma solução completa (_full-stack_ ou SPA robusta), o mercado utiliza frameworks construídos sobre ele, como o **Next.js** ou **Remix**, que adicionam roteamento, renderização no servidor (_SSR_) e otimizações.
    

#### 2. Conceitos e Padrões Arquiteturais no React

##### A. Arquitetura Baseada em Componentes (_Component-Driven_)

No React, a interface do usuário é dividida em pequenas partes isoladas, independentes e reutilizáveis chamadas **Componentes**.

- **JSX (JavaScript XML):** O React utiliza uma extensão de sintaxe que permite escrever código semelhante ao HTML diretamente dentro do JavaScript.
    
- **Componentes Funcionais:** Hoje em dia, o padrão oficial é escrever componentes como funções JavaScript simples que retornam JSX.
    

##### B. Virtual DOM e Reconciliação

- O React não altera o DOM real do navegador diretamente a cada mudança de estado. Em vez disso, ele mantém uma representação leve em memória chamada **Virtual DOM**.
    
- **Algoritmo de Reconciliação (_Diffing_):** Quando o estado da aplicação muda, o React compara a nova árvore do Virtual DOM com a anterior, calcula as diferenças exatas e atualiza apenas os elementos que realmente mudaram no DOM real, garantindo alta performance.
    

##### C. Fluxo Unidirecional de Dados (_One-Way Data Flow_)

Ao contrário de padrões com _Two-Way Data Binding_, no React os dados fluem estritamente em uma única direção (de cima para baixo, do componente Pai para o Filho via _Props_).

#### 3. Padrões de Desenvolvimento no React (_React Patterns_)

##### A. Hooks (O Padrão Moderno)

Introduzidos na versão 16.8, os **Hooks** permitem gerenciar estado e ciclo de vida dentro de componentes funcionais sem a necessidade de criar classes:

- `useState`: Declara e gerencia o estado local do componente.
    
- `useEffect`: Gerencia efeitos colaterais (como buscar dados de uma API REST ou registrar eventos).
    
- `useContext`: Permite acessar dados compartilhados globalmente sem precisar passar _props_ manualmente por vários níveis (_Prop Drilling_).
    
- `useMemo` / `useCallback`: Utilizados para otimização de performance e _caching_ de cálculos/funções.
    

##### B. Componentes Controlados vs. Não Controlados

- **Controlados:** O valor de elementos de formulário (como `<input>`) é totalmente controlado pelo estado do React.
    
- **Não Controlados:** O valor é mantido e lido diretamente do DOM nativo através de referências (`useRef`).
    

##### C. Padrão de Composição (_Composition Pattern_)

Em vez de depender fortemente de herança, o React utiliza a composição de componentes (por exemplo, utilizando a _prop_ `children`) para construir interfaces flexíveis e modulares.

#### 4. Padrões de Gerenciamento de Estado Global

Para aplicações de grande porte onde o estado precisa ser acessado por componentes distantes na árvore:

- **Context API:** Solução nativa do próprio React para compartilhar estados simples ou médios (ex: tema claro/escuro, dados do usuário logado).
    
- **Redux / Redux Toolkit:** Padrão arquitetural baseado em uma **única fonte de verdade (Single Source of Truth)**, estado imutável e ações puras (_Reducers_) para alterar o estado global.
    
- **Bibliotecas Atômicas e de Fetching:** Uso de ferramentas modernas como **Zustand**, **Jotai** ou **TanStack Query (React Query)** para gerenciar cache e dados vindos de APIs.
    

##### 📝 Resumo do Professor para Revisão Rápida

- **Natureza:** Biblioteca voltada exclusivamente para a camada de interface (_UI_), e não um framework completo por si só.
    
- **Construção:** Uso de **JSX** e criação de **Componentes Funcionais**.
    
- **Performance:** Uso do **Virtual DOM** para atualizar a tela de forma otimizada.
    
- **Lógica:** Uso de **Hooks** (`useState`, `useEffect`) para controle de estado e ciclo de vida.
    
- **Fluxo de Dados:** **Unidirecional** (_Props Down, Events Up_).
    

Ficou clara a diferença entre o React e os frameworks completos, turma? Para a próxima aula, podemos fazer um quadro comparativo entre o **React** e o **Vue.js** ou resolver exercícios sobre Hooks e manipulação de estado!