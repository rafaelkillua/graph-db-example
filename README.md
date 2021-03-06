## Introdução a Neo4j e Express - Exemplos de uso e *queries* básicas

Nesse repositório você encontrará alguns exemplos de queries na linguagem ***Cypher*** do **Neo4j** de um modo bem inicial e um exemplo básico de como conectar ao banco de dados Neo4j usando o driver padrão Javascript.

Caso queira mais informações, há uma [**apresentação de slides**](https://github.com/rafaelkillua/express-neo4j-example/blob/master/Introdu%C3%A7%C3%A3o%20a%20Graph%20DBs.pdf) explicando um pouco da história dos *graph databases*, o que são **grafos**, seus casos de uso e exemplos da linguagem ***Cypher***.

### Quick start

- Clone o repositório.
- Instale o Neo4j ou crie o container Docker usando o comando a seguir, ou, caso use **Docker Compose**, [clique aqui](https://neo4j.com/developer/docker-run-neo4j/).

   `docker run --name testneo4j -p7474:7474 -p7687:7687 -d --env NEO4J_AUTH=neo4j/graph neo4j:latest`
- Crie um arquivo `.env` baseado no `.env.example`. Se tiver usado o código acima, a senha do banco será **graph**.
- Rode `yarn` ou `npm install`.
- Rode `yarn dev` ou `npm run dev` para rodar o app Express em modo de desenvolvimento.
- **OPCIONAL**: Baixe o [*json* do **Insomnia**](https://github.com/rafaelkillua/express-neo4j-example/raw/master/ExpressNeo4jExample_Insomnia_20200805.json) com algumas rotas para facilitar o desenvolvimento.

### Modelagem do projeto

Esse projeto consiste em 3 modelos (**Person**, **Expertise** e **Framework**) e 3 relacionamentos (**IS_TEAMMATE**, **HAS_EXPERTISE** e **REQUIRES_EXPERTISE**).

Todos os modelos tem a propriedade **name**. Os relacionamentos não têm propriedades.

As possibilidades são:
  - `(:Person)    -[:IS_TEAMMATE]->   (:Person)`
  - `(:Person)    -[:HAS_EXPERTISE]-> (:Expertise)`
  - `(:Framework) -[:REQUIRES_EXPERTISE]->      (:Expertise)`

Então, um exemplo de ligação entre **Person** e **Framework** seria:

  `(:Person) -[:HAS_EXPERTISE]-> (:Expertise) <-[:REQUIRES_EXPERTISE]- (:Framework)`

### Mais informações:
- [Neo4j](https://neo4j.com/)
- [Neo4j para desenvolvedores](https://neo4j.com/developer/)
- [Neo4j com Docker](https://neo4j.com/developer/docker-run-neo4j/)
- [Driver Javascript para Neo4j](https://github.com/neo4j/neo4j-javascript-driver)
- [OGM (Object Graph Mapping) em Java](https://github.com/neo4j/neo4j-ogm)
- [OGM (Object Graph Mapping) em Javascript](https://github.com/adam-cowley/neode)
- [Manual do **Cypher**](https://neo4j.com/docs/cypher-manual/4.1/)
- [Cursos online **grátis** oficial Neo4j (com certificado)](https://neo4j.com/graphacademy/online-training/)
- [Sandbox do SGBD online do Neo4j](https://neo4j.com/sandbox/)
- [Nota do Facebook sobre Graph DBs](https://www.facebook.com/notes/facebook-engineering/tao-the-power-of-the-graph/10151525983993920/)

### Contribuições
Quaisquer PRs serão bem vindos!
