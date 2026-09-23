### 🎓 Aula: Assinatura Digital no Padrão CEBRASPE

#### 1. Conceito e Mecanismo de Funcionamento

A Assinatura Digital é um mecanismo criptográfico baseado em **Criptografia Assimétrica** (de chave pública). Ela vincula uma identidade a uma mensagem ou documento eletrônico.

**Como funciona o processo de Assinatura (na visão da banca):**

1. **Geração do Hash (Digest):** Aplica-se uma função _hash_ (como SHA-256) sobre o documento original para gerar um resumo único e de tamanho fixo.
    
2. **Cifragens:** O remetente encripta (cifra) esse _hash_ utilizando a sua própria **CHAVE PRIVADA**.
    
    > ⚠️ **PEGADINHA DE PROVA (CEBRASPE):** Guarde bem! **Assina-se com a chave PRIVADA do remetente**. O CEBRASPE vai tentar te enganar dizendo que se assina com a chave pública do destinatário. _Errado!_
    

**Como funciona a Verificação/Validação:**

1. O destinatário recebe o documento e a assinatura.
    
2. Aplica a **CHAVE PÚBLICA do remetente** sobre a assinatura para decifrar e obter o _hash_ original.
    
3. Calcula novamente o _hash_ do documento recebido.
    
4. Se os dois _hashes_ forem idênticos, a assinatura é **VÁLIDA**.
    

#### 2. Princípios e Garantias da Segurança da Informação

Esta é a questão clássica de **Certo/Errado** do CEBRASPE. A Assinatura Digital garante **TRÊS** pilares fundamentais da Segurança da Informação:

1. **Integridade:** Garante que o documento não foi alterado durante o trânsito. (Se 1 bit for alterado no documento, o _hash_ muda completamente e a validação falha).
    
2. **Autenticidade:** Confirma a identidade de quem assinou (já que apenas o dono da chave privada poderia ter gerado aquela assinatura).
    
3. **Não Repúdio (ou Irretratabilidade):** O emissor não pode negar a autoria da assinatura, pois a chave privada é de seu conhecimento e posse exclusiva.
    

> ❌ **ATENÇÃO MÁXIMA:** A Assinatura Digital **NÃO garante Confidencialidade**! O documento assinado via de regra continua em texto aberto (_plaintext_). Se você quiser sigilo, precisará cifrar o documento (usando a chave pública do destinatário) **além** de assiná-lo.

#### 3. Criptografia Assimétrica vs. Hash

Para que a Assinatura Digital exista, ela precisa do trabalho conjunto de duas tecnologias criptográficas:

- **Função Hash:** Garante a eficiência (assina-se o _hash_, que é pequeno, e não o documento inteiro de vários gigabytes) e a **Integridade**.
    
- **Chave Assimétrica (Chave Privada/Pública):** Garante a **Autenticidade** e o **Não Repúdio**.
    

#### 4. Infraestrutura de Chaves Públicas (ICP-Brasil)

Para que uma Chave Pública seja confiável e vinculada a uma pessoa ou entidade real, entra em cena a **ICP-Brasil** (a Infraestrutura de Chaves Públicas brasileira):

- **Autoridade Certificadora (AC):** Entidade responsável por emitir, renovar, revogar e vincular certificados digitais (que contêm a chave pública) a uma pessoa física ou jurídica.
    
- **Certificado Digital:** O "RG" ou "CPF" digital do usuário.
    
- No Brasil, a assinatura digital realizada com certificado emitido no âmbito da ICP-Brasil possui **validade jurídica presumida**.
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _A assinatura digital garante os princípios da integridade, da autenticidade, do não repúdio e da confidencialidade das informações._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** A assinatura digital **não garante confidencialidade**. O conteúdo assinado continua visível a menos que seja explicitamente criptografado para esse fim.

**2. (CEBRASPE - Inédita)** _No processo de assinatura digital, o emissor utiliza sua chave pública para cifrar o resumo (hash) do documento, garantindo, assim, que apenas o destinatário possa validar a assinatura._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** O emissor utiliza sua **chave PRIVADA** para assinar (cifrar o _hash_). O destinatário utiliza a chave **PÚBLICA** do emissor para verificar/validar.

**3. (CEBRASPE - Inédita)** _A alteração de um único caractere em um arquivo eletrônico assinado digitalmente invalida a assinatura digital correspondente._

> 🟢 **Gabarito: CERTO.** **Justificativa:** Qualquer alteração no arquivo altera o resultado da função _hash_, tornando os resumos divergentes no momento da validação, o que comprova a quebra da integridade.

📌 **Resumão de Bolso para o dia da prova:**

- **Assinar:** usa Chave **Privada** do remetente.
    
- **Verificar:** usa Chave **Pública** do remetente.
    
- **Garante:** Integridade + Autenticidade + Não Repúdio.
    
- **NÃO Garante:** Confidencialidade (Sigilo).