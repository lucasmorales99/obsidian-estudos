### 🎓 Aula: Engenharia Social no Padrão CEBRASPE

#### 1. Conceito e Definição de Engenharia Social

A **Engenharia Social** é o conjunto de técnicas e manobras psicológicas utilizadas por atacantes para manipular, enganar e induzir pessoas a realizar ações comprometedoras ou divulgar informações confidenciais (como senhas, dados bancários e acessos do sistema).

PDF

⚠️ **CONCEITO CHAVE DE PROVA (CEBRASPE):**

- A Engenharia Social explora as **vulnerabilidades humanas** (confiança, curiosidade, medo, ganância, ingenuidade, autoridade e urgência) e **não as falhas técnicas do sistema/software diretamente**.
    
- **Frase típica da banca:** _"A engenharia social visa explorar a confiança do usuário para obter acesso não autorizado a sistemas de informação, independentemente do uso de softwares maliciosos avançados."_ -> **CERTO!**
    

#### 2. As Principais Técnicas de Engenharia Social (O que despenca na prova!)

O CEBRASPE adora colocar cenários práticos e pedir para você identificar qual é a técnica de ataque. Grave cada uma delas:

##### A) Phishing (A "Pescaria" Digital)

- **O que é:** Envio em massa de mensagens fraudulentas (e-mails, mensagens instantâneas, SMS) fingindo ser de uma fonte confiável (banco, chefia, suporte técnico) para capturar dados sensíveis ou induzir o clique em links maliciosos.
    
- **Variações de Phishing que o CEBRASPE cobra:**
    
    - **Spear Phishing:** Ataque de phishing **direcionado e personalizado** a um indivíduo ou organização específica (pesquisa prévia sobre a vítima).
        
    - **Whaling (Ataque à Baleia):** Phishing direcionado especificamente a **altos executivos, diretores ou autoridades** (vítimas do "alto escalão").
        
    - **Smishing:** Phishing realizado por meio de mensagens de texto **SMS**.
        
    - **Vishing:** Phishing realizado por meio de chamadas de **voz (telefone)**.
        

##### B) Shoulder Surfing (Olhar por cima do ombro)

- **O que é:** Observação direta e física do atacante para capturar informações confidenciais (como senhas digitadas no teclado, PINs no caixa eletrônico ou telas de computador/celular) sem a percepção da vítima.
    

##### C) Dumpster Diving (Pesquisa no Lixo)

- **O que é:** Procura no lixo físico (papéis descartados, relatórios sem trituração, notas fiscais, mídias antigas) por documentos com informações confidenciais ou dados de acesso.
    

##### D) Baiting (Isca)

- **O que é:** O atacante deixa uma "isca" física (como um pendrive infectado com malware escrito "Salários 2026") em um local público ou no estacionamento da empresa, contando com a **curiosidade** da vítima ao conectá-lo ao computador corporativo.
    

##### E) Pretexting (Pretexto)

- **O que é:** O atacante cria um **cenário ou identidade falsa de autoridade** (ex.: dizendo ser do suporte de TI, auditoria ou gerência) para convencer a vítima a fornecer dados ou alterar procedimentos de segurança.
    

##### F) Tailgating / Piggybacking (Carona Física)

- **O que é:** O atacante consegue acesso físico a uma área restrita ou prédio corporativo **seguindo uma pessoa autorizada** logo atrás (aproveitando quando alguém segura a porta por cortesia ou passar pela catraca junto).
    

#### 3. Como o CEBRASPE Cobra na Prática (Certo / Errado)

Vamos analisar os padrões de itens típicos que aparecem na sua prova do CEBRASPE:

- **Item 1:** _"A engenharia social é fundamentada na manipulação psicológica de pessoas para que executem ações ou divulguem informações confidenciais, explorando a confiança e a desatenção dos usuários."_
    
    - **Gabarito:** **CERTO.** Definição perfeita do conceito de engenharia social.
        
- **Item 2:** _"Caso um atacante envie um e-mail falso direcionado especificamente ao Diretor Financeiro de uma instituição pública para obter credenciais do sistema de pagamentos, trata-se de um ataque conhecido como Whaling."_
    
    - **Gabarito:** **CERTO.** Ataque focado em executivos e autoridades (altos cargos) é a especificação do Whaling.
        
- **Item 3:** _"A implementação de firewalls, antivírus e sistemas de detecção de intrusão (IDS) garante proteção total contra ataques de engenharia social, tornando desnecessário o treinamento de conscientização de usuários."_
    
    - **Gabarito:** **ERRADO.** Nenhum controle técnico/lógico é 100% eficaz contra engenharia social. O treinamento de conscientização de usuários é a medida principal e mais eficaz de prevenção.
        

#### 4. Medidas de Mitigação e Prevenção

Em questões que cobram o que a organização deve fazer para se proteger de ataques de engenharia social (conforme prega a gestão de segurança da informação e a LGPD):

PDF+ 1

1. **Conscientização e Treinamento Contínuo:** Capacitar os colaboradores a reconhecer pedidos suspeitos e técnicas de indução.
    
2. **Políticas de Descarte Seguro:** Uso de fragmentadoras de papel para evitar o _Dumpster Diving_.
    
3. **Autenticação Multi-fator (MFA):** Reduz o impacto caso a senha do usuário seja capturada via _Phishing_.
    
4. **Princípio do Menor Privilégio:** Garantir que o usuário só tenha acesso aos recursos estritamente necessários para a sua função.
    

📌 **Checklist do Concurseiro para a Prova de Engenharia Social:**

1. Esqueceu de atualizar o sistema? ➡️ Vulnerabilidade técnica.
    
2. O usuário clicou porque acreditava que era o chefe pedindo ajuda rápida? ➡️ **Engenharia Social**!
    
3. Preste atenção no termo: _Massa_ (Phishing), _Alvo específico_ (Spear Phishing), _Diretoria/Autoridade_ (Whaling), _Voz_ (Vishing), _SMS_ (Smishing), _Lixo_ (Dumpster Diving), _Olhando a tela_ (Shoulder Surfing).