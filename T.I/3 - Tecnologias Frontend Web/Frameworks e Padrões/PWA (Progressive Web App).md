#frameworks

### 🎓 Aula: Arquitetura, Padrões e Componentes de um PWA

#### 1. O que é um Progressive Web App (PWA)?

Um **PWA** não é uma nova linguagem de programação nem um _framework_ isolado, mas sim um **conjunto de tecnologias _web_ e padrões de arquitetura** (HTML, CSS, JavaScript) que transformam uma aplicação _web_ tradicional ou SPA (_Single Page Application_) em um aplicativo instalável, seguro e capaz de rodar offline.

- **Princípio da Progressividade:** A aplicação deve funcionar em qualquer navegador. Em navegadores antigos, funciona como um site convencional; em navegadores modernos, libera recursos avançados (como atalhos nativos, _push notifications_ e cache offline).
    

#### 2. Os Três Pilares Técnicos de um PWA

Para que uma aplicação _web_ seja considerada um PWA completo, ela deve implementar obrigatoriamente três requisitos:

##### A. Service Worker (O Coração do PWA)

O **Service Worker** é um _script_ JavaScript que roda em segundo plano, totalmente separado da _thread_ principal da interface do navegador.

- **Atuação como Proxy Interceptador:** Ele atua entre a aplicação _web_, a rede e o cache do navegador.
    
- **Recursos Offline:** Permite interceptar requisições de rede (via requisições assíncronas / Ajax) e responder com recursos salvos localmente quando o usuário está sem internet.
    
- **Tarefas em Segundo Plano:** Gerencia _Push Notifications_ (notificações nativas) e sincronização de dados em _background_.
    

##### B. Web App Manifest (`manifest.json`)

É um arquivo de configuração estruturado em **JSON** que diz ao sistema operacional como o aplicativo deve se comportar ao ser instalado.

- Define o nome da aplicação, ícones para a tela inicial, cores de tema, orientação de tela (retrato/paisagem) e o modo de exibição (ex: `standalone`, para ocultar as barras e menus do navegador).
    

##### C. Conexão Segura via HTTPS

PWAs exigem obrigatoriamente o protocolo **HTTPS**. Como o _Service Worker_ pode interceptar requisições e manipular conexões de rede, o HTTPS garante a integridade dos dados e previne ataques de interceptação (_Man-in-the-Middle_).

#### 3. Padrões Arquiteturais no PWA

##### A. App Shell Model (Padrão de Arquitetura de Interface)

O padrão **App Shell** separa a estrutura básica da interface do usuário (cabeçalho, menu, rodapé) do seu conteúdo dinâmico.

- **Funcionamento:** O _Service Worker_ salva o "esqueleto" (_Shell_) da aplicação no cache local durante o primeiro acesso.
    
- **Resultado:** Nas visitas seguintes, a estrutura carrega instantaneamente, e o aplicativo busca apenas os dados dinâmicos da API via JSON/Ajax.
    

##### B. Padrões de Cache do Service Worker (_Caching Strategies_)

A gestão de dados no PWA depende do padrão de cache escolhido para cada tipo de recurso:

- **Cache First (Cache Primeiro):** Busca o recurso no cache local. Se não encontrar, vai à rede. Ideal para arquivos estáticos (CSS, imagens, fontes).
    
- **Network First (Rede Primeiro):** Tenta buscar o dado atualizado na rede. Se a conexão falhar, entrega a versão salva em cache. Ideal para dados dinâmicos de APIs.
    
- **Stale-While-Revalidate:** Entrega imediatamente a versão salva em cache (rápida) e, ao mesmo tempo, faz uma requisição em segundo plano para atualizar o cache com novos dados.
    

##### 📝 Resumo do Professor para Revisão Rápida

- **Definição:** Padrão _web_ para transformar sites em aplicações instaláveis e com recursos nativos.
    
- **Componente Chave:** **Service Worker** (script em segundo plano para interceptação de rede, suporte offline e _push notifications_).
    
- **Configuração:** **`manifest.json`** (arquivo JSON com metadados para instalação).
    
- **Segurança:** Exige **HTTPS** obrigatoriamente.
    
- **Padrão de UI:** **App Shell Model** (separação da estrutura da interface dos dados dinâmicos).