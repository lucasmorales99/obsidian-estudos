#frameworks
### 🎓 Aula: Framework e Padrões do Vue.js

#### 1. O que é o Framework Vue.js?

O **Vue.js** é um framework JavaScript progressivo utilizado para a construção de interfaces de usuário (_frontend_) e aplicações de página única (SPA - _Single Page Applications_).

- **Por que "Progressivo"?** Significa que você pode adotá-lo gradualmente em uma aplicação já existente (como uma simples biblioteca para manipular a UI) ou usá-lo como um framework completo e robusto para gerenciar toda a sua aplicação _frontend_.
    

#### 2. Padrões Arquiteturais no Vue.js

##### A. Padrão MVVM (_Model-View-ViewModel_)

Embora seja inspirado no MVC, o Vue.js adota prioritariamente o padrão **MVVM**:

- **Model (Modelo):** Representa os dados e a lógica da aplicação (geralmente objetos JavaScript simples ou dados vindos de requisições AJAX/APIs REST).
    
- **View (Visão):** A interface gráfica HTML/DOM renderizada na tela.
    
- **ViewModel (O Vue):** É o coração do Vue.js. Ele vincula a _View_ ao _Model_ de forma transparente, escutando as mudanças nos dados e atualizando o DOM automaticamente (e vice-versa) através da reatividade.
    

##### B. Componentização (_Component-Driven Architecture_)

No Vue, a interface da aplicação é dividida em pequenas peças isoladas, independentes e reutilizáveis chamadas **Componentes**.

- **Single File Components (SFCs - arquivos `.vue`):** O Vue padroniza a criação de componentes encapsulando em um único arquivo três camadas estruturais:
    
    1. `<template>`: Onde fica a estrutura HTML (_View_).
        
    2. `<script>`: Onde fica o comportamento em JavaScript/TypeScript e o estado (_ViewModel_ / _Logic_).
        
    3. `<style>`: Onde fica o estilo CSS (que pode ser escopado usando `scoped` para não afetar outros componentes).
        

#### 3. Padrões do Framework (_Options API_ vs _Composition API_)

Ao programar com Vue (especialmente do Vue 3 em diante), utilizamos dois padrões principais de organização do código:

1. **Options API (Padrão Tradicional):**
    
    - Organiza a lógica em um objeto com propriedades predefinidas (`data`, `methods`, `computed`, `watch`, `mounted`).
        
    - **Vantagem:** Muito estruturado e fácil para iniciantes entenderem onde declarar cada tipo de instrução.
        
2. **Composition API (Padrão Moderno):**
    
    - Introduzido no Vue 3, permite organizar o código baseado em funcionalidades e contexto de negócio (usando o hook `<script setup>`).
        
    - **Vantagem:** Facilita o reuso de código e a manutenção em componentes grandes e complexos.
        

#### 4. Padrões de Reatividade e Recursos Chaves do Vue

Anotem estes termos no caderno, pois são cobranças frequentes em testes e provas:

- **Two-Way Data Binding (Ligação de Dados Bidirecional):**
    
    - Realizado via diretiva `v-model`.
        
    - As alterações feitas na interface (ex: um campo de texto `<input>`) atualizam automaticamente o estado no JavaScript, e alterações no JavaScript atualizam a interface.
        
- **Reatividade Declarativa:** O Vue cria um sistema de proxy sobre os dados do estado; quando o estado muda, a interface é re-renderizada automaticamente.
    
- **Virtual DOM:** Assim como o React, o Vue utiliza uma representação em memória do DOM real para calcular as diferenças (_diffing_) e atualizar apenas as partes que realmente mudaram na tela, otimizando a performance.
    
- **Propriedades Computadas (_Computed Properties_):** Padrão do Vue para criar valores derivados do estado que possuem sistema de _cache_ automático baseados em suas dependências.
    

#### 5. Padrões de Comunicação entre Componentes

Dentro de uma aplicação Vue, os componentes se comunicam seguindo padrões bem definidos:

- **Props Down, Events Up (Padrão Pai-Filho):**
    
    - **Props:** O componente Pai envia dados para o componente Filho de forma descendente.
        
    - **Emits (Custom Events):** O componente Filho notifica o componente Pai sobre mudanças e ações emitindo eventos.
        
- **Gerenciamento de Estado Centralizado (Pinia / Vuex):**
    
    - Para aplicações grandes onde muitos componentes precisam compartilhar informações, utiliza-se a arquitetura de estado global centralizado (semelhante ao padrão Flux/Redux).
        

##### 📝 Resumo do Professor para Revisão Rápida

- **Arquitetura Base:** MVVM (_Model-View-ViewModel_) e Arquitetura orientada a Componentes reusáveis.
    
- **Estrutura de Componentes:** Arquivos `.vue` divididos em `<template>`, `<script>` e `<style>`.
    
- **Estilos de Escrita:** _Options API_ (estruturado em propriedades) e _Composition API_ (funcional e modular).
    
- **Comunicação:** _Props_ para enviar dados para baixo; _Events/Emits_ para notificar para cima.
    
- **Conceito Chave:** Reatividade automática com _Two-Way Data Binding_ (`v-model`) e uso de _Virtual DOM_ para alta performance.
    

Alguma dúvida sobre o ecossistema e os padrões do Vue, turma? Caso queiram, podemos fazer uma comparação entre o ciclo de vida (_Lifecycle Hooks_) do Vue e do React no _frontend_!