# MICROSERVICES

+ Configuração do Bucket
+ Implementar o sentry (https://docs.sentry.io/clients/javascript/)
+ Use HTTP Methods & API Routes
+ Use HTTP Status Codes Correctly
+ Use HTTP headers to Send Metadata
+ Pick the right framework for your Node.js REST API (Cors)

# Express x Restfy

+ "Restify exists to let you build "strict" API services that are maintainable & observable." <br />
 http://restify.com/

+ Black-box testing is a method of testing where the functionality of an application is examined without the <br /> knowledge. of its internal structures or workings

+ Documentação da api Swagger (https://swagger.io/)

+ Avaliar uma readequação da api em GraphQL (https://developer.github.com/v3/)

# Benefícios em usar microservices

+ Impõe um nível de modularidade

+ Inicialização mais rápida da aplicação, o que torna desenvolvimento mais rápido.

+ Cada serviço pode ser implementado independentemente de outros serviços.

+ Desenvolvimento mais ágil e facilita avaliar a produtividade e também pode ter vantagens de desempenho.

+ Diminui o compromisso com uma pilha de tecnologia. Um novo serviço pode ser feito em nova pilha tecnológica.

+ Organização: Cada microservice possui um trabalho muito específico e independente

+ Os serviços desacoplados são mais fáceis de refatorar e reconfigurar para servir os propósitos de diferentes <br /> aplicativos (por exemplo, atendendo tanto os clientes da web quanto a API pública).

## Arquitetura para o nosso microservice


Cada área funcional do aplicativo agora é implementada por seu próprio microservice. Além disso, o aplicativo da Web é dividido em um conjunto 
de aplicativos web mais simples

Cada serviço de backend expõe uma API REST e a maioria dos serviços consome API fornecidos por outros serviços

GATEWAY  => As aplicações não tem acesso direto aos serviços do backend. A comunicação é mediada por um intermediário conhecido como
Gateway da API. Ele é responsável por tarefas como balanceamento de carga, armazenamento em cache, controle de acesso, medição de API
e monitoramento, e podem ser implementadas efetivamente usando o NGINX .

Cada microservice é uma mini-aplicação que possui sua própria arquitetura hexagonal consistindo em lógica de negócios e vários adaptadores.
Alguns microservices iriam expor uma API que é consumida por outros microservices ou pelos clientes da aplicação.
Outros microservices podem implementar uma UI na web. Em tempo de execução, cada instância é muitas vezes uma VM em nuvem ou um contêiner Docker.

Cada instância de serviço é um contêiner Docker. Para estar altamente disponível, os contêineres estão sendo executados em múltiplas VMs em nuvem. 
Na frente das instâncias do serviço, existe um balanceador de carga como o NGINX que distribui pedidos em todas as instâncias.
O balanceador de carga também pode lidar com outras preocupações, como cache , controle de acesso , medição de API e monitoramento .

O padrão de arquitetura Microservices afeta significativamente a relação entre o aplicativo eo banco de dados. Em vez de compartilhar um único 
esquema de banco de dados com outros serviços, cada serviço possui seu próprio esquema de banco de dados. Por um lado, essa abordagem está em 
desacordo com a idéia de um modelo de dados em toda a empresa. Além disso, muitas vezes resulta em duplicação de alguns dados. No entanto, ter 
um esquema de banco de dados por serviço é essencial se você deseja se beneficiar de microservices, pois assegura o acoplamento solto. O diagrama 
a seguir mostra a arquitetura do banco de dados para o exemplo de aplicativo.

Cada um dos serviços possui sua própria base de dados. Além disso, um serviço pode usar um tipo de banco de dados mais adequado às suas necessidades, 
a chamada arquitetura de persistência poliglota (polyglot persistence architecture). 