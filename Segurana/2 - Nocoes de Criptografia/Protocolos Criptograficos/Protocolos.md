#cripto 
### 🎓 Aula: Protocolos Criptográficos no Padrão CEBRASPE

#### 1. SSL (Secure Sockets Layer) e TLS (Transport Layer Security)

O SSL e o TLS são os protocolos criptográficos mais cobrados em concursos para garantir segurança na comunicação pela Internet.

- **Camada de Atuação:** Atuam prioritariamente na **Camada de Transporte** (ou entre a camada de Aplicação e Transporte).
    
- **Evolução Histórica:** O SSL é o antecessor do TLS. Hoje, todas as versões do SSL (1.0, 2.0 e 3.0) e do TLS antigo (1.0 e 1.1) são consideradas **descontinuadas e vulneráveis**. O padrão de mercado seguro é o **TLS 1.2 e TLS 1.3**.
    
- **Como Funciona (Handshake SSL/TLS):**
    
    1. Utiliza **Criptografia Assimétrica** (Chave Pública/Certificado Digital) para autenticar o servidor e realizar a troca segura de chaves.
        
    2. Utiliza **Criptografia Simétrica** para cifrar a sessão e o tráfego de dados de fato (devido à velocidade e eficiência).
        
    3. Utiliza funções **Hash** para garantir a integridade das mensagens.
        

> ⚠️ **PEGADINHA DE PROVA (CEBRASPE):** A banca costuma dizer que o TLS utiliza _apenas_ criptografia assimétrica por ser mais segura. **ERRADO!** O TLS utiliza um **sistema híbrido**: assimétrica no estabelecimento do handshake e simétrica no tráfego dos dados!

#### 2. HTTPS (Hypertext Transfer Protocol Secure)

O HTTPS não é um protocolo novo, mas sim a combinação da aplicação **HTTP rodando sobre uma camada de proteção SSL/TLS**.

- **Porta Padronizada:** Opera por padrão na **porta TCP 443** (enquanto o HTTP convencional utiliza a porta TCP 80).
    
- **Garantias:** Assegura **Confidencialidade**, **Integridade** e **Autenticidade** na navegação Web.
    
- **Obrigatório para PWA:** Lembre-se das aulas de desenvolvimento web: PWAs (_Progressive Web Apps_) e _Service Workers_ exigem **obrigatoriamente** o uso de conexões HTTPS para funcionar com segurança.
    

#### 3. IPsec (Internet Protocol Security)

O IPsec é um conjunto de protocolos de segurança que atua na **Camada de Rede (Camada 3)** do modelo OSI/TCP-IP, sendo a base para a criação de redes privadas virtuais (**VPNs**).

- **Diferencial de Camada:** Como opera na camada de rede, ele protege **todo o tráfego de dados** entre dois nós (qualquer aplicação rodando acima dele é protegida transparentemente).
    
- **Dois Protocolos Principais do IPsec:**
    
    1. **AH (Authentication Header):** Garante **Autenticidade** e **Integridade**, mas **NÃO fornece Confidencialidade** (não cifra os dados).
        
    2. **ESP (Encapsulating Security Payload):** Garante **Confidencialidade**, **Autenticidade** e **Integridade** (cifra o conteúdo dos pacotes).
        
- **Dois Modos de Operação:**
    
    - **Modo Transporte:** Protege apenas a carga útil (_payload_) do pacote IP (o cabeçalho IP original é mantido).
        
    - **Modo Túnel:** Cifra o pacote IP **inteiro** (payload + cabeçalho original) e adiciona um novo cabeçalho IP. É o modo utilizado para construir **VPNs Site-to-Site**.
        

#### 4. SSH (Secure Shell)

O SSH é o protocolo criptográfico de aplicação utilizado para **acesso e gerenciamento remoto e seguro** de computadores e servidores.

- **Porta Padronizada:** Opera na **porta TCP 22**.
    
- **Substituto Seguro:** Foi criado para substituir protocolos antigos e inseguros em texto claro, como o **Telnet** e o **Rlogin**.
    
- **Copiando arquivos via SSH:** Utiliza utilitários como **SFTP** (Secure File Transfer Protocol) e **SCP** (Secure Copy).
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _O protocolo HTTPS utiliza a porta TCP 80 para estabelecer uma comunicação criptografada entre o navegador e o servidor web por meio da suíte IPsec._

> 🛑 **Gabarito: ERRADO.** **Justificativa:** O HTTPS opera na porta **TCP 443** e utiliza **SSL/TLS** (e não IPsec) na camada de transporte/aplicação. A porta TCP 80 é do HTTP não seguro.

**2. (CEBRASPE - Inédita)** _Ao estabelecer uma conexão segura via TLS, a criptografia assimétrica é empregada na fase inicial de handshake para a negociação e troca das chaves, enquanto a criptografia simétrica é utilizada para a cifragem dos dados trafegados na sessão._

> 🟢 **Gabarito: CERTO.** **Justificativa:** Afirmativa perfeita! O TLS combina o melhor dos dois mundos: a segurança da assimetria no handshake com a velocidade da simetria na transmissão de dados.

**3. (CEBRASPE - Inédita)** _No conjunto de protocolos IPsec, o protocolo Authentication Header (AH) é o responsável por fornecer sigilo e confidencialidade aos pacotes de dados por meio de algoritmos de cifragem forte._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** O protocolo **AH** garante apenas integridade e autenticidade. O responsável por fornecer **confidencialidade (sigilo)** no IPsec é o **ESP** (_Encapsulating Security Payload_).

📌 **Resumão de Bolso para o dia da prova:**

- **HTTPS:** HTTP + SSL/TLS (Porta **TCP 443**).
    
- **TLS:** Funciona de forma **híbrida** (assimétrica no handshake + simétrica na sessão).
    
- **IPsec:** Atua na **Camada de Rede (L3)** / Base para VPNs.
    
    - **AH:** Integridade e Autenticidade (Sem sigilo).
        
    - **ESP:** Cifra tudo (Confidencialidade + Integridade + Autenticidade).
        
- **SSH:** Acesso remoto seguro (Porta **TCP 22** / Substituiu o Telnet).