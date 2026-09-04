#microsserviços #arquitetura 

## 1. O Conceito Fundamental (Monólito vs. Microsserviços)

- **Arquitetura Monolítica:**
    
    - O sistema inteiro é construído e implantado como uma **única unidade**.
        
    - Todas as funcionalidades (autenticação, pagamentos, catálogo, relatórios) compartilham o mesmo projeto, processo de execução e, geralmente, o mesmo banco de dados.
        
    - **Problema:** À medida que o sistema cresce, fica difícil de manter, o _deploy_ torna-se arriscado (uma falha em um módulo pode derrubar o sistema inteiro) e escalar o sistema requer escalar todo o monólito.
        
- **Arquitetura de Microsserviços:**
    
    - A aplicação é dividida em **serviços independentes**, onde cada serviço é responsável por uma função específica do negócio (ex: _Serviço de Autenticação_, _Serviço de Pagamentos_, _Serviço de Notificações_).
        
    - Cada serviço pode ser desenvolvido, testado, implantado e escalado de forma totalmente autônoma.
        

## 2. Principais Características dos Microsserviços

1. **Autonomia e Implantação Independente:** É possível atualizar ou refatorar o _Serviço de Pagamentos_ sem precisar fazer redeploy ou parar os outros serviços.
    
2. **Descentralização de Dados (_Database per Service_):** Cada microsserviço deve ter o seu próprio banco de dados isolado. Um serviço jamais deve acessar o banco de dados de outro diretamente.
    
3. **Persistência Poliglota:** Diferentes serviços podem usar diferentes tecnologias de banco de dados (ex: Relacional/Oracle para transações financeiras e NoSQL/MongoDB para catálogo).
    
4. **Resiliência e Isolamento de Falhas:** Se o serviço de recomendações falhar, a loja virtual continua funcionando e permitindo compras.
    
5. **Comunicação Via APIs/Eventos:** Os serviços conversam entre si por meio de protocolos leves (HTTP/REST, gRPC) ou assíncronos (mensageria/eventos).
    

## 3. Padrões e Componentes Essenciais na Arquitetura

Para que um ecossistema de microsserviços funcione com eficiência, utilizam-se componentes e padrões auxiliares:

- **API Gateway:** Atua como o ponto único de entrada para requisições externas (clientes web/mobile), realizando roteamento, autenticação, controle de taxa (_rate limiting_) e agregação de respostas.
    
- **Service Discovery (Descoberta de Serviços):** Como as instâncias dos microsserviços podem subir e descer dinamicamente em contêineres, o _Service Discovery_ atua como uma "agenda" para que os serviços se localizem na rede de forma automática.
    
- **Serviços de Mensageria e Eventos (Event-Driven):** Utilizado para comunicação assíncrona entre serviços (ex: RabbitMQ, Apache Kafka) para evitar acoplamento síncrono rígido.
    
- **Conteinerização e Orquestração:** Utilização de **Docker** para empacotar os serviços e **Kubernetes** para gerenciar a execução, dimensionamento (_scaling_) e disponibilidade dos contêineres em nuvem (_cloud native_).
    
- **Circuit Breaker (Disjuntor):** Padrão que previne falhas em cascata interrompendo temporariamente as chamadas para um microsserviço que esteja indisponível ou instável.
    

## 4. Vantagens vs. Desvantagens

|**Vantagens**|**Desvantagens**|
|---|---|
|**Escalabilidade Granular:** Escala-se apenas o serviço que precisa de mais recursos.|**Complexidade Operacional:** Requer alto nível de automação (DevOps, CI/CD, observabilidade).|
|**Flexibilidade Tecnológica:** Cada serviço pode ser escrito na linguagem mais adequada (Java, Python, JS, Go).|**Complexidade na Gestão de Dados:** Manter consistência de dados entre múltiplos bancos é um desafio (necessita de padrões como _Saga_).|
|**Times Menores e Autônomos:** Múltiplas equipes podem trabalhar simultaneamente sem interferir umas nas outras.|**Latência e Overhead de Rede:** A comunicação via rede entre múltiplos serviços introduz latência.|
|**Resiliência:** A falha de um módulo isolado não paralisa o sistema por completo.|**Dificuldade em Testes de Integração:** Testar fluxos ponta a ponta exige gerenciar vários ambientes simultaneamente.|

## 5. Resumo Rápido para Provas e Concursos

- **Escopo:** Microsserviços é uma abordagem de **Sistemas Distribuídos** focada na decomposição de sistemas por **domínio de negócio**.
    
- **Banco de Dados:** O padrão ideal é **um banco de dados por microsserviço**.
    
- **Comunicação:** É realizada utilizando **APIs (REST, gRPC)** ou **Mensageria/Eventos** (comunicação assíncrona).
    
- **Entrada do Sistema:** O **API Gateway** unifica e protege o acesso externo aos microsserviços.
    
- **Infraestrutura:** É fortemente vinculada ao uso de **Contêineres** (Docker), **Cloud Native** e **DevOps (CI/CD)**