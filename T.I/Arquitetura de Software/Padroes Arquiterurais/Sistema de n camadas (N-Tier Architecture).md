#n-camadas #arquitetura

A arquitetura de **N Camadas (N-Tier)** é um padrão arquitetural de software no qual a aplicação é dividida em partes fisicamente ou logicamente separadas e independentes.

==**Camada (_Tier_ vs _Layer_):**==

- **Layer (Camada Lógica):** Divisão lógica do código-fonte 
	(ex: pacotes, namespaces ou projetos separados na mesma aplicação).
    
- **Tier (Camada Física):** Divisão física da infraestrutura onde o código/serviço executa 
	(ex: servidores, contêineres ou clusters diferentes).

O objetivo principal é a **separação de responsabilidades (_Separation of Concerns_)**, permitindo que cada camada seja mantida, escalada ou atualizada sem impactar diretamente as outras.

### **A Evolução e Tipos de Arquitetura em Camadas**
### A. 1-Camada (==Monolítica Monoware==)

- **Estrutura:** Interface de usuário, lógica de negócios e banco de dados residem no mesmo ambiente físico e máquina.
    
- **Exemplo:** Aplicação Desktop local com SQLite ou Access embutido.
    
- **Vantagens:** Simplicidade de implantação inicial.
    
- **Desvantagens:** Baixa escalabilidade, acoplamento extremo.
    

### B. 2 Camadas (==Cliente-Servidor Clássico==)

- **Camada 1 (Cliente):** Interface do Usuário (UI) + Lógica de Negócios (Cliente Pesado) ou apenas UI (Cliente Leve).
    
- **Camada 2 (Servidor):** Banco de Dados.
    
- **Vantagens:** Separação entre dados e interface.
    
- **Desvantagens:** O banco de dados acaba contendo muitas Regras de Negócio (_Stored Procedures_), criando dependência e gargalo de desempenho.
    

### C. 3 Camadas (==A Arquitetura Canônica==)

O modelo clássico de 3 camadas serve de base para o conceito de N Camadas:

```
[ Camada de Apresentação ]  ---> (Navegador / App Mobile / SPA)
           |
           v  (HTTP / REST / gRPC)
[ Camada de Negócio / Aplicação ] ---> (Servidor de Aplicação / Regras de Negócio)
           |
           v  (SQL / ORM / Drivers)
[  Camada de Dados / Persistência ] ---> (SGBD Relacional ou NoSQL)
```

1. **Apresentação (Presentation Tier):**
    
    - **Função:** Captura interações do usuário e exibe dados.
        
    - **Tecnologias:** HTML/CSS/JS, React, VueJS, Angular, Flutter, iOS/Android.
        
2. **Lógica de Negócio (Application / Business Tier):**
    
    - **Função:** Executa validações, cálculos, fluxos de trabalho e processamento principal da aplicação.
        
    - **Tecnologias:** Java (Spring), C# (.NET), Python (Django/FastAPI), Node.js, Servidores de Aplicação.
        
3. **Dados (Data Tier):**
    
    - **Função:** Armazenamento, persistência e gerenciamento de transações.
        
    - **Tecnologias:** Oracle, PostgreSQL, MySQL, MongoDB, Redis.
        

### D. ==N Camadas== (N > 3)

Em sistemas complexos, a camada intermediária pode ser subdividida em múltiplas camadas especializadas:

- **Camada de Apresentação (UI)**
    
- **Camada de Fachada / API Gateway** (Roteamento, autenticação, rate-limiting)
    
- **Camada de Serviços / Aplicação** (Orquestração de casos de uso)
    
- **Camada de Domínio / Regras de Negócio** (Lógica do sistema puro)
    
- **Camada de Acesso a Dados / Persistência (DAO/Repository)**
    
- **Camada de Banco de Dados / Armazenamento**
    

## Características Principais das N Camadas

- **Acoplamento Fraco (_Loose Coupling_):** As camadas se comunicam através de interfaces bem definidas (APIs, DTOs, Contratos).
    
- **Comunicação Unidirecional / Em Cascata:** Uma camada superior geralmente consome serviços apenas da camada imediatamente inferior a ela.
    
- **Encapsulamento:** Mudar o SGBD (ex: de Oracle para PostgreSQL) na camada de dados não afeta a camada de apresentação.
    

## Vantagens e Desvantagens

| **Vantagens**                                                                                           | **Desvantagens**                                                                                                  |
| ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Manutenibilidade:** Alterações em uma camada raramente quebram outras.                                | **Complexidade:** Mais overhead de rede e infraestrutura.                                                         |
| **Escalabilidade Independente:** A camada de aplicação pode ser escalada sem precisar mudar a de dados. | **Latência:** Chamadas de rede entre várias camadas físicas reduzem o desempenho bruto.                           |
| **Reutilização:** Múltiplas UIs (Web, Mobile) consomem a mesma camada de negócio.                       | **Desenvolvimento Inicial:** Requer maior tempo de arquitetura e configuração inicial.                            |
| **Segurança:** O cliente nunca acessa o Banco de Dados diretamente.                                     | **Efeito de Repasse (_Sinkhole Effect_):** Algumas chamadas passam por todas as camadas sem adicionar valor real. |

## N Camadas vs. Outros Padões Arquiteturais

|**Conceito**|**N Camadas (N-Tier)**|**Microsserviços**|**MVC (Model-View-Controller)**|
|---|---|---|---|
|**Foco**|Divisão de infraestrutura e responsabilidade em camadas físicas/lógicas.|Divisão do sistema por domínios de negócio autônomos.|Padrão de projeto/UI para estruturação interna de código.|
|**Implantação**|Geralmente implantação monolítica por camada.|Deploys independentes para cada serviço.|Executa dentro do mesmo processo da aplicação.|
|**Escopo**|Arquitetura de Infraestrutura / Sistema.|Arquitetura de Sistemas Distribuídos.|Padrão de Arquitetura de Software/Design de UI.|

## Resumo Rápido para Provas de Concursos

1. **Definição de _Tier_:** Refere-se à distribuição física (máquinas/servidores distintos).
    
2. **Definição de _Layer_:** Refere-se à separação lógica no código.
    
3. **Isolamento e Segurança:** Melhora a segurança pois a camada de apresentação não se comunica diretamente com o Banco de Dados.
    
4. **Comunicação:** Geralmente síncrona (HTTP/REST, gRPC) ou assíncrona (mensageria/eventos).
    
5. **Acesso a Dados:** Utiliza frameworks de persistência e ORM na camada de dados/Acesso a Dados.