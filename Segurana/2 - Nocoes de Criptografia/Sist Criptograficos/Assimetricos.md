Atenção, turma! Silêncio na sala e anotando tudo no caderno!

Dando sequência ao nosso módulo de **Segurança da Informação e Criptografia**, a aula de hoje abordará um dos pilares mais cobrados pelo **CEBRASPE**: os **Sistemas Criptográficos Assimétricos** (ou Criptografia de Chave Pública)!

O CEBRASPE adora explorar a mecânica das chaves, o objetivo principal (confidencialidade vs. autenticidade/não repúdio), o desempenho computacional e as pegadinhas sobre qual chave é usada para cada operação.

### 🎓 Aula: Criptografia Assimétrica no Padrão CEBRASPE

#### 1. Conceito e Par de Chaves

Diferente da Criptografia Simétrica (que utiliza uma **única chave secreta** compartilhada), a **Criptografia Assimétrica** utiliza um **par de chaves matematicamente relacionadas**, mas distintas entre si:

- **Chave Pública:** Pode ser distribuída abertamente para qualquer pessoa.
    
- **Chave Privada (ou Secreta):** Deve ser mantida sob guarda estrita e **exclusiva do seu dono**. Nunca é compartilhada.
    

> 💡 **Propriedade Matemática Fundamental:** O que uma chave cifra, **apenas a outra chave do mesmo par** consegue decifrar!

#### 2. Os Dois Grandes Modos de Uso (A Maior Pegadinha de Prova!)

Nas questões de Certo/Errado do CEBRASPE, a banca vai tentar baralhar qual chave é usada em cada situação. Grave estas duas regras de ouro:

##### A. Para Garantir CONFIDENCIALIDADE (Sigilo)

Se o objetivo de Ana é enviar uma mensagem secreta para Bernardo (onde **apenas Bernardo** poderá ler):

1. **Cifragem:** Ana cifra a mensagem usando a **Chave PÚBLICA do Destinatário (Bernardo)**.
    
2. **Decifragem:** Bernardo decifra a mensagem usando a sua **Chave PRIVADA**.
    

> ⚠️ **Lógica de prova:** Qualquer um pode usar a chave pública de Bernardo para enviar algo secreto a ele, mas **apenas Bernardo** (dono da chave privada) consegue abrir.

##### B. Para Garantir AUTENTICIDADE e NÃO REPÚDIO (Assinatura Digital)

Se o objetivo de Ana é provar a Bernardo que foi **ela mesma** quem enviou a mensagem e que o conteúdo não foi alterado:

1. **Cifragem (Assinatura):** Ana cifra o resumo (hash) usando a sua própria **Chave PRIVADA (Remetente)**.
    
2. **Decifragem (Validação):** Bernardo decifra o resumo usando a **Chave PÚBLICA de Ana (Remetente)**.
    

> ⚠️ **Lógica de prova:** Se a chave pública de Ana conseguiu decifrar, é prova matemática de que o conteúdo foi gerado com a chave privada de Ana.

#### 3. Simétrica vs. Assimétrica (Comparativo Direto)

|**Característica**|**Criptografia Simétrica**|**Criptografia Assimétrica**|
|---|---|---|
|**Quantidade de Chaves**|1 Chave (Compartilhada)|2 Chaves (Pública e Privada)|
|**Velocidade/Desempenho**|**Muito Rápida** (Baixo custo computacional)|**Lenta** (Cálculos matemáticos complexos)|
|**Gerenciamento de Chaves**|Díficil para muitos usuários|Facilitado (Chave pública é aberta)|
|**Tamanho das Chaves**|Menor (ex: AES 128/256 bits)|Maior (ex: RSA 2048/4096 bits)|
|**Principais Algoritmos**|AES, DES, 3DES, RC4, Blowfish|**RSA, ECC (Curvas Elípticas), ElGamal, DSA**|

> 📌 **Uso Combinado (Sistemas Híbridos):** Como a criptografia assimétrica é lenta, na prática (como no protocolo SSL/TLS usado no HTTPS) utiliza-se a criptografia **assimétrica para trocar a chave secreta** e a criptografia **simétrica para cifrar a comunicação** em si.

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _Em um sistema criptográfico assimétrico, para garantir a confidencialidade de uma mensagem enviada por Maria para João, Maria deve cifrar o texto utilizando a sua própria chave privada._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** Se Maria cifrar com sua própria chave privada, qualquer pessoa com a chave pública de Maria poderá ler a mensagem. Para garantir confidencialidade, Maria deve cifrar com a **chave PÚBLICA de João (destinatário)**.

**2. (CEBRASPE - Inédita)** _Os algoritmos de criptografia assimétrica, como o RSA, apresentam desempenho computacional superior e maior velocidade de processamento quando comparados aos algoritmos simétricos, como o AES._

> 🛑 **Gabarito: ERRADO.**
> 
> **Justificativa:** A criptografia assimétrica é consideravelmente **mais lenta e custosa** computacionalmente que a simétrica. Por isso, arquivos grandes costumam ser cifrados com algoritmos simétricos (como o AES).

**3. (CEBRASPE - Inédita)** _A criptografia de chave pública permite alcançar os objetivos de autenticidade e não repúdio quando o emissor cifra a informação utilizando a sua chave privada._

> 🟢 **Gabarito: CERTO.**
> 
> **Justificativa:** O uso da **chave privada do emissor** para cifrar (ou assinar) o dado atesta quem criou a mensagem (Autenticidade) e impede que o autor negue a autoria (Não Repúdio).

📌 **Resumão de Bolso para o dia da prova:**

- **Confidencialidade:** Cifra com a **Pública do Destinatário**.
    
- **Autenticidade / Assinatura:** Cifra com a **Privada do Remetente**.
    
- **Velocidade:** É **lenta** (se comparada à simétrica).
    
- **Principais Algoritmos Assimétricos:** RSA, ECC, DSA e ElGamal.