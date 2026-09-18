#devops #infraestrutura

# 📚 Guia Didático: Integração e Implantação Contínua (CI/CD)

## 1. O Conceito Fundamental e Objetivos

O conceito de **CI/CD** é um conjunto de práticas e automações que visa entregar código em produção de forma rápida, segura e frequente. Trata-se da ponte direta entre o desenvolvimento de software e a infraestrutura de operações.

- **CI (Continuous Integration / Integração Contínua):** É a prática em que os desenvolvedores mesclam suas alterações de código frequentemente em um repositório central (ex: Git). A cada _commit_ ou _pull request_, um _pipeline_ automatizado compila (build) a aplicação e executa testes automatizados para identificar falhas o mais cedo possível (_Shift-Left Testing_).
    
- **CD (Continuous Delivery / Entrega Contínua):** Garante que o código validado no processo de CI esteja sempre pronto para ser implantado em produção a qualquer momento. A etapa final de envio para produção depende de uma **aprovação manual**.
    
- **CD (Continuous Deployment / Implantação Contínua):** Leva o conceito um passo adiante: todas as alterações que passam com sucesso pelas etapas de validação e testes são **implantadas automaticamente em produção** sem intervenção humana manual.
    

## 2. As Fases de um Pipeline de CI/CD

Um _Pipeline_ de CI/CD é a representação em etapas do fluxo de automação:

```
[ Código (Git) ] ──> [ 1. Build ] ──> [ 2. Testes ] ──> [ 3. Segurança ] ──> [ 4. Artefato ] ──> [ 5. Deploy ]
```

1. **Gatilho (Source / Trigger):** Alteração enviada para o controle de versão (Git).
    
2. **Construção (Build):** Compilação do código e resolução de dependências. Em arquiteturas modernas, envolve a geração de uma imagem de contêiner (ex: Docker).
    
3. **Testes (Test):** Execução de testes unitários, de integração e funcionais.
    
4. **Análise de Segurança e Qualidade (SAST / SonarQube):** Validação estática de código e checagem de vulnerabilidades em dependências.
    
5. **Empacotamento e Repositório de Artefatos:** Armazenamento do binário/imagem gerada em um _registry_ (ex: Docker Hub, AWS ECR, Nexus).
    
6. **Implantação (Deploy):** Publicação da aplicação no ambiente de destino (Desenvolvimento, Staging ou Produção) utilizando orquestradores como Kubernetes ou servidores tradicionais.
    

## 3. Estratégias de Deploy na Infraestrutura

Em infraestrutura e arquitetura de software, a forma como o código entra em produção impacta diretamente a disponibilidade do sistema. As principais estratégias são:

### A. Deploy Blue/Green (Azul/Verde)

- **Como funciona:** Mantém dois ambientes idênticos de infraestrutura (Blue = versão atual em produção, Green = nova versão). A nova versão é implantada no ambiente Green. Após validação, o roteador/load balancer redireciona o tráfego do Blue para o Green.
    
- **Vantagens:** _Downtime_ zero e _rollback_ instantâneo (basta redirecionar o tráfego de volta para o Blue em caso de falha).
    

### B. Deploy Canary (Canário)

- **Como funciona:** A nova versão é implantada em uma pequena fração de servidores/instâncias (ex: 5% ou 10% dos usuários). Conforme os métricas de saúde e erros se mantêm estáveis, a porcentagem de tráfego aumenta gradualmente até cobrir 100% da infraestrutura.
    
- **Vantagens:** Minimiza o impacto de falhas em produção atingindo apenas uma pequena parcela de usuários finais.
    

### C. Deploy Rolling (Gradual)

- **Como funciona:** Atualiza as instâncias da aplicação sequencialmente (uma por uma ou em pequenos lotes) no mesmo cluster (ex: _Rolling Update_ nativo do Kubernetes).
    
- **Vantagens:** Não exige o dobro de infraestrutura (diferente do Blue/Green), mantendo a capacidade do ambiente balanceada.
    

## 4. Ecossistema de Ferramentas

Para construir um ecossistema completo de CI/CD na infraestrutura, utilizam-se diversas ferramentas especializadas:

- **Servidores de CI/CD / Automation Servers:** GitHub Actions, GitLab CI/CD, Jenkins, Azure DevOps, Bitbucket Pipelines.
    
- **Gerenciamento de Artefatos e Imagens:** Docker Hub, GitHub Container Registry, AWS ECR, Nexus.
    
- **Orquestração e Execução:** Docker, Kubernetes.
    
- **GitOps e CD em Kubernetes:** ArgoCD, FluxCD (ferramentas que sincronizam o estado declarado no Git com o cluster).
    

## 5. Resumo Executivo para Provas e Concursos

1. **Diferença Chave:** **CI** foca em compilar e testar; **Continuous Delivery** deixa o software pronto para deploy (aprovação manual); **Continuous Deployment** realiza o deploy em produção de forma 100% automatizada.
    
2. **Pilar do DevOps:** CI/CD é a técnica central para automação, integração contínua e ciclos rápidos de entrega em ambientes de infraestrutura modernos.
    
3. **Estratégias de Deploy:** _Blue/Green_ foca em alternar tráfego entre ambientes paralelos; _Canary_ foca em liberar novidades para uma porcentagem reduzida de usuários.
    
4. **Relacionamento com Contêineres:** A arquitetura Cloud Native favorece pipelines que empacotam aplicações em contêineres Docker para implantação em clusters.