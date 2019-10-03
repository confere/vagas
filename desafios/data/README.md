# Data Challenge - Confere

Aqui você terá uma ideia do funcionamento do mercado de integrações com software houses e adquirentes, e poderá aplicar seu conhecimento de programação na prática :)

## Contexto

Várias empresas de software, adquirentes e sistemas de gestão transitam grandes volumes de dados com arquivos padronizados chamados EDI. Esses arquivos são como CSV's, porém com cada linha possuindo definição própria das colunas. Por exemplo, considerando o layout:

```
Registro 0: Header
Posição 1: Tipo do Registro
Posição 2: Data do arquivo (YYYYMMDD)

Registro 1: Venda
Posição 1: Tipo do Registro
Posição 2: Valor da venda
Posição 3: Número Sequencial Único (NSU)
```

O arquivo contendo:
```
0;20191001
1;10550;110
1;20060;120
```

Nos informa que ele foi gerado em `2019-10-01` e possui uma venda de `105,50` (os arquivos possuem os valores monetários em centavos). Também temos outra venda de `200,60` na linha logo abaixo. Esta segunda venda tem um NSU de 120, enquanto a primeira possui o NSU de 110.

## Desafio

Construa um serviço que faça download do arquvivo disponível em um endpoint SFTP, e transforme ele em um array de JSONs. No exemplo acima, o resultado final seria:

```json
[
	{
		"line_type": 0,
		"created_at": "2019-10-01",
	},
	{
		"line_type": 1,
		"transaction_amount": 105.50,
		"nsu": 110
	},
	{
		"line_type": 1,
		"transaction_amount": 200.60,
		"nsu": 120
	}
]
```

1. O arquivo está disponibilizado no seguinte servidor SFTP:
```
Host: sftp.confere.com.br
Port: 22
User: desafio
Password: N2JiYTcwMGYzNTFiYjZmMTE3YjJlYmNk
Home: /confere-data/sftp-users/desafio
```

2. Após baixá-lo, você deverá lê-lo, e fazer a tradução dos valores [seguindo o padrão disponibilizado nesse link](https://docs.google.com/document/d/1wIeA-loc3OVUJTb5O633A1LIOrJZeKHgSb1zUOVuqcc/edit?usp=sharing).

Referir-se ao arquivo de vendas para tradução.

3. Por fim, seu script dever gerar um array de JSON's, conforme descrito no início dessa sessão. Esse array deve ser escrito em um arquivo.

## Funcionamento

O programa deve receber um imput equivalente a:

```
python3 script.py --output arquivo_parseado.json
```

Na chamada acima, ele deve gerar um arquivo chamado `arquivo_parseado.json` com o array de JSONs.

## Restrições
1. O programa deve ser desenvolvido em Python

2. Tente usar as bibliotecas padrões quando possível. O projeto terá pontos extras se utilizar as bibliotecas padrões ao invés de instalar novos pacotes.

3. Crie uma documentação! Um Readme.md com informações sobre o script

## Considerações finais
1. Caso você tenha algum problema com o endpoint ou a documentação, não hestie em perguntar. Meu email é `brenno.flavio@conferecartoes.com.br`

2. O script será avaliado pela escolha de bibliotecas, qualidade do código, passar no linter e code formatter (usamos `flake8` e `black`) e simplicidade

3. Alguns extras que contam pontos a mais:
- Poder escolher entre mostrar o output em tela (stdout) ou em um arquivo
- Adição de Log de execução
- Controle de erros (caso o arquivo venha com algum problema)
- Banco de dados com output do script (pode considar um SQLite por exemplo)

4. Após finalizar, crie um gitub privado e compartilhe o código comigo, ou me envie um `.zip` com o código
