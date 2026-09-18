#devops

# 📚 Guia Didático: Cloud Native e Conteinerização (Docker e Kubernetes)

## 1. O Conceito de Cloud Native (Nativo da Nuvem)

Ser **Cloud Native** não significa apenas "executar sistemas em um servidor na nuvem" (o chamado _Lift-and-Shift_). Trata-se de uma **abordagem arquitetural** projetada para construir e executar aplicações explorando totalmente o modelo de computação em nuvem (escalabilidade dinâmica, resiliência e flexibilidade).

### Os Pilares do Cloud Native (CNCF - Cloud Native Computing Foundation):

1. **Microsserviços:** Aplicações divididas em pequenos serviços autônomos por domínio de negócio.
    
2. **Conteinerização:** Empacotamento de software e suas dependências em unidades isoladas.
    
3. **Gerenciamento Dinâmico (Orquestração):** Automatizado por orquestradores (ex: Kubernetes).
    
4. **DevOps e CI/CD:** Integração e entrega contínuas para automação de testes e deploys rápidos.
    

## 2. Conteinerização com Docker

A **conteinerização** é a técnica de isolar uma aplicação e todo o seu ambiente de execução (bibliotecas, arquivos de configuração, runtime) em um contêiner padronizado.

### A. Diferença Chave: Virtualização (VMs) vs. Conteinerização

- **Máquinas Virtuais (VMs):** Cada VM possui seu próprio sistema operacional convidado (_Guest OS_) completo sobre um _Hypervisor_. Isso gera alto consumo de memória, disco e tempo de inicialização lento.
    
- **Contêineres (Docker):** Compartilham o **Kernel do Sistema Operacional hospedeiro**. Cada contêiner executa como um processo isolado no _User Space_, tornando-o leve, rápido para inicializar (segundos) e altamente eficiente no uso de recursos.
    

### B. Conceitos Fundamentais do Docker

- **Dockerfile:** Arquivo de declaração em texto plano com as instruções passo a passo para construir uma imagem (ex: imagem base, comandos de instalação, portas de rede e ponto de entrada).
    
- **Imagem (Docker Image):** Modelo somente leitura (_read-only_) empacotado que contém o código, runtime e bibliotecas da aplicação.
    
- **Contêiner (Docker Container):** A instância em execução de uma Imagem Docker. É um processo isolado no ambiente hospedeiro.
    
- **Registry (Repositório):** Local onde as imagens são armazenadas e distribuídas (ex: Docker Hub, AWS ECR).
    

## 3. Orquestração de Contêineres com Kubernetes (K8s)

Quando a arquitetura cresce e passa a ter dezenas ou centenas de contêineres Docker espalhados por múltiplos servidores, gerenciá-los manualmente torna-se inviável. É aqui que entra o **Kubernetes (K8s)**: um orquestrador open-source para automatizar a implantação, o dimensionamento e a gestão de aplicações em contêineres.

### A. Arquitetura do Cluster Kubernetes

Um cluster Kubernetes é dividido em dois planos:

1. **Control Plane (Master Node):** O "cérebro" do cluster.
    
    - **kube-apiserver:** Ponto central de entrada da API do K8s (recebe comandos do `kubectl` e de outros componentes).
        
    - **etcd:** Banco de dados chave-valor distribuído que armazena todo o estado do cluster.
        
    - **kube-scheduler:** Decide em qual nó do cluster um novo Pod deve ser alocado.
        
    - **kube-controller-manager:** Garante que o estado atual do cluster seja igual ao estado desejado.
        
2. **Worker Nodes:** As máquinas (físicas ou virtuais) que realmente executam as aplicações.
    
    - **kubelet:** Agente em cada nó que garante que os contêineres estejam rodando conforme instruído pelo Control Plane.
        
    - **kube-proxy:** Gerencia as regras de rede nos nós e faz o balanceamento de carga entre Pods.
        
    - **Container Runtime:** O motor que executa os contêineres (ex: `containerd`).
        

### B. Principais Abstrações/Objetos do Kubernetes

- **Pod:** A menor unidade implantável no Kubernetes. Um Pod encapsula um ou mais contêineres que compartilham o mesmo endereço IP, armazenamento e recursos de rede.
    
- **Deployment:** Objeto que gerencia o ciclo de vida e o estado dos Pods (permite definir o número de réplicas, atualizações graduais/_rolling updates_ e _rollbacks_).
    
- **Service:** Fornece um ponto de acesso fixo (IP estável e nome DNS) e balanceamento de carga para um grupo de Pods dinâmicos.
    
    - _ClusterIP:_ Acesso apenas interno ao cluster.
        
    - _NodePort:_ Expõe o serviço em uma porta fixa em cada nó do cluster.
        
    - _LoadBalancer:_ Integra-se ao provedor de nuvem para criar um balanceador externo.
        
- **ConfigMap / Secret:** Mecanismos para separar configurações e senhas/chaves da imagem da aplicação.
    
- **Ingress:** Gerencia o acesso externo aos serviços (normalmente tráfego HTTP/HTTPS), atuando como um roteador de camada 7 (com suporte a TLS/SSL e nomes de domínio).
    

## 4. Recursos Nativos e Resiliência no K8s

- **Auto-healing (Auto-recuperação):** Se um Pod ou nó falhar, o Kubernetes automaticamente reinicia ou recria o Pod em outro nó saudável.
    
- **Autoscaling (HPA - Horizontal Pod Autoscaler):** Aumenta ou diminui o número de réplicas de Pods automaticamente com base no uso de CPU, memória ou métricas customizadas.
    
- **Rolling Updates:** Permite atualizar a versão de um software sem indisponibilidade (_zero downtime_), substituindo gradualmente Pods antigos por novos.
    

## 5. Resumo Executivo para Provas e Concursos

1. **Cloud Native:** Focado em explorar ao máximo os recursos da nuvem usando microsserviços, contêineres, orquestração e automação (DevOps).
    
2. **Contêineres vs VMs:** Contêineres compartilham o Kernel do sistema operacional hospedeiro, tornando-os mais leves e ágeis do que máquinas virtuais convencionais.
    
3. **Docker:** Ferramenta para **criar e empacotar** aplicações em imagens isoladas.
    
4. **Kubernetes:** Ferramenta para **orquestrar, escalar e manter a alta disponibilidade** de contêineres em um cluster distribuído.
    
5. **Pod:** Menor objeto manipulável no K8s; pode conter um ou mais contêineres compartilhando rede e volume.