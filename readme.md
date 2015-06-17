### Exemplo de Consumo de API com Ionic Framework

Este exemplo simples visa demonstrar como consumir o conteúdo de uma API REST (servida com WordPress, neste caso) para um APP.

Neste exemplo foi usado o projeto base do Ionic, e o código que vem junto foi mantido.

As únicas alterações foram no arquivo `www/templates/tab-dash.html` e `www/js/controllers.js`, mais especificamente no `.controller('DashCtrl', function($scope.....))`. 

Nele, injetamos o $http como dependência, e depois fazemos uma requisição para o endpoint `/posts` da API criada com o plugin WP REST API.

Essa requisição é feita com `$http.get()`, e, atravéz do método `.sucess(function(data){...})`, atrelamos o resultado (que vem na variável `data`) ao `$scope.posts`, o que significa que o conteúdo fica disponível no template que usar o controller em questão, na variável `{{posts}}` .

No HTML, usamos a diretiva `ng-repeat` para fazer um loop no conteúdo da variável `{{posts}}`, sendo que `ng-repeat="post in posts"` indica que cada loop terá uma variável `{{post}}` com o conteúdo daquele loop. Por isso `{{post.title}}` retorna o título `Hello World`, do único post existente em nossa instalação.