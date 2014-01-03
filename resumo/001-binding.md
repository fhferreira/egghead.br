# AngularJS - Binding

### [Post Original](http://www.thinkster.io/pick/0apUP9HK4G/angularjs-binding)

Vamos começar configurando uma `div` com um atributo `ng-app`

```html

<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>AngularJS Tutorials</title>
	<link rel="stylesheet" href="vendor/foundation.min.css">
</head>
<body>
	
	<div ng-app="">

	</div>

	<script type="text/javascript" src="vendor/angular.js"></script>
</body>
</html>

```

Este atributo diz que este elemento (a div) e tudo dentro dele pertence a este app. [Binding](http://docs.angularjs.org/api/ng.directive:ngBind) pode ser representado no AngularJS usando a diretiva `ng-bind` ou com chaves duplas. Nós podemos testar isto tentando algumas expressões em nossa `div`:

```html

<div ng-app="">
	{{ 1 + 1 }}
	{{ "john" + "lindquist" }}
	{{ 3 * 3 }}
</div>

```

Você deve manter a lógica na View de forma mínima. Binding é mais útil quando você cria um input ou um caminho para o usuário para interagir com o sua app. Vamos criar um input com um atributo `ng-model` que é configurado para "data.message" e então ligado dentro de nossa div.

```html

<div ng-app="">
	<input type="text" ng-model="data.message">
	<h1>{{ data.message }}</h1>
</div>

```

Agora quando nós carregamos a página, se nós começamos a escrever no campo input, você vai ver que o modelo foi vinculado e nosso texto vai começar a mostrar o que escrevermos. Se nós adicionarmos `'+ "world"'` dentro da *binding*, nós obteremos "hello world" quando nós atualizarmos e escrevermos *hello* dentro do input.

```html

<div ng-app="">
	<input type="text" ng-model="data.message">
	<h1>{{ data.message + " world"}}</h1>
</div>

```

Nós podemos ficar um pouco loucos e criar uma div com um atributo `class` igual a "{{data.message}}" e dizer "Envolvido com um componente Foundation".

```html

<div ng-app="">
	<input type="text" ng-model="data.message">
	<h1>{{ data.message }}</h1>
	<div class="{{data.message}}">
		Envolvido com um componente Foundation.
	</div>
</div>

```

Agora podemos escrever as classes do foundation dentro da caixa input, como "panel", "alert-box" e "label", e veremos que isso de fato altera a classe da div e a div recebe um estilo diferente. Podemos manipular um monte de DOM usando binding, não somente apresentando simples textos.