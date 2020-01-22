# Bots Challenge - Confere

Aqui você terá a oportunidade de testar suas habilidades de web scrapping e tratamento de dados usando Python e Selenium!

## Contexto

Na Confere, nós temos um desafio de integração muito grande: dependemos de dados externos para construir nosso produto. Esses dados vem de diversas fontes, e várias são portais de Adquirentes de cartão de crédito.

Assim sendo, nessa vaga, o grande desafio é conseguir extrair informações de sites e portais para consolidar isso nas nossas bases internas.

## Desafio
Constura um Bot usando [Selenium](https://selenium-python.readthedocs.io/) e [Python](https://www.python.org/). Esse bot deverá acessar o site da Bovespa, e consultar algumas informações da Petrobrás. Abaixo está o passo a passo na perspectiva de um usuário, mas você pode pular passos no código se conseguir!

### Passo a passo
1. Abra a url http://www.bmfbovespa.com.br/pt_br/produtos/listados-a-vista-e-derivativos/renda-variavel/empresas-listadas.htm

2. Procure por "Petrobrás"
![Image1](https://i.imgur.com/yJ3f7Lu.png)
![Image2](https://i.imgur.com/tVkPnzr.png)

3. Clique em "PETROLEO BRASILEIRO S.A. PETROBRAS"
![Image3](https://i.imgur.com/OmE2zJA.png)

4. Procure por "Balanço Patrimonial - Consolidado"
![Image4](https://i.imgur.com/mCEEmFa.png)

5. Pegue os campos da tabela

6. Construa o seguinte dicionário:
```json
{
    "ativo_imobilizado": 702228000,
    "ativo_total": 924465000,
    "patrimonio_liquido": 309753000,
    "patrimonio_liquido_atribuido_a_corretora": 306252
}
```

7. Use a função `print` para mostar esse dicionário na tela

## Restrições e considerações
1. Você deve usar o `selenium` e o `python3`.

2. Você não precisa seguir o passo a passo que está acima. Retornando o dicionário está ótimo!

3. Utilize o drive de Google Chrome (`chromedriver`) ou o de Firefox (`geckodriver`). Não utilize drivers que funcionam apenas em um sistema operacional

4. Após finalizar, crie um gitub privado e compartilhe o código comigo, ou me envie um `.zip` com o código
