### 🎓 Aula: ICP-Brasil no Padrão CEBRASPE

#### 1. Conceito e Criação

A **ICP-Brasil** é uma estrutura de **cadeia hierárquica de confiança** instituída pela **Medida Provisória nº 2.200-2/2001**. Ela tem como objetivo garantir a autenticidade, a integridade e a validade jurídica de documentos em forma eletrônica, das aplicações de suporte e das aplicações habilitadas que utilizem certificados digitais, bem como a realização de transações eletrônicas seguras.

#### 2. Hierarquia da ICP-Brasil (Quem é Quem)

O CEBRASPE adora inventar trocas de funções entre os atores da ICP-Brasil. Memorize a atribuição exata de cada um:

1. **CG ICP-Brasil (Comitê Gestor da ICP-Brasil):**
    
    - É o órgão **vinculado à Presidência da República** responsável por definir as políticas, as regras de funcionamento, os regulamentos e as diretrizes técnicas de toda a infraestrutura.
        
2. **AC-Raiz (Autoridade Certificadora Raiz):**
    
    - É a autoridade executiva principal, papel desempenhado pelo **ITI (Instituto Nacional de Tecnologia da Informação)**.
        
    - **Atribuições:** Executar as políticas definidas pelo Comitê Gestor, credenciar, descredenciar e fiscalizar as demais Autoridades Certificadoras (ACs) de nível inferior, além de emitir, expedir e revogar os certificados das ACs subordinadas.
        
    - ⚠️ **PEGADINHA CEBRASPE:** A AC-Raiz **NÃO emite certificados digitais diretamente para os usuários finais** (cidadãos ou empresas).
        
3. **AC (Autoridade Certificadora):**
    
    - Entidade pública ou privada credenciada pela AC-Raiz.
        
    - **Atribuições:** É a responsável por **emitir, assinar, renovar, distribuir e revogar os certificados digitais** dos usuários finais (pessoas físicas ou jurídicas). Também é responsável por publicar as **Listas de Certificados Revogados (LCR)**.
        
4. **AR (Autoridade de Registro):**
    
    - Entidade operacional vinculada a uma AC.
        
    - **Atribuições:** Funciona como a "ponta de atendimento". É responsável por **validar a identificação presencial ou biométrica** do solicitante e conferir seus documentos originais.
        
    - ⚠️ **PEGADINHA CEBRASPE:** A AR **NÃO emite e NÃO assina certificados digitais**! Ela apenas valida a solicitação e a encaminha para a AC emissora.
        

#### 3. Presunção de Validade Jurídica

De acordo com a legislação da ICP-Brasil:

- Os documentos eletrônicos assinados digitalmente com certificados emitidos **no âmbito da ICP-Brasil** possuem **validade jurídica presumida** em relação aos signatários (possuem presunção legal de veracidade).
    
- **Atenção:** A legislação brasileira **não nega a validade jurídica** de assinaturas digitais efetuadas com certificados _fora_ do padrão ICP-Brasil, desde que haja aceitação prévia entre as partes contratantes. Porém, apenas o padrão ICP-Brasil possui a presunção legal absoluta concedida pela MP 2.200-2/2001.
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _No âmbito da ICP-Brasil, o Instituto Nacional de Tecnologia da Informação (ITI) atua como a Autoridade Certificadora Raiz (AC-Raiz), sendo responsável direta pela emissão e distribuição de certificados digitais de tipo A3 aos cidadãos brasileiros._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** O ITI (AC-Raiz) credencia e emite certificados apenas para as ACs de nível inferior. Ele **não** atende diretamente o usuário final para emissão de certificados pessoais.

**2. (CEBRASPE - Inédita)** _Uma Autoridade de Registro (AR) tem entre suas atribuições operacionais a validação presencial da documentação do requerente e a assinatura digital do certificado emitido._

> 🛑 **Gabarito: ERRADO.** **Justificativa:** A AR realiza a validação documental e a verificação de identidade, mas **não assina nem emite** certificados. Essa função é exclusiva das **ACs**.

**3. (CEBRASPE - Inédita)** _A Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil) foi criada para prover uma estrutura de confiança e garantir a autenticidade, a integridade e a validade jurídica de documentos em forma eletrônica._

> 🟢 **Gabarito: CERTO.** **Justificativa:** Afirmativa perfeita que resume a finalidade da ICP-Brasil disposta no art. 1º da MP 2.200-2/2001.

📌 **Resumão de Bolso para a prova:**

- **CG ICP-Brasil:** Define as regras e normas.
    
- **AC-Raiz (ITI):** Credencia as ACs e assina os certificados das ACs (não atende o cidadão comum).
    
- **AC:** Emite, assina, renova e revoga certificados do usuário final.
    
- **AR:** Confere documentos e valida identidades (não emite certificados).