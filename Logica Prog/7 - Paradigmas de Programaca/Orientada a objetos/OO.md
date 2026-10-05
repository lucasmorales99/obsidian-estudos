#paradigmaDeProgramacao #OO #logProg
### Guia Definitivo de Programação Orientada a Objetos (POO) — Foco CEBRASPE

A banca **CEBRASPE** cobra a Orientação a Objetos combinando **conceitos teóricos/conceituais** (propriedades, pilares e relacionamentos) com a sua **aplicação prática** em linguagens modernas de mercado (especialmente **Java** e **Python**) e padrões de projeto/arquitetura.

### 1. Pilares Fundamentais de POO (A Pauta Favorita de Pega-Rapazes)

#### **A) Abstração**

- **Conceito:** Capacidade de isolar aspectos essenciais de um domínio do mundo real, ignorando detalhes irrelevantes para o modelo.
    
- **Pegadinha do CEBRASPE:** A banca costuma confundir _Abstração_ com _Encapsulamento_. Lembre-se: Abstração foca no **o que** o objeto faz; Encapsulamento foca em **como** ele oculta sua estrutura interna.
    

#### **B) Encapsulamento**

- **Conceito:** Ocultamento dos dados/estados internos de um objeto, liberando acesso apenas por meio de uma interface pública (métodos getter/setter ou métodos de negócio).
    
- **Modificadores de Acesso (foco em Java):**
    
    - `public`: Acessível por qualquer classe.
        
    - `protected`: Acessível no mesmo pacote ou por subclasses (mesmo em outros pacotes).
        
    - _default_ (package-private): Acessível apenas dentro do mesmo pacote.
        
    - `private`: Acessível **apenas** dentro da própria classe.
        

#### **C) Herança**

- **Conceito:** Mecanismo que permite que uma classe (subclasse/derivada) herde atributos e métodos de outra classe (superclasse/base), promovendo reuso de código.
    
- **Pegadinha do CEBRASPE:**
    
    - **Herança Múltipla:** O CEBRASPE ama afirmar que _Java suporta herança múltipla de classes_. **ERRADO!** Java possui herança simples de classes (uma classe estende apenas uma superclasse com `extends`). O que Java permite é a **implementação múltipla de interfaces** (`implements`).
        
    - Python, por outro lado, **suporta** herança múltipla de classes diretamente.
        

#### **D) Polimorfismo**

- **Conceito:** Capacidade de um mesmo método/mensagem responder de formas diferentes dependendo do objeto que o executa.
    
- **Sobrecarga (_Overloading_) vs. Sobrescrita (_Overriding_):**
    

|**Recurso**|**Tipo de Polimorfismo**|**Assinatura do Método**|**Onde Ocorre**|
|---|---|---|---|
|**Sobrecarga (_Overloading_)**|Estático (Tempo de Compilação)|**Muda** (parâmetros ou tipos diferentes)|Na **mesma** classe|
|**Sobrescrita (_Overriding_)**|Dinâmico (Tempo de Execução)|**Igual** (mesmo nome, parâmetros e retorno)|Entre **Subclasse** e **Superclasse**|

### 2. Classes, Interfaces, Classes Abstratas e Métodos

- **Classe Abstrata:**
    
    - Não pode ser instanciada diretamente (`new`).
        
    - Pode conter métodos abstratos (sem corpo) e métodos concretos (com implementação).
        
    - Serve como estrutura/base para subclasses.
        
- **Interface:**
    
    - Define um contrato de comportamento.
        
    - Por padrão, todos os métodos são `public` e `abstract` (no Java tradicional).
        
    - A partir do Java 8, interfaces podem ter métodos com implementação usando a palavra-chave `default`.
        
- **Classes Seladas / Imutabilidade:** Atente-se a conceitos modernos do Java (como `record` e classes `final`, que não podem ser estendidas).
    

### 3. Relações Entre Objetos (UML & Projeto)

O CEBRASPE frequentemente cobra a distinção entre os tipos de associação:

1. **Associação Simples:** Um objeto "conhece" ou se relaciona com outro, mas sem vínculo de dependência rígido de ciclo de vida.
    
2. **Agregação (Relação "Tem-Um" fraca):**
    
    - Todo e Parte existem de forma independente.
        
    - _Exemplo:_ `Departamento` e `Professor`. Se o Departamento for extinto, o Professor continua existindo no sistema.
        
3. **Composição (Relação "Tem-Um" forte):**
    
    - A Parte não existe sem o Todo (dependência de ciclo de vida).
        
    - _Exemplo:_ `Pedido` e `ItemPedido`. Se o Pedido for destruído, os itens acompanham o ciclo de vida.
        
4. **Acoplamento e Coesão (Regra de Ouro em Concursos):**
    
    - O objetivo do bom design OO é buscar **Baixo Acoplamento** (pouca dependência direta entre classes) e **Alta Coesão** (cada classe focada em uma única responsabilidade).
        

### 4. Visão CEBRASPE: Padrões de Itens (Certo/Errado)

#### ⚠️ Armadilhas Recorrentes da Banca

1. **Ligação Tardia (_Late Binding / Dynamic Binding_):**
    
    - O CEBRASPE costuma conceituar que o polimorfismo dinâmico (sobrescrita) depende da ligação tardia, na qual a decisão de qual método chamar é tomada em **tempo de execução** (_runtime_), e não de compilação. _(Geralmente afirmativa CORRETA)._
        
2. **Ocultamento de Membros x Sobrescrita:**
    
    - Atributos ou métodos estáticos (`static`) **não são sobrescritos**, mas sim **ocultados** (_shadowing/hiding_).
        
3. **Conceito de Interface x Classe Abstrata:**
    
    - Se o item disser que _"uma interface pode instanciar objetos diretamente no código por meio do operador new"_, a afirmativa está **INCORRETA**.
        
4. **Mapeamento Objeto-Relacional (ORM):**
    
    - A banca adora conectar POO a bancos de dados relacionais via ORM (Hibernate, JPA), citando o **Impedimento de Impedância** (diferença estrutural entre o modelo orientado a objetos e o modelo relacional de tabelas/chaves estrangeiras).
        

### 💡 Resumo Tático de Revisão

- **Herança Múltipla:** Não existe para classes em Java; existe em Python; Java resolve com interfaces.
    
- **Sobrecarga:** Mesma classe, assinaturas diferentes (compilação).
    
- **Sobrescrita:** Subclasse reescreve método da classe pai, mesma assinatura (execução).
    
- **Agregação x Composição:** Agregação = a parte sobrevive sem o todo; Composição = a parte morre com o todo.
    
- **Design de Qualidade:** Baixo Acoplamento + Alta Coesão.
- 