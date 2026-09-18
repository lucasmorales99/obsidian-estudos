#devops

# 📚 Guia Didático: Gerência de Configuração de Software (Git)

## 1. O Conceito de Gerência de Configuração de Software (GCS)

A **Gerência de Configuração de Software** é a disciplina da arquitetura e engenharia de software responsável por identificar, organizar, controlar e rastrear todas as alterações no código-fonte e nos artefatos do projeto ao longo de seu ciclo de vida.

### Principais Objetivos da GCS na Infraestrutura:

- **Rastreabilidade e Auditoria:** Saber _quem_, _quando_ e _por que_ uma linha de código ou arquivo de infraestrutura foi alterado.
    
- **Integridade e Consistência:** Garantir que o ambiente de produção execute exatamente o estado homologado do código, evitando surpresas em _deploys_.
    
- **Trabalho Colaborativo e Concorrente:** Permitir que múltiplos desenvolvedores e engenheiros de DevOps trabalhem simultaneamente no mesmo código sem sobrescrever o trabalho uns dos outros.
    
- **Reprodutibilidade:** Capacidade de "voltar no tempo" e restaurar a aplicação ou a infraestrutura para qualquer estado passado conhecido (_Rollback_).
    

## 2. Modelos de Controle de Versão: Centralizado vs. Distribuído

Para aplicar a GCS, utilizamos Sistemas de Controle de Versão (_VCS - Version Control System_).

- **Centralizado (ex: SVN, CVS):** Existe um único servidor central que armazena todo o histórico do código. Se o servidor central cair, ninguém consegue fazer _commits_ ou acessar o histórico.
    
- **Distribuído / DVCS (ex: Git):** Cada desenvolvedor possui uma **cópia completa** de todo o repositório e do seu histórico de alterações em sua máquina local. O servidor remoto (ex: GitHub, GitLab, Bitbucket) atua como um ponto de sincronização e backup centralizado, mas a perda temporária de conexão não impede o trabalho nem a consulta ao histórico local.
    

## 3. Arquitetura Interna e Fluxo de Trabalho do Git

Para compreender o Git em nível de arquitetura, é necessário entender suas **3 Áreas Locais de Trabalho** e o **Repositório Remoto**:

```
 ┌─────────────────────────────────────────────────────────┐
 │                     AMBIENTE LOCAL                      │
 │                                                         │
 │  [ Working Directory ] ──> [ Staging Area ] ──> [ Local ]│
 └─────────────────────────┬───────────────────────────────┘
                           │ git push
                           ▼
                 [ Remote Repository ]
```

1. **Working Directory (Diretório de Trabalho):** Os arquivos reais que você está editando no sistema de arquivos da sua máquina.
    
2. **Staging Area / Index (Área de Preparação):** Uma zona intermediária onde você seleciona e organiza quais arquivos ou alterações específicas farão parte do próximo _commit_ (`git add`).
    
3. **Local Repository (Repositório Local / `.git`):** Onde o Git armazena permanentemente os instantâneos (_snapshots_) do projeto após você confirmar o _commit_ (`git commit`).
    
4. **Remote Repository (Repositório Remoto):** O servidor centralizado na nuvem ou na infraestrutura corporativa onde os _commits_ locais são enviados (`git push`) para compartilhar com o time.
    

## 4. Comandos Essenciais do Git para a Infraestrutura

- **`git init` / `git clone`:** Inicializa um novo repositório local ou clona um repositório remoto existente.
    
- **`git status` / `git diff`:** Verifica o estado das alterações locais em relação à área de _staging_ ou ao último _commit_.
    
- **`git add <arquivo>`:** Move as alterações do _Working Directory_ para a _Staging Area_.
    
- **`git commit -m "mensagem"`:** Grava o instantâneo da _Staging Area_ no repositório local com uma mensagem explicativa.
    
- **`git fetch` vs. `git pull`:**
    
    - `git fetch`: Baixa as alterações do servidor remoto sem mesclá-las no seu código local.
        
    - `git pull`: Baixa as alterações e faz a mesclagem (_merge_) automática no seu ramo local atual.
        
- **`git checkout` / `git switch`:** Navega entre diferentes ramos (_branches_) ou restaura arquivos passados.
    

## 5. Estratégias de Ramificação (Branching Strategies)

Na Arquitetura de Software, definir uma **estratégia de branches** é vital para manter a estabilidade da infraestrutura e o fluxo contínuo de entregas.

### A. GitFlow

- **Como funciona:** Modelo estruturado baseado em ramificações de longa duração:
    
    - `main` / `master`: Contém o código estável em produção.
        
    - `develop`: Ramo principal onde a próxima versão é construída.
        
    - `feature/*`: Ramos temporários para criar novas funcionalidades (criadas a partir da `develop`).
        
    - `release/*`: Ramos de preparação para publicação em produção.
        
    - `hotfix/*`: Ramos urgentes para correção direta de bugs em produção.
        
- **Uso recomendado:** Projetos tradicionais com ciclos de lançamento (_releases_) bem definidos e agendados.
    

### B. Trunk-Based Development

- **Como funciona:** Todos os desenvolvedores fazem _commits_ frequentes (várias vezes ao dia) diretamente em um único ramo principal chamando `main` (o _trunk_), ou criam pequenas _feature branches_ de curtíssima duração (1 a 2 dias).
    
- **Uso recomendado:** Arquiteturas modernas com **CI/CD** e práticas de _Continuous Deployment_, onde pequenos testes automatizados garantem a estabilidade a cada integração.
    

## 6. Práticas de Integração e Rastreabilidade

- **Pull Requests (PR) / Merge Requests (MR):** Mecanismo de revisão de código (_code review_) antes que as alterações sejam mescladas no ramo principal. Permite a validação de regras de arquitetura e testes de segurança por pares.
    
- **Resolução de Conflitos:** Ocorre quando duas alterações modificam as mesmas linhas de um arquivo de formas incompatíveis. O Git sinaliza o conflito para que seja resolvido manualmente antes de concluir o _merge_.
    
- **GitOps:** Prática de infraestrutura moderna em que todo o estado da infraestrutura (arquivos descritores de Kubernetes, scripts Terraform, etc.) é gerenciado e versionado via Git. O Git atua como a **única fonte da verdade** (_Single Source of Truth_) para o ambiente operacional.
    

## 7. Resumo Executivo para Provas e Concursos

1. **Definição de GCS:** Disciplina para controlar, rastrear, organizar e auditar mudanças no software e na infraestrutura ao longo do tempo.
    
2. **Git é DVCS:** O Git é um sistema de controle de versão **distribuído**; cada nó tem a cópia integral do repositório localmente.
    
3. **Três Áreas do Git:** _Working Directory_ ➔ _Staging Area (Index)_ ➔ _Local Repository (.git)_.
    
4. **GitFlow vs. Trunk-Based:** GitFlow é voltado para entregas estruturadas e versionadas com múltiplos ramos; Trunk-Based foca em integração contínua (CI) com ciclo de vida curto em um único ramo principal.