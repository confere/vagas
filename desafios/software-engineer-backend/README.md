# Desafio Software Engineer, Back-end - Confere

Nesse desafio você construirá uma versão super simplificada de um Payment Service Provider (PSP)

## Contexto

Em sua essência um PSP tem duas funções muito importantes:

1.  Permitir que nossos clientes processem transações ("cash-in")
2.  Efetuar os pagamentos dos recebíveis para os nossos clientes ("cash-out")

Neste exemplo, nós teremos duas entidades que representam essas informações:	
-   `transactions`: que representam as informações da compra, dados do cartão, valor, etc
-   `financials`: que representam os recebíveis do cliente 
## Requisitos

Você deve criar os seguintes serviços:
1.  Um serviço deve processar as transações, com as seguintes regas:
	1. O serviço deve seguir o schema a baixo:
	```json
	{
		"value": 100.00, // Valor da transação
		"description": "Bicicleta ZXY Aro 21", // Descrição da transação
		"type": "debit", // Tipo de transação (`debit`, `credit`, `installment_credit`)
		"installments": null, // Número de parcelas, caso seja debito, passar `null`
		"card": {
			"number": "5200555500001234", // Número do cartão
			"expiry": "20/21", // Validade do cartão
			"cvv": "123", // Código de verificação do cartão
			"holder": "Fulano de tal" // Nome do portador do cartão
		}
	}
	```
	2. Como o número do cartão é uma informação sensível, o serviço só pode armazenar e retornar os 4 últimos dígitos do cartão.
2.  Um serviço que retorna todas as transações registradas, permitindo filtros. 
3.  Um serviço deve criar os recebíveis do cliente (`financials`), com as seguintes regras:

	1. Se a transação for feita com um cartão de débito, um recebível deve ser criado:

		1. O recebível deve ser criado com o status = `received` (indicando que o cliente já recebeu esse valor).

		2. O recebível deve ser criado com a data do recebimento (`received_date`) = data da criação da transação `(D + 0)`.

	2. Se a transação for feita com um cartão de crédito à vista, um recebível deve ser criado:

		1. O recebível deve ser criado com o status = `expected`.

		2. O recebível deve ser criado com a data do recebimento (`received_date`) = data da criação da transação + 30 dias`(D + 30)`.

	3. Se a transação for feita com um cartão de crédito parcelado, N recebíveis devem ser criados (sendo N o número de parcelas):

		1. Os recebíveis devem ser criados com o status = `expected`.

		2. Os recebíveis devem ser criados com a data do recebimento (`received_date`) = data da criação da transação + 30 dias * número da parcela `(D + (30 * N))`.

4. No momento de criação dos recebíveis (`financials`) deve ser descontado a taxa da adquirente (chamada de fee)

	* 2,8% para transações feitas com cartão de débito

	* 3,2% para transações feitas com cartão de crédito à vista

	* 3.8% para transações feitas com cartão de crédito parcelado, sendo de 2 a 6 parcelas

	* 4.2% para transações feitas com cartão de crédito parcelado, sendo de 7 a 12 parcelas

5.  Um serviço deve listar todas os recebíveis do cliente (`financial`), permitindo filtros.
6.  Um serviço deve listar o saldo cliente, com as seguintes regas:
	1.  As seguintes informações devem ser apresentadas:
		* Saldo `available` (disponível): tudo que o cliente já recebeu (financials received)
		* Saldo `expected` (a receber): tudo que o cliente tem a receber (financials expected)
	2. O serviço deve permitir filtros.

## Restrições

1.  O serviço deve ser escrito em Node.js
2.  Sinta-se livre para usar qualquere framework.
3.  Usar autenticação JWT
4.  O serviço deve armazenar informações em um banco de dados. Você pode escolher o banco que achar melhor.
5.  O projeto deve ter um README.md com todas as instruções sobre como executar e testar o projeto e os serviços disponibilizados.

## Avaliação

1.  O desafio deve ser enviado para a pessoa da Confere que estiver em contato com você, um link para um repositório do Github
2.  Iremos te avaliar pela arquitetura do serviço, qualidade do código, entendimento das regras de negócio, capricho com o desafio e o quão preparado esse serviço estaria para ser rodado em produção
3.  Depois que corrigirmos o desafio, te chamaremos para conversar com o time, apresentar o desafio e discutir sobre as decisões que você tomou
4.  Achamos que  **1 semana**  é um tempo ok para fazer o desafio, mas sabemos que nem todo mundo tem o mesmo nível de disponibilidade. Portanto, nos avise se precisar de mais tempo, ok?
5.  Boa sorte :)

## Créditos extras

1. Testes `(integração e unitário)`
2. CI/CD
3. Deploy da api em algum serviço de cloud (pode ser usado serviços gratuitos, como o `heroku`, `MLab`, etc)
4. Qualquer outra feature que você achar que se encaixe no projeto!
