# Essence, Teste Too Seguros, 
# TooSeguros.TesteMarceloCirino | Marcelo dos Santos Cirino
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
