### 🎓 Aula: Função Hash no Padrão CEBRASPE

#### 1. Conceito e Definição

A função **Hash** é um algoritmo matemático unidirecional (_one-way_) que pega uma entrada (_input_) de **qualquer tamanho** (desde uma única letra até um arquivo de vários Terabytes) e a transforma em uma saída (_output_) de **tamanho FIXO**. Essa saída é chamada de **Hash**, **Digest**, **Resumo Criptográfico** ou **Huipim Digital**.

> ⚠️ **PEGADINHA DE PROVA (CEBRASPE):** O CEBRASPE ama afirmar que _"quanto maior for o arquivo de entrada, maior será o tamanho do Hash gerado"_. **ERRADO!** O tamanho da saída é **sempre fixo**, independentemente do tamanho da entrada!

#### 2. Propriedades Fundamentais do Hash (Para Provas de Certo/Errado)

Guarde estes quatro pilares, pois a banca cobra exatamente a definição técnica de cada um deles:

1. **Unidirecionalidade (Irreversibilidade):** É fácil calcular o Hash a partir do dado original, mas é **computacionalmente inviável** fazer o caminho inverso (ou seja, descobrir o documento original a partir do seu Hash). Hash **NÃO** é criptografia reversível; não existe "descriptografar um Hash".
    
2. **Efeito Avalanche:** Qualquer mínima variação na entrada (como alterar uma vírgula ou um único bit) gera um Hash **completamente diferente**.
    
3. **Determinismo:** Uma mesma entrada sempre gerará exatamente o mesmo Hash, usando o mesmo algoritmo.
    
4. **Resistência à Colisão:**
    
    - **Colisão:** Ocorre quando duas entradas **diferentes** produzem exatamente a **mesma saída** (mesmo Hash).
        
    - Uma função Hash criptográfica ideal deve ser extremamente resistente a colisões.
        

#### 3. Princípio de Segurança Garantido pelo Hash

Assim como na aula de Assinatura Digital, memorize o pilar da Segurança da Informação atrelado ao Hash:

- O Hash garante estritamente a INTEGRIDADE dos dados!
    
- Ele **NÃO garante Confidencialidade** (pois o Hash não esconde o texto, apenas gera um resumo dele).
    
- Ele **NÃO garante Autenticidade nem Não Repúdio sozinho** (para isso, ele precisa ser cifrado com uma chave privada, virando uma Assinatura Digital).
    

#### 4. Principais Algoritmos de Hash

O CEBRASPE costuma citar os nomes das famílias de algoritmos nas questões. Fique atento ao estado de segurança de cada um:

- **MD5 (Message Digest 5):** Gera um Hash de **128 bits**.
    
    > ⚠️ **Na prova:** O MD5 é considerado **obsoleto e inseguro** devido a vulnerabilidades graves de colisão descobertas ao longo dos anos.
    
- **SHA-1 (Secure Hash Algorithm 1):** Gera um Hash de **160 bits**. Também é considerado **descontinuado/inseguro** para aplicações críticas.
    
- **SHA-2 (SHA-256, SHA-512):** Gera resumos de **256 ou 512 bits**. É o padrão **amplamente utilizado e seguro** na atualidade.
    
- **SHA-3:** Família mais recente, baseada no algoritmo Keccak, mantendo alto nível de segurança.
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _As funções hash criptográficas são algoritmos bidirecionais que permitem recuperar o conteúdo original de uma mensagem a partir da aplicação da chave privada correspondente._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** As funções Hash são **unidirecionais** (de sentido único). Não existe chave e não é possível reverter o Hash para obter a mensagem original.

**2. (CEBRASPE - Inédita)** _O algoritmo MD5, por gerar resumos criptográficos de tamanho fixo independentemente do volume do texto de entrada, é recomendado pela ICP-Brasil para garantia de integridade de documentos eletrônicos de alto sigilo._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** Embora gere resumos de tamanho fixo (128 bits), o MD5 é tecnicamente **inseguro e vulnerável a colisões**, não sendo recomendado para uso seguro.

**3. (CEBRASPE - Inédita)** _Uma das propriedades essenciais de uma função hash criptográfica é a resistência a colisões, o que significa que deve ser computacionalmente inviável encontrar duas mensagens distintas que produzam o mesmo resumo._

> 🟢 **Gabarito: CERTO.**
> 
> **Justificativa:** Essa é a definição exata do conceito de resistência à colisão cobrado pela banca.

📌 **Resumão de Bolso para o dia da prova:**

- **Entrada:** Qualquer tamanho.
    
- **Saída:** Tamanho **Fixo**.
    
- **Unidirecional:** Não dá pra reverter!
    
- **Garante:** **Integridade**.
    
- **Inseguros/Obsoletos:** MD5 e SHA-1.
    
- **Seguro/Padrão:** Família SHA-2 (SHA-256) e SHA-3.