### Exemplo de Consumo de API com Ionic Framework

Este exemplo simples demonstra o consumo do conteúdo de uma API REST (servida com WordPress, neste caso) para um APP.

Neste exemplo usa o projeto base do Ionic, e o código que vem junto foi mantido.

As únicas alterações foram nos arquivos: 

- `www/templates/tab-dash.html`
- `www/js/controllers.js` (mais especificamente no `.controller('DashCtrl', function($scope.....))`). 

### As Alterações:

#### Javascript:
1. Injetamos no controller o `$http` como dependência
2. Requisição para o endpoint `/posts` da API criada com o plugin WP REST API. (`http://localhost/MeuWordPress/wp-json/posts`)

- Essa requisição é feita com `$http.get()`
- usando o método `.sucess()`, executamos uma função que recebe os dados no parâmetro *data*. 
- Ela define `$scope.posts = data`, o que significa que o conteúdo daquela url da API ficará disponível no template que usar o controller `DashCtrl`, mais precisamente na variável `{{posts}}` .

#### Html: 

- Usamos a diretiva `ng-repeat` para fazer um loop na variável `{{posts}}`
-  `ng-repeat="post in posts"` indica que, para cada item da {{posts}},será criada uma variável `{{post}}`
- `{{post.title}}` retorna o título de cada post retornado na API
-  `Hello World`, é o único post existente em nossa instalação.

## Para usar este repositório:

- Tenha o NodeJS Instalado

- Instale o Ionic (`npm install -g ionic`) e o Bower (`npm install -g bower`)

- Baixe e descompacte o Repositório (melhor clonar né hehe)

- Na pasta raíz do projeto rode `npm install`, depois `bower install` e por último `ionic serve`

### CheatSheet do WorkShop no WordCamp Belo Horizonte 2015:

- http://pt.slideshare.net/romulozoch/cheatsheet-workshop-criando-apps-multidispositivos-e-servindo-contedo-com-wordpress