#mvc #arquitetura 
O **MVC** (Model-View-Controller) é um dos padrões de arquitetura de software (_architectural patterns_) mais utilizados no desenvolvimento de aplicações web e de sistemas. Ele divide a aplicação em três componentes principais para separar as responsabilidades de negócio, interface do usuário e controle de fluxo.

- ==**Model== (Modelo):**
    
    - **O que faz:** Gerencia os dados, a regra de negócio e a lógica da aplicação.
        
    - **Função:** Acessa o banco de dados, valida dados e executa operações lógicas. Ele não sabe como os dados serão exibidos na tela.
        
- ==**View== (Visão / Interface):**
    
    - **O que faz:** É a camada de apresentação gráfica com a qual o usuário interage (HTML, CSS, JSON, UI de apps mobile).
        
    - **Função:** Exibe os dados vindos do _Controller_ / _Model_ para o usuário e envia os eventos/ações do usuário para o _Controller_.
        
- ==**Controller== (Controlador):**
    
    - **O que faz:** Atua como o "intermediário" ou cérebro das requisições.
        
    - **Função:** Recebe as requisições do usuário (através da View), processa as entradas, solicita dados ou ações ao _Model_ e decide qual _View_ deve ser renderizada como resposta.


### **Fluxo de Funcionamento** (Como as peças se conversam)

1. **Usuário faz uma ação:** O usuário clica em um botão na página (View) ou digita uma URL (requisição HTTP).
    
2. **Controller intercepta:** O Controller recebe essa requisição e analisa o que precisa ser feito.
    
3. **Controller chama o Model:** Se for necessário buscar ou salvar dados, o Controller chama as funções do Model.
    
4. **Model processa:** O Model faz as consultas no banco de dados, aplica as regras de negócio e devolve o resultado ao Controller.
    
5. **Controller atualiza a View:** O Controller pega os dados retornados pelo Model e escolhe a View adequada para exibir os resultados ao usuário.

### Vantagens do uso do MVC

- **Separação de Conceitos (Separation of Concerns):** O código de banco de dados não fica misturado com o código HTML/UI.
    
- **Reutilização de Código:** Um mesmo Model (lógica de negócios) pode ser reutilizado para diferentes Views (ex: uma página Web em HTML e uma API para App Mobile).
    
- **Facilidade de Manutenção e Testes:** É muito mais fácil criar testes unitários para a lógica (Model) sem depender da interface gráfica (View).
    
- **Trabalho em Equipe:** Desenvolvedores _Frontend_ podem focar nas Views enquanto desenvolvedores _Backend_ focam nos Controllers e Models.