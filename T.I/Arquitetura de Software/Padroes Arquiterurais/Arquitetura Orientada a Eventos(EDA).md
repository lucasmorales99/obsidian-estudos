
A **Arquitetura Orientada a Eventos (_Event-Driven Architecture_ — EDA)** é um padrão no qual os componentes do sistema se comunicam de forma **assíncrona** reagindo à produção e ao consumo de eventos.

## 1. O Conceito Fundamental de Evento

- **O que é um Evento?** É a declaração ou registro imutável de um fato relevante ocorrido no sistema (ex.: `PedidoCriado`, `PagamentoAprovado`, `EstoqueAtualizado`).
    
- **Inversão de Dependência:** Em vez de um serviço A chamar o serviço B diretamente (requisição/resposta síncrona), o serviço A apenas notifica que algo aconteceu. Os serviços interessados reagem de forma **assíncrona**.
    

## 2. Componentes e Atores da Arquitetura

- **Produtores (Publishers/Producers):** Detectam uma mudança de estado ou ação do usuário e publicam o evento no barramento de eventos ou broker de mensageria.
    
- **Canal/Broker de Mensageria (Event Broker):** Infraestrutura responsável por receber, armazenar e rotear os eventos até os interessados (ex.: Apache Kafka, RabbitMQ, AWS SNS/SQS).
    
- **Consumidores (Subscribers/Consumers):** Componentes ou serviços que escutam e reagem aos eventos processando-os conforme a sua própria regra de negócio.
    

## 3. Topologias e Padrões de Comunicação

### A. Topologia Publish/Subscribe (Pub/Sub)

- Um único evento emitido por um produtor pode ser entregue e processado em paralelo por múltiplos consumidores interessados, sem que o produtor precise conhecer quem são os receptores.
    

### B. Event Streaming

- Os eventos são gravados em uma ordem cronológica (_log_ de dados) e mantidos por um tempo. Consumidores podem ler o fluxo (_stream_) no seu próprio ritmo e processar dados em tempo real ou reprocessar dados passados (ex.: Apache Kafka).
    

### C. Padrões Avançados para Concursos e Arquitetura

- **Event Sourcing:** Em vez de salvar apenas o estado atual da entidade no banco de dados, o sistema armazena **todas as mudanças como uma sequência ordenada de eventos**. O estado atual é reconstruído executando esse histórico de eventos.
    
- **CQRS (Command Query Responsibility Segregation):** Separa as operações de escrita (comandos) e leitura (consultas) no banco de dados. Frequentemente utilizado junto a EDA e _Event Sourcing_.
    
- **Padrão Outbox (Transactional Outbox):** Garante a consistência transacional ao gravar o evento na mesma transação de banco de dados do negócio antes de enviá-lo ao broker de mensageria.
    

## 4. Vantagens e Desvantagens

|**Vantagens**|**Desvantagens**|
|---|---|
|**Acoplamento Extremamente Fraco:** Produtores e consumidores funcionam sem saber da existência uns dos outros.|**Complexidade de Rastreamento:** Dificuldade em debugar fluxos que atravessam múltiplos eventos (necessita de _Distributed Tracing_).|
|**Escalabilidade e Desempenho:** Processamento não bloqueante (assíncrono), permitindo que requisições pesadas ocorram em segundo plano.|**Consistência Eventual:** O estado dos dados pode não estar sincronizado instantaneamente em todo o sistema.|
|**Alta Resiliência:** Se um consumidor cair, as mensagens ficam salvas na fila/stream até que ele se restabeleça.|**Garantias de Entrega:** Lidar com idempotência (evitar que o mesmo evento altere o sistema duas vezes).|

## 5. Resumo Rápido para Questões de Prova

1. **Assincronismo:** A comunicação é predominantemente assíncrona baseada na ocorrência de **fatos** (eventos).
    
2. **Serviços de Mensageria:** É fortemente associada ao uso de serviços de mensageria e _Event Brokers_.
    
3. **Consistência Eventual (_Eventual Consistency_):** Em contraste com transações ACID estritas distribuídas, sistemas baseados em eventos aceitam um tempo de propagação até a sincronização completa do estado.
    
4. **Resiliência:** Reduz a propagação de falhas em cascata; se o receptor estiver fora do ar, a fila retém a mensagem até o reestabelecimento do serviço.