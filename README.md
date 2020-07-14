# Essence, Teste Too Seguros, 
# TooSeguros.TesteMarceloCirino | Marcelo dos Santos Cirino


1- EXPLIQUE COM SUAS PALAVRAS O QUE É DOMAIN DRIVEN DESIGN E SUA IMPORTÂNCIA NA ESTRATÉGIA DE DESENVOLVIMENTO DE SOFTWARE.

DDD é uma prática de desenvolvimento de software onde o foco principal é o negócio (Dominio), Eric Evans em seu livro compilou diversas práticas, padrões e abordagens para um desenvolvimento de software de aplicações complexas, visando com isso uma forma de melhorar a comunicação entre desnvolvedores, analistas de negócios, clientes, etc. Assim fazendo com o que o software por si só seja autodescrito, todos entendem perfeitamente os termos, o codigo expressa exatamente o que a aplicação foi criada para fazer, divide as resposabilidades em contextos menores para diminuir a complexidade, cada contexto deve fazer exatamente o que ele se destina a resolver.

2 - EXPLIQUE COM SUAS PALAVRAS O QUE É E COMO FUNCIONA UMA ARQUITETURA BASEADA EM MICROSERVICES. EXPLIQUE GANHOS COM ESTE MODELO E DESAFIOS EM SUA IMPLEMENTAÇÃO.

A arquitetura de microserviços tem com definição ser uma parte pequena de uma solução altamente especializada, ou seja que faça somente uma coisa, ela funciona com a quebra de uma solução em varias partes pequenas que são independentes, cada microserviço pode ter sua propria técnologia o quer ajuda muito em ter uma tecnologia otima para aquele determinado problema a ser resolvido, uma equipe especializa em determinada parte do negocio tambem é uma outra vantagem. A grande vantagem de trabalhar com esse modelo é escalabilidade, é possivel escalar um ponto especifico que necessita po algum motivo sazional naquele momento precisar de mais recursos. O grande desafio no meu ver fica por conta das integrações entre esses diversos serviços pois eles se comunicam entre si, e esse gernciamento dessas integrações no meu ver são as partes mais desafiantes desse modelo.

3- EXPLIQUE QUAL A DIFERENÇA ENTRE COMUNICAÇÃO SINCRONA (HTTP) E ASSINCRONA (MSMQ) E QUAL O MELHOR CENÁRIO PARA UTILIZAR UMA OU OUTRA.

Comunicação sincrona é aquele em que você envia uma requisição e fica conectado aguardando uma resposta, já a assincrona é desconectada você envia sua requisição e não necessariamente obtem sua resposta imediatamente. Comunicação sincrona é mais indicada em cenários em que você precisa da resposta imediatamente, como algo em real time onde não pode haver uma inconsitencia eventual, já o assincrono seria para cenários em que você não necessita exatamente de uma resposta imediata uma compra com cartão de crédito por exemplo a compra é efetuada e a resposta da aprovação não necessariamente vem no mesmo momento, o usuário é notificado posteriormente sobre o processamento do mesmo

------------------------------------------------------------------------------------

Para executar o projeto de teste, utilize o Visual Studio 2017, abrindo a solution TooSeguros.TesteMarceloCirino.sln
A solution é composta pelos projeto:
- TooSeguros.TesteMarceloCirino.Api
- TooSeguros.TesteMarceloCirino.Domain	
- TooSeguros.TesteMarceloCirino.Infra
- TooSeguros.TesteMarceloCirino.Test.Integration
- TooSeguros.TesteMarceloCirino.Test.Unit



Recursos utilizados:
- Asp.Net Core 2.1
- AutoMapper
- Swashbuckle.AspNetCore (Swagger)


Para os testes integrados (teste do WebAPI):
- luentAssertions
- Microsoft.AspNetCore.Mvc.Testing
- Microsoft.AspNetCore.TestHost

- xUnit
- xunit.runner.visualstudio
- xunit.runner.console


Execução dos Teste:
----------------------

Os testes podem ser executados por:
- Test Explorer do Visual Studio.
- Executando o xUnit via PowerShell
- Através do Postman, no repositório, encontra-se arquivo de importação com os endpoits configurados (Essence.TesteMarceloCirino.TooSeguros.postman_collection.json)
- Através do Swagger: http://localhost:1040/swagger/

Adicionais:
--------------------
Também em anexo os documentos com as respostas das perguntas e o currículo formatado.


Pradão chamada endpoint (/Conta/EfetuaLancamento) de operação crédito/débito:
Exemplo para o teste de operação Crédi/Débito:
OBS.: atributo tipoOpercao 
                           
    1 -> crédito [crédito conta origem, débito conta destino], 
     
    2 -> débito [débito conta origem, crédito conta destino]


JSON:

{
  "contaOrigem": {
    "banco": "Banco Santander",
    "agencia": 1020,
    "contaNumero": 123456,
    "digito": 4,
    "tipo": 1,
    "saldo": 2300
  },
  "contaDestino": {
    "banco": "Banco Santander",
    "agencia": 1020,
    "contaNumero": 789012,
    "digito": 2,
    "tipo": 1,
    "saldo": 1000
  },
  "tipoOpercao": 1,
  "valor": 250
}
