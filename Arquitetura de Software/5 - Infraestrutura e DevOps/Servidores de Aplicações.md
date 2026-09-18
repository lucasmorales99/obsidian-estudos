#devops

# 📚 Guia Didático: Servidores de Aplicações em Arquitetura de Software

## 1. O Conceito Fundamental e Localização na Arquitetura

Na arquitetura clássica de **3 ou N Camadas (N-Tier)**, o **Servidor de Aplicação** reside na **Camada Intermediária / Lógica de Negócio** (_Business / Application Tier_).

```
[ Cliente / Browser / SPA ]
           │ (HTTP / HTTPS / REST / JSON)
           ▼
  [ Servidor Web (Web Server) ]
           │ (Forwarding / Proxy Reverso / AJP)
           ▼
[ SERVIDORES DE APLICAÇÃO ] ───► (Executa Regras de Negócio, Conexões, Transações)
           │ (SQL / JDBC / Driver)
           ▼
 [ Banco de Dados / SGBD ]
```

### Web Server vs. Application Server (Diferença Crucial em Provas)

- **Servidor Web (_Web Server_):**
    
    - **Foco:** Entregar conteúdo estático (HTML, CSS, imagens, arquivos JS) e gerenciar requisições HTTP[cite: 1, 3].
        
    - **Exemplos:** Nginx, Apache HTTP Server, IIS.
        
- **Servidor de Aplicação (_Application Server_):**
    
    - **Foco:** Executar código dinâmico da lógica de negócios, gerenciar o ciclo de vida de componentes do lado do servidor, prover controle transacional e gerenciar conexões.
        
    - **Suporte a Protocolos:** Suporta HTTP/HTTPS, mas também lida com protocolos de baixo nível/corporativos (como RMI, gRPC, JMS, IIOP).
        
    - **Exemplos:** WildFly (JBoss), GlassFish, Apache TomEE, IBM WebSphere, Oracle WebLogic.
        

> 💡 _Nota do Professor:_ Em arquiteturas legadas ou corporativas Java EE / Jakarta EE, o **Apache Tomcat** é classificado estritamente como um **Web Container / Servlet Container** (gerencia apenas Servlets e JSPs), enquanto o **WildFly** ou **WebLogic** são Servidores de Aplicação completos (_Full Profile_).

## 2. Serviços e Funcionalidades Providos pelo Servidor de Aplicação

O grande valor de um Servidor de Aplicação para a arquitetura é abstrair a infraestrutura para o desenvolvedor. Em vez de reescrever a gestão de rede e memória, o servidor de aplicação provê nativamente:

1. **Gerenciamento do Ciclo de Vida de Componentes:** Instancia, gerencia a memória, executa e destrói objetos de negócios conforme necessário.
    
2. **Pool de Conexões com Banco de Dados (_Connection Pooling_):** Mantém um conjunto de conexões pré-estabelecidas com o SGBD abertas para reutilização por threads concorrentes, reduzindo drasticamente a latência e o custo de abertura de conexões TCP/SQL.
    
3. **Gestão de Transações Distribuídas:** Suporta gerenciamento de transações que envolvem múltiplos bancos de dados ou filas (ex: via protocolo 2PC / _Two-Phase Commit_ ou especificações como JTA).
    
4. **Segurança e Autenticação:** Centraliza políticas de autenticação, autorização baseada em papéis (RBAC) e criptografia.
    
5. **Comunicação Assíncrona e Mensageria:** Integração nativa com barramentos de mensagens/filas (ex: JMS).
    
6. **Agendamento de Tarefas e Concorrência:** Gerencia o paralelismo de requisições por meio de _pools_ de threads dedicados.
    

## 3. O Papel do Servidor de Aplicação em Arquiteturas Modernas

Como se comporta o Servidor de Aplicação na transição entre arquiteturas Monolíticas e Microsserviços?

### A. Cenário Monolítico / Enterprise Tradicional

Aplicações pesadas (ex: Java EE / Jakarta EE em arquivos `.ear` ou `.war`) eram implantadas diretamente em clusters de Servidores de Aplicação grandes e centralizados (como Oracle WebLogic ou WebSphere). A escalabilidade era **vertical** (aumentar RAM/CPU do servidor) ou por **clusters de grande porte**.

### B. Cenário Cloud Native, Contêineres e Microsserviços

Com a chegada da conteinerização (Docker) e do Kubernetes:

- Os Servidores de Aplicação pesados foram substituídos por **runtimes e frameworks leves / embutidos** (_Embedded Application Servers_).
    
- Em vez de instalar o servidor na máquina e implantar a aplicação nele, a própria aplicação carrega o servidor de aplicação embutido no seu executável (ex: **Spring Boot** com Tomcat/Jetty embutido ou **Quarkus** / **Micronaut**).
    
- Cada microsserviço roda em seu próprio contêiner isolado, facilitando a escalabilidade **horizontal**.
    

## 4. Alta Disponibilidade, Clusterização e Tolerância a Falhas

Na camada de infraestrutura, os servidores de aplicação precisam garantir disponibilidade e resiliência:

- **Cluster de Servidores de Aplicação:** Várias instâncias do servidor de aplicação rodando em paralelo para dividir a carga de trabalho.
    
- **Replicação de Sessão (_Session Replication_):** Garantir que o estado da sessão HTTP do usuário seja compartilhado entre as instâncias do cluster (ou persistido em cache externo como Redis), permitindo _failover_ transparente se um servidor cair.
    
- **Balanceamento de Carga (_Load Balancing_):** Um _Web Server_ ou _API Gateway_ fica na frente distribuindo as requisições entre as instâncias disponíveis usando algoritmos como _Round-Robin_, _Least Connections_ ou _IP Hash_.
    

## 5. Resumo Executivo para Provas e Concursos

1. **Camada de Lógica de Negócio:** O Servidor de Aplicação é projetado para processar código dinâmico e regras de negócio na camada intermediária de sistemas N-Tier.
    
2. **Servidor Web vs. Servidor de Aplicação:** O Servidor Web gerencia requisições HTTP e arquivos estáticos[cite: 1]; o Servidor de Aplicação fornece serviços de infraestrutura complexos (Pool de conexões, transações distribuídas, segurança, mensageria).
    
3. **Padrão Moderno (Embedded):** Em arquiteturas de microsserviços e Cloud Native, o servidor de aplicação deixa de ser uma infraestrutura externa e passa a ser embutido diretamente na própria aplicação dentro de um contêiner Docker.