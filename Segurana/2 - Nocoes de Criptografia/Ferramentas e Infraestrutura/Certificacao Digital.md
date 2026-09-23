### 🎓 Aula: Certificação Digital no Padrão CEBRASPE

#### 1. Conceito de Certificado Digital

Um **Certificado Digital** é um arquivo eletrônico que funciona como uma "carteira de identidade virtual" de uma pessoa física, jurídica ou servidor/computador. Ele associa uma **chave pública** a uma **identidade** (CPF, CNPJ, domínio web etc.), sendo assinado digitalmente por uma entidade de confiança: a **Autoridade Certificadora (AC)**.

> 💡 **O que consta em um Certificado Digital (Padrão X.509):**
> 
> - A chave pública do titular.
>     
> - Os dados de identificação do titular (nome, CPF/CNPJ, e-mail).
>     
> - O período de validade do certificado.
>     
> - O nome e a assinatura digital da Autoridade Certificadora (AC) que o emitiu.
>     
> - O número de série e algoritmo de assinatura.
>     

#### 2. Estrutura e Hierarquia da ICP-Brasil

A **ICP-Brasil** (Infraestrutura de Chaves Públicas Brasileira) é uma estrutura hierárquica em cadeia de confiança.

1. **Autoridade Certificadora Raiz (AC-Raiz):**
    
    - É a autoridade executiva principal. No Brasil, esse papel é desempenhado pelo **ITI (Instituto Nacional de Tecnologia da Informação)**.
        
    - É responsável por emitir, assinar e gerenciar os certificados das **ACs de Primeiro Nível** (ACs Intermediárias).
        
    - **Pegadinha da banca:** A AC-Raiz **NÃO** emite certificados diretamente para os usuários finais!
        
2. **Autoridades Certificadoras (ACs Intermediárias e Subordinadas):**
    
    - Entidades públicas ou privadas responsáveis por emitir, renovar, homologar ou revogar os certificados digitais dos **usuários finais**.
        
3. **Autoridades de Registro (AR):**
    
    - **NÃO emitem certificados!** As ARs funcionam como a "ponta de atendimento". Elas são responsáveis por receber, validar a documentação presencial/biométrica do titular e encaminhar a solicitação para a AC emitir o certificado.
        
4. **Autoridade do Tempo (ACT):**
    
    - Entidade responsável por prestar serviços de **Carimbo do Tempo (Timestamping)**, atestando a data e a hora exatas em que um documento foi assinado.
        

#### 3. Tipos de Certificados Digitais na ICP-Brasil

O CEBRASPE frequentemente cobra as nomenclaturas e a finalidade de cada tipo:

- **Série A (Assinatura Digital):** Utilizados para assinar documentos digitais, garantindo autoria, integridade e não repúdio.
    
- **Série S (Sigilo/Confidencialidade):** Utilizados para **criptografar** dados ou comunicações confidenciais.
    
- **Série T (Carimbo do Tempo):** Utilizados para atestar a tempestividade (data e hora) de um documento.
    

**Quanto ao meio de armazenamento (Tipos de Certificado A):**

- **A1:** A chave privada é gerada e armazenada no próprio **computador/software**. Validade de **1 ano**.
    
- **A3:** A chave privada é gerada e armazenada em hardware criptográfico exclusivo e seguro (**Cartão Inteligente/Smartcard** ou **Token USB**). A chave **não pode ser exportada** do dispositivo. Validade de até **5 anos** (dependendo da regulamentação vigente).
    

#### 4. Revogação de Certificados e LCR

Um certificado pode perder a validade antes do prazo previsto (por perda da chave privada, alteração de dados, comprometimento do dispositivo, etc.).

- **Lista de Certificados Revogados (LCR):** Relação publicada periodicamente pela Autoridade Certificadora contendo os certificados revogados que ainda estão dentro do prazo de validade original.
    
- **Protocolo OCSP (Online Certificate Status Protocol):** Permite a verificação em tempo real do status de um certificado (válido, revogado ou desconhecido), sem a necessidade de baixar a LCR completa.
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _Na estrutura da ICP-Brasil, a Autoridade de Registro (AR) é a entidade responsável por emitir e assinar digitalmente os certificados digitais fornecidos aos cidadãos._

> 🛑 **Gabarito: ERRADO.** **Justificativa:** A Autoridade de Registro (AR) apenas valida a documentação do titular e encaminha o pedido. Quem **emite e assina** o certificado é a **Autoridade Certificadora (AC)**.

**2. (CEBRASPE - Inédita)** _A chave privada contida em um certificado digital do tipo A3 pode ser facilmente copiada e exportada para múltiplos computadores para fins de backup._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** Nos certificados do tipo A3, a chave privada é gerada diretamente no hardware seguro (token ou smartcard) e **nunca pode ser exportada** ou copiada.

**3. (CEBRASPE - Inédita)** _A Autoridade Certificadora Raiz da ICP-Brasil tem como atribuição a emissão dos certificados das ACs subordinadas, não emitindo certificados diretamente para o usuário final._

> 🟢 **Gabarito: CERTO.**
> 
> **Justificativa:** A AC-Raiz é o topo da cadeia de confiança e interage apenas com as ACs de nível inferior, sem prestar atendimento direto ao usuário final.

📌 **Resumão de Bolso para o dia da prova:**

- **AC-Raiz:** ITI (não emite para usuário final).
    
- **AC:** Emite e assina o certificado.
    
- **AR:** Identifica o usuário e checa documentos (não emite nada).
    
- **Certificado A1:** Armazenado via software / Validade 1 ano.
    
- **Certificado A3:** Armazenado em hardware (Token/Smartcard) / Chave privada inexportável.
    
- **Revogação:** Checada via **LCR** ou em tempo real via **OCSP**.