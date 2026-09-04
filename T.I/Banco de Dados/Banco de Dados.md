#db 
==**1. Bancos de Dados Relacionais (SGBDR) vs. NoSQL**==

- **Relacionais (SQL):** Organizados em tabelas rígidas compostas por linhas e colunas, utilizando relacionamentos (chaves primárias e estrangeiras) e linguagem SQL. Priorizam integridade e consistência.
    
    - _Exemplos:_ PostgreSQL, Oracle, MySQL, SQL Server.
        
- **Não Relacionais (NoSQL):** Modelos flexíveis sem esquema estrito (_schema-less_), otimizados para alta escalabilidade horizontal e grandes volumes de dados ilimitados.
    
    - _Documentos:_ Salva dados em JSON/BSON (ex.: MongoDB).
        
    - _Chave-Valor:_ Estrutura ultra-rápida de consulta por chave (ex.: Redis).
        
    - _Colunar:_ Armazena dados em colunas agrupadas (ex.: Cassandra).
        
    - _Grafos:_ Otimizado para dados interconectados (ex.: Neo4j).
        

==**2. Transações e Propriedades ACID**==

Para garantir integridade nas operações do banco de dados, o modelo relacional adota as regras **ACID**:

- **Atomicidade:** A transação executa inteira ou é totalmente cancelada (_tudo ou nada_).
    
- **Consistência:** O banco transita de um estado válido a outro respeitando todas as regras e restrições (_constraints_).
    
- **Isolamento:** Transações concorrentes executam sem interferir umas nas outras.
    
- **Durabilidade:** Uma vez confirmada (_commit_), a alteração persiste mesmo em caso de falhas de sistema.
    

> Sistemas NoSQL distribuídos frequentemente utilizam o modelo **BASE** (Basically Available, Soft-state, Eventual consistency), priorizando alta disponibilidade sobre consistência imediata.

==**3. Mapeamento Objeto-Relacional (ORM) e Persistência**==

O **ORM** faz a ponte entre o paradigma orientado a objetos (código) e o modelo relacional (tabelas).

- **Mapeamento:** Classes viram tabelas, atributos viram colunas e objetos viram linhas.
    
- **Benefícios:** Abstração de queries SQL manuais, produtividade e independência parcial do SGBD subjacente.
    
- **Principais Frameworks:**
    
    - _Java:_ Hibernate / Jakarta Persistence API (JPA).
        
    - _C# / .NET:_ Entity Framework Core.
        
    - _Python:_ SQLAlchemy / Django ORM.
        
    - _Node.js / TypeScript:_ Prisma / TypeORM / Sequelize.
        

==**4. Resumo Rápido para Questões e Revisão**==

- **Chave Primária (PK):** Identificador único de um registro em uma tabela.
    
- **Chave Estrangeira (FK):** Campo que cria um vínculo referencial com a PK de outra tabela.
    
- **Mapeamento Objeto-Relacional:** Mapeia a lógica de classes para estruturas de tabela.
    
- **Frameworks de Persistência:** Gerenciam a gravação e leitura de objetos na base de dados de forma automatizada.