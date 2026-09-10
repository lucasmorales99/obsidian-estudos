As **APIs (_Application Programming Interfaces_)** e seus padrões de troca de dados (REST, SOAP, gRPC, JSON) são o pilar de comunicação entre sistemas modernos, microsserviços e integração de aplicações.

Abaixo está o guia focado nesses tópicos da arquitetura de software:

# Guia de Estudos: APIs (REST, SOAP, gRPC, JSON)

## 1. REST (_Representational State Transfer_)

REST é um estilo arquitetural (e não um protocolo) que utiliza os padrões nativos da Web (HTTP) para comunicação.

- **Princípios/Constraints do REST:**
    
    1. **Cliente-Servidor:** Separação clara de responsabilidades entre interface e processamento backend.
        
    2. **Stateless (Sem Estado):** Cada requisição do cliente deve conter todas as informações necessárias para ser processada; o servidor não guarda estado da sessão entre requisições.
        
    3. **Cacheable:** As respostas devem explicitar se podem ou não ser armazenadas em cache pelo cliente.
        
    4. **Interface Uniforme:** Identificação de recursos através de URIs e manipulação via verbos HTTP padronizados.
        
    5. **Sistema em Camadas (_Layered System_):** O cliente não sabe se está conectado diretamente ao servidor final ou a um intermediário (como _Load Balancer_ ou _API Gateway_).
        
- **Verbos HTTP Principais:** `GET` (leitura), `POST` (criação), `PUT` (atualização completa), `PATCH` (atualização parcial), `DELETE` (remoção).
    
- **Nível de Maturidade de Richardson (Modelo Nível 0 a 3):**
    
    - _Nível 0:_ Uso do HTTP apenas como meio de transporte (RPC sobre HTTP).
        
    - _Nível 1:_ Uso de Recursos (URIs individuais para cada entidade).
        
    - _Nível 2:_ Uso correto dos Verbos HTTP e Códigos de Status HTTP (`200 OK`, `201 Created`, `404 Not Found`, etc.).
        
    - _Nível 3:_ **HATEOAS** (_Hypermedia As The Engine Of Application State_) — A resposta inclui links com as próximas ações possíveis a partir daquele recurso.
        

## 2. SOAP (_Simple Object Access Protocol_)

SOAP é um **protocolo rigoroso e padronizado** baseado inteiramente em **XML** para troca de informações estruturadas.

- **Características Principais:**
    
    - **Protocolo Estrito:** Define regras rígidas de mensagem e segurança.
        
    - **Formato das Mensagens:** Utiliza envelopes XML estruturados composta por `<Envelope>`, `<Header>` (opcional) e `<body>`.
        
    - **WSDL (_Web Services Description Language_):** Documento em XML que funciona como o contrato estrito da API, detalhando todas as operações, parâmetros e tipos de dados aceitos.
        
    - **Independência de Protocolo:** Embora seja frequentemente usado sobre HTTP/HTTPS, pode operar sobre SMTP, TCP, JMS, etc.
        
    - **Padrões de Segurança (WS-Security):** Suporta criptografia e assinaturas de mensagens nativas no nível de aplicação.
        
- **Uso Típico:** Sistemas bancários antigos, integrações governamentais e ambientes corporativos legados que exigem garantias rígidas de contrato e segurança.
    

## 3. gRPC (_Google Remote Procedure Call_)

gRPC é um framework moderno de RPC (_Remote Procedure Call_) de **altíssimo desempenho**, desenvolvido pelo Google.

- **Características Principais:**
    
    - **Protocolo HTTP/2:** Utiliza multiplexação de requisições sobre uma única conexão TCP, permitindo _streaming_ bidirecional (cliente/servidor) com baixíssima latência.
        
    - **Protocol Buffers (Protobuf):** Utiliza um formato binário compacto em vez de texto plano (JSON/XML). É muito mais rápido para serialização e desserialização e usa significativamente menos largura de banda.
        
    - **Arquivos `.proto`:** Arquivos de definição nos quais o contrato de serviço e os tipos de dados são declarados. A partir desses arquivos, o código de cliente/servidor é gerado automaticamente em diversas linguagens (C#, Java, Go, Python, etc.).
        
- **Modos de Comunicação:**
    
    1. _Unary RPC:_ O cliente envia uma requisição e recebe uma resposta (estilo tradicional).
        
    2. _Server Streaming:_ O cliente envia uma requisição e o servidor responde com um fluxo contínuo de dados.
        
    3. _Client Streaming:_ O cliente envia um fluxo contínuo de dados e o servidor responde uma vez.
        
    4. _Bi-directional Streaming:_ Ambos enviam fluxos de dados de forma independente.
        
- **Uso Típico:** Comunicação de **baixa latência entre microsserviços internos (East-West traffic)**.
    

## 4. Formatos de Dados: JSON vs. XML

- **JSON (_JavaScript Object Notation_):**
    
    - Formato leve de intercâmbio de dados baseado em pares **chave/valor** e **listas**.
        
    - Altamente legível por humanos e facilmente processado nativamente por navegadores e linguagens modernas.
        
    - Formato padrão utilizado por APIs REST.
        
- **XML (_eXtensible Markup Language_):**
    
    - Formato baseado em **tags** e metadados.
        
    - Suporta validação rígida através de Schemas (`.xsd`) e transformações complexas (`XSLT`).
        
    - Formato obrigatório no SOAP.
        

## 5. Tabela Comparativa de APIs

| **Característica**     | **REST**                                   | **SOAP**                                     | **gRPC**                                 |
| ---------------------- | ------------------------------------------ | -------------------------------------------- | ---------------------------------------- |
| **Estilo / Protocolo** | Estilo Arquitetural (geralmente sob HTTP)  | Protocolo Estrito                            | Framework RPC (sob HTTP/2)               |
| **Formato de Dados**   | JSON (principal), XML, HTML, Texto         | Exclusivamente XML                           | Protocol Buffers (Binário)               |
| **Contrato de API**    | Opcional (OpenAPI / Swagger)               | Obrigatório (WSDL)                           | Obrigatório (Arquivos `.proto`)          |
| **Desempenho**         | Médio / Alto                               | Baixo (devido ao XML verboso)                | **Extremamente Alto** (binário + HTTP/2) |
| **Streaming**          | Limitado (Server-Sent Events / WebSockets) | Não                                          | Sim (Nativo e Bidirecional)              |
| **Caso de Uso Ideal**  | APIs públicas e integração Web/Mobile      | Integrações corporativas legadas e bancárias | Comunicação interna entre microsserviços |

## 6. Resumo Rápido para Questões de Concurso

1. **REST é Stateless:** O servidor não mantém o estado da sessão do cliente entre chamadas.
    
2. **WSDL e SOAP:** Sempre que citar WSDL, XML Envelope ou WS-Security, a resposta refere-se ao **SOAP**.
    
3. **Protobuf e gRPC:** O gRPC utiliza **Protocol Buffers** para serializar dados de forma binária e roda prioritariamente sobre **HTTP/2**.
    
4. **HATEOAS:** É a característica que define o nível máximo de maturidade do REST (Nível 3 do Modelo Richardson).
    
5. **JSON:** É o formato padrão para payloads REST devido ao menor _overhead_ de processamento e tamanho se comparado ao XML.