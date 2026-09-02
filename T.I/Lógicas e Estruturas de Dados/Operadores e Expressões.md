#ti #estruturaDeDados         
**Operadores** são símbolos especiais que indicam ao processador qual operação matemática, relacional ou lógica deve ser executada. **Expressões** são combinações de operadores, variáveis e valores (operandos) que, quando avaliados, resultam em um único valor.

### Tipos de Operadores
#### ==1. Operadores Aritméticos==

Servem para realizar cálculos matemáticos fundamentais sobre dados numéricos (inteiros e reais).

- **Soma (`+`):** `10 + 5` $\rightarrow$ `15`
    
- **Subtração (`-`):** `10 - 5` $\rightarrow$ `5`
    
- **Multiplicação (`*`):** `10 * 5` $\rightarrow$ `50`
    
- **Divisão (`/`):** `10 / 4` $\rightarrow$ `2.5`
    
- **Módulo / Resto da Divisão (`%` ou `mod`):** Retorna o resto de uma divisão inteira.
    
    - _Exemplo:_ `10 % 3` $\rightarrow$ `1` (pois $10 = 3 \times 3 + 1$)
        
- **Exponenciação (`**` ou `^`):** `2 ** 3` $\rightarrow$ `8`
    

#### ==2. Operadores Relacionais (Comparação)==

Comparam dois valores e sempre retornam um resultado **Lógico** (`Verdadeiro` ou `Falso`).

|**Operador**|**Significado**|**Exemplo**|**Resultado**|
|---|---|---|---|
|`==` ou `=`|Igual a|`5 == 5`|Verdadeiro|
|`!=` ou `<>`|Diferente de|`5 != 3`|Verdadeiro|
|`>`|Maior que|`7 > 10`|Falso|
|`<`|Menor que|`3 < 8`|Verdadeiro|
|`>=`|Maior ou igual a|`5 >= 5`|Verdadeiro|
|`<=`|Menor ou igual a|`4 <= 2`|Falso|

#### ==3. Operadores Lógicos (Booleanos)==

Usados para combinar múltiplas condições relacionais. Operam sobre valores booleanos e retornam um valor booleano.

- **E (`AND` / `&&`):** Retorna `Verdadeiro` **apenas se todas** as condições forem verdadeiras.
    
    - _Exemplo:_ `(idade >= 18) && (tem_carteira == true)`
        
- **OU (`OR` / `||`):** Retorna `Verdadeiro` se **pelo menos uma** das condições for verdadeira.
    
    - _Exemplo:_ `(dia == "Sábado") || (dia == "Domingo")`
        
- **NÃO (`NOT` / `!`):** Inverte o valor lógico. Se era `Verdadeiro`, vira `Falso`.
    
    - _Exemplo:_ `!(5 > 10)` $\rightarrow$ `Verdadeiro` (pois `5 > 10` é Falso, e a negação inverte).
        

### ==Expressões e Precedência==

Uma **expressão** avalia operandos na ordem estabelecida pelas regras de **precedência de operadores** (similar à matemática tradicional).

**Ordem Geral de Execução:**

1. Parênteses `()` — alteram a ordem natural e são resolvidos de dentro para fora.
    
2. Operações Aritméticas (Exponenciação $\rightarrow$ Multiplicação/Divisão/Módulo $\rightarrow$ Soma/Subtração).
    
3. Comparações Relacionais (`>`, `<`, `==`, etc.).
    
4. Operadores Lógicos (`NOT` $\rightarrow$ `AND` $\rightarrow$ `OR`).
    

#### Exemplo Prático de Avaliação de Expressão:

Dadas as variáveis `a = 5`, `b = 2` e `c = 10`:

$$\text{resultado} = (a * b + 2) > c \text{ AND } b == 2$$

1. **Parênteses / Aritmética:** $(5 \times 2 + 2) \rightarrow (10 + 2) \rightarrow 12$
    
2. **Relacional 1:** $12 > 10 \rightarrow \text{Verdadeiro}$
    
3. **Relacional 2:** $2 == 2 \rightarrow \text{Verdadeiro}$
    
4. **Lógico:** $\text{Verdadeiro} \text{ AND } \text{Verdadeiro} \rightarrow \mathbf{Verdadeiro}$