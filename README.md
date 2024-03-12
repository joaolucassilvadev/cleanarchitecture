Pontos importantes sobre a Arquitetura clen 

FORMATO QUE O SOFTARE TERÁ: Bom para começarmos todo software precisa ter um projeto inicial para entender como ele vai ser
como um predio em si, todo predio tem um projeto inicial para podermos começar a construção.

DIVISÃO DE COMPONENTES:Bom precismos ter as divisões bem claras, para podermos dividir todos os componentes do software. Tudo preto no branco

COMUNICAÇÃO DE COMPONENTES: Certo após o principio dos componentes precisamos a comunicação desses componentes, vamos supor que cada componentes
é um andar e que todos foram divididos,agora como vamos ter acesso a esses componentes?, pela comunicação, onde são escas, elevadores ou rotas. 

Arquitetura descente vai me ajudar a desenvolver: precismos arquitetar sempre o desenvolvimento do softare, saber como vamos fazer cada coisa dele do inicio ao fim. 

OBJETIVOS DE UMA BOA ARQUITETURA: O objetivo principal de uma arquitetura boa é dar suporte ao ciclo de vida do sistema. Uma boa arquitetura torna o sistema facil de
entender, escalonas e fazer manutenção. O objetico final é minimizar o custo de vida util do sistema e maximizar a produtividade do programador. 

frameworks, banco de dados,apis, não devem imapactar nas use cases ou regras de negocios. 

O QUE É DDD: Não sei explicar direito ainda. 


Use cases: Bom os casos de uso devem ter clareza no que estão fazendo, por exemplo o caso de uso deve demostra por si proprio o que ele esta fazendo
primeiramente construimos os casos de uso e depois pensamos nos detalhes, como por exemplo banco, framwork e demais. 
Os use cases não devem ter uma unica responsabilidade, para não ferir o principio de responsabilidade unica.

LIMITES ARQUITETURAIS: Bom tudo que não impacta diretamente nas regras de negocio não deve estar em um limite arquitetural diferente. 
Por exemplo o banco de dados ou frontend não devem afetar a regra de negocios e todos eles devem estar em camadas diferentes da minha regra de negocios. 

Input vs Output: No final do dia tudo se resumo a um input que retorna um output
ex: vamos criar um pedido(dados do pedido = input) 
pedido criado(dados de retorno do pedido output) 
vamos simplificar o raciocinio ao criar um software sempre pensando em input e output.
aula 256

DTO: bom o data transfer object ajuda a trafegar os dados entre os limites arquiteturais, o dto é um objeto anemico ele não possui comportamento, ele não tem uma regra de negocios em si, ele é somente dados.Geralmente cada use case possui um dto diferente aula 257

Presenters: Bom os presenters são objetos de tranformação, ele tranforma os dados do DTO para o formato correto de entrega de resultados, os formatos de entrega são os seguintes, json, xml,csv, protobuf, se quisermos determinar com qual tipo vamos retornar nosso objeto podemos utilizar presenters. aula 258

Entities:Bom o entitie é a identidade de um um objeto, por exemplo as entities são as entidades de um sistema

NOSSO OBJETIVO:Bom nossa regra de negocio é pegar o preço do produto mais a taxa e calcular o preço final, porém quando rodamos o projeto em um unico binario ele vai funcionar como um web service e subir um servidor graphql e um grpc
COMEÇANDO PROJETO: bom primeiramente vamos destrinchar as pastas e entender o que cada uma faz. primeiramente começamos com a pasta internal: é onde temos nosso projeto, é onde fica o coração das nossas implementações. Dentro da pasta internal existe a pasta entity,event, infra e usecase. 
Vamos começar com o entity a qual possui nossa regra de negocio, dentro da nossa pasta entity existe o order.go, bom o order.go tem nossa regra de negocios.

