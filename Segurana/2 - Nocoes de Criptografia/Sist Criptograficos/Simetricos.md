#cripto 
### 🎓 Aula: Criptografia Simétrica no Padrão CEBRASPE

#### 1. Conceito e Mecanismo de Funcionamento

A **Criptografia Simétrica** é o modelo tradicional de cifragem. A sua característica fundamental é que **uma única chave secreta** é utilizada tanto para o processo de **cifragem** (encriptação) quanto para o de **decifragem** (desencriptação).

**Como funciona o processo (na visão da banca):**

1. **Cifragem:** O remetente pega o texto claro (_plaintext_), aplica o algoritmo simétrico usando a **chave secreta compartilhada** e gera o texto cifrado (_ciphertext_).
    
2. **Decifragem:** O destinatário recebe o texto cifrado e utiliza a **MESMA chave secreta compartilhada** para reverter o processo e obter o texto claro original.
    

> ⚠️ **PEGADINHA DE PROVA (CEBRASPE):** Guarde bem! Se a questão falar em _"par de chaves"_, _"chave pública"_ ou _"chave privada"_, ela **NÃO** está falando de criptografia simétrica! Na simétrica existe apenas **uma única chave** (que precisa ser mantida em segredo por ambas as partes).

#### 2. Princípios de Segurança e Características Principais

- **Confidencialidade (Sigilo):** O objetivo primário da criptografia simétrica é garantir a **confidencialidade** das informações (impedir que não autorizados leiam o conteúdo).
    
- **Desempenho e Velocidade:** Os algoritmos simétricos são **extremamente rápidos** e possuem baixo custo computacional se comparados aos algoritmos assimétricos. Por isso, são ideais para cifrar grandes volumes de dados (como arquivos grandes, discos inteiros e fluxos de dados em tempo real).
    
- **O Grande Desafio (Distribuição de Chaves):** Como remetente e destinatário precisam da mesma chave, o principal problema da criptografia simétrica é **como compartilhar essa chave de forma segura** antes de iniciar a comunicação.
    

#### 3. Classificação dos Algoritmos Simétricos

O CEBRASPE pode cobrar a divisão técnica entre como os dados são processados:

1. **Cifras de Bloco (_Block Ciphers_):**
    
    - O texto claro é dividido em blocos de tamanho fixo (ex: 64 bits, 128 bits) e cada bloco é cifrado por vez.
        
    - _Exemplos:_ AES, DES, 3DES, Blowfish, RC5.
        
2. **Cifras de Fluxo (_Stream Ciphers_):**
    
    - Os dados são cifrados bit a bit (ou byte a byte) de forma contínua em um fluxo de dados.
        
    - _Exemplos:_ RC4, ChaCha20.
        

#### 4. Principais Algoritmos Simétricos (Memorize para a Prova!)

Grave este rol de algoritmos, pois o CEBRASPE ama colocar um algoritmo simétrico em uma questão sobre assimetria e vice-versa:

- **AES (_Advanced Encryption Standard_):** O padrão atual mais utilizado no mundo. Altamente seguro e eficiente. Trabalha com blocos de 128 bits e chaves de 128, 192 ou 256 bits.
    
- **DES (_Data Encryption Standard_):** Antigo padrão (bloco de 64 bits / chave de 56 bits). **Obsoleto e inseguro** atualmente devido ao tamanho reduzido da chave (vulnerável a ataques de força bruta).
    
- **3DES (Triple DES):** Aplica o algoritmo DES três vezes seguidas para aumentar a segurança. Também caindo em desuso.
    
- **RC4:** Cifra de fluxo historicamente muito utilizada (inclusive em protocolos antigos como o WEP do Wi-Fi), mas hoje considerada obsoleta/insegura.
    
- **Blowfish / Twofish:** Cifras de bloco desenvolvidas como alternativas abertas ao DES/AES.
    

### 📝 Questões no Estilo CEBRASPE (Para Fixação)

**1. (CEBRASPE - Inédita)** _Na criptografia simétrica, a segurança da comunicação baseia-se na utilização de duas chaves distintas: uma chave pública, responsável por cifrar a mensagem, e uma chave privada, utilizada pelo destinatário para decifrá-la._

> 🛑 **Gabarito: ERRADO.** **Justificativa:** A descrição refere-se à criptografia **assimétrica** (de chave pública). A criptografia simétrica utiliza uma **única chave secreta** compartilhada para ambas as operações.

**2. (CEBRASPE - Inédita)** _O algoritmo AES (Advanced Encryption Standard) é um exemplo de sistema criptográfico simétrico amplamente utilizado na atualidade para garantir a confidencialidade dos dados devido à sua alta eficiência computacional._

> 🟢 **Gabarito: CERTO.** **Justificativa:** O AES é um algoritmo simétrico padrão de mercado, de altíssimo desempenho e focado no pilar da confidencialidade.

**3. (CEBRASPE - Inédita)** _Uma das vantagens dos sistemas criptográficos simétricos em relação aos assimétricos é a facilidade e a segurança no processo de distribuição prévia das chaves entre os interlocutores._

> 🛑 **Gabarito: ERRADO.** **Justificativa:** A distribuição segura da chave secreta compartilhada é justamente a **maior desvantagem e desafio** da criptografia simétrica.

📌 **Resumão de Bolso para o dia da prova:**

- **Chaves:** Apenas **1 chave secreta** (compartilhada).
    
- **Garante principalmente:** **Confidencialidade** (Sigilo).
    
- **Velocidade:** **Muito RÁPIDA** (ideal para grandes arquivos e transmissões).
    
- **Gargalo:** Distribuição/troca segura da chave inicial.
    
- **Principais Algoritmos Simétricos:** AES, DES, 3DES, RC4, Blowfish.