# Desafio Software Engineer, Mobile Developer - Confere

Nesse desafio você construirá uma versão super simplificada de um Gerenciador de produtos.

## Especificação

 - O aplicativo deverá conter uma CRUD (Create, Read, Update, Delete) de produtos, os mesmos deverão ser persistidos em uma banco local no aplicativo, de maneira que mesmo que o aplicativo seja encerrado, ao abrir novamente, o mesmo deverá ser capaz de pegar a listagem atual de produtos;
 - Na listagem de produtos, deverá ser apresentado os seguintes campos:
    - Imagem
    - Nome
    - Preço
    - Preço de promoção (se disponível)
- A listagem de produtos, deverá retornar os produtos ordenados de forma alfabética;
-  Na criação e edição de produtos deverá ser apresentados os seguintes campos para preenchimento:
    - Nome (String - obrigatório) 
    - Preço (double -  obrigatório) 
    - Preço de promoção (double)
    - Percentual de desconto (double)
    - Disponível para venda (bool)
-   Ao salvar, deverá ser validado a obrigatoriedade dos campos e em caso de não cumprimento de alguma regra, deverá ser apresentada uma mensagem de erro em baixo do campo e o mesmo deverá ser destacado em vermelho;
- Ao salvar um produto (criação ou edição) deverá ser redirecionado para a listagem de produtos, com a mesma atualizada e apresentar um Snackbar, informando o sucesso na operação;
- Nesse primeiro momento, não será necessário a adição ou edição de fotos em um produto. Apenas será apresentado na listagem, para aqueles que já possuem;
- Na edição de um produto, deverá conter um botão para exclusão do produto, que ao ser clicado, será apresentado um Dialog para confirmação da ação, em caso de afirmação, o mesmo deverá ser deletado do banco e a listagem ser atualizada. apresentando uma Snackbar, informando o sucesso na operação;

## Requisitos

-   Deverá ser desenvolvido utilizando Flutter;
-   Deverá utilizar BloC para gerência de estado;
-   O código fonte deverá ser disponibilizado em um repositório do Github e enviado via e-mail para a pessoa da Confere que está em contato com você;

## Pontos Extras

-   Crie uma barra de busca;
-   Na listagem, adicione a funcionalidade de excluir um item utilizando o plugin [https://pub.dev/packages/flutter_slidable](https://pub.dev/packages/flutter_slidable)
-   Adicione um ícone para seu aplicativo e disponibilize ele como APK;
-   Adicione os campos restantes do json, nos formulário de edição e adição;
-   Utilize Hero, para trazer mais vida ao seu aplicativo;

## Avaliação
Iremos te avaliar pela arquitetura do serviço, qualidade do código, capricho com o desafio e o quão preparado esse aplicativo estaria para ser rodado em produção.

Depois que corrigirmos o desafio, chamaremos você para conversar com o time, apresentar o desafio e discutir sobre as decisões que você tomou.

Achamos que 1 semana é um tempo ok para fazer o desafio, mas sabemos que nem todo mundo tem o mesmo nível de disponibilidade. Portanto, nos avise se precisar de mais tempo, ok?

Boa sorte :)
