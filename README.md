﻿![Logo](https://contrato.express/assets/logo-f-84a3e182be013ed38cbedbebe140d39b5027603886746a031c758669b069704a.png)

# iDox - Estag
Olá, se você chegou aqui é porque foi pré selecionado na primeira etapa e está no nivel 2 :D

Faça um fork do projeto e depois que terminar, envie um pull request!

Você pode utilizar:
* Bootstrap ou outros frameworks
* Angular, VueJS ou ReactJS
* Bower, gulp, sass, webpack, less...

Você precisara utilizar seus conhecimentos em:
* Consumir REST Api
* Organização do projeto
* Qualidade do código

A sua tarefa é fazer um projeto consumindo a seguinte API:
https://newsapi.org/

Você pode utilizar a seguinte api key ou gerar uma nova:
77a4f1c173664832a89a7d3cac6b4f0a

Use sua criatividade para exibir as notícias. Pode pesquisar a vontade.
Recomendamos que execute a tarefa em até 4 horas para que possamos avaliar a produtividade.
Não tem problema caso não consiga finalizar o projeto, é só um estágio :D

Boa sorte!

Projeto
----------------------------------------------------------------------------------------
<html>

<head>
<meta charset="UTF-8">
<title>Noticias</title>
<link rel="stylesheet" href="bootstrap.css"></link>
<link rel="stylesheet" href="style.css"></link>
<script src="angular.min.js"></script>
<script src="app.js"></script>
<script src="NoticiasController.js"></script>
</head>

<body ng-app="app" ng-controller="NoticiasController">
	<div class="jumbotron align-center"><h1><b>NOTICIAS</b></h1></div>
	<div class="container">
			<div ng-repeat="n in mostra">
			<a href="{{n.url}}">
					<h1><b>{{n.title}}</b></h1>
					{{n.description}} <br>
					<b>{{n.author}}</b>		
			</a>
			</div>
	</a>
	</div>
</body>

</html>
--------------------------------------------------------------------------------

var app=angular.module('app', []);


--------------------------------------------------------------------------------

.align-center{
	text-align: center;
}

--------------------------------------------------------------------------------

app.controller('NoticiasController', function($scope, $http){
	var link="https://newsapi.org/v1/articles?source=techcrunch&apiKey=77a4f1c173664832a89a7d3cac6b4f0a"
	$http.get(link).then(function(response){
		console.log($http.get(link))
		$scope.mostra=response.data.articles;
	});
});

---------------------------------------------------------------------------------

