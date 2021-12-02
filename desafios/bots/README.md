# Bots Challenge - Confere

Aqui você terá a oportunidade de testar suas habilidades de web scrapping e tratamento de dados usando Python e Selenium!

## Contexto

Na Confere, nós temos um desafio de integração muito grande: dependemos de dados externos para construir nosso produto. Esses dados vem de diversas fontes, e várias são portais de Adquirentes de cartão de crédito.

Assim sendo, nessa vaga, o grande desafio é conseguir extrair informações de sites e portais para consolidar isso nas nossas bases internas.

## Desafio
Constura um Bot usando [Selenium](https://selenium-python.readthedocs.io/) e [Python](https://www.python.org/). Esse bot deverá acessar o site da Bovespa, e consultar algumas informações da Petrobrás. Abaixo está o passo a passo na perspectiva de um usuário, mas você pode pular passos no código se conseguir!

### Passo a passo
1. Abra a url https://www.b3.com.br/pt_br/produtos-e-servicos/negociacao/renda-variavel/empresas-listadas.htm

2. Procure por "Petrobrás"
![Image1](https://imgur.com/TKZYLvg.jpg)

3. Clique em "PETROLEO BRASILEIRO S.A. PETROBRAS"
![Image2](https://i.imgur.com/6Wq7xal.jpg)

4. Procure por "Balanço Patrimonial - Consolidado"
![Image3](https://imgur.com/hJxFnH1.jpg)

5. Pegue os campos da tabela

6. Construa o seguinte dicionário:
```json
{
    "data": "2021-09-30",
    "ativo_imobilizado": 702228000,
    "ativo_total": 924465000,
    "patrimonio_liquido": 309753000,
    "patrimonio_liquido_atribuido_a_controladora": 306252
}
```

7. Use a função `print` para mostar esse dicionário na tela

## Restrições e considerações
1. Você deve usar o `selenium` e o `python3`.

2. Você não precisa seguir o passo a passo que está acima. Retornando o dicionário está ótimo!

3. Utilize o drive de Google Chrome (`chromedriver`) ou o de Firefox (`geckodriver`). Não utilize drivers que funcionam apenas em um sistema operacional

4. Após finalizar, crie um gitub privado e compartilhe o código comigo, ou me envie um `.zip` com o código
