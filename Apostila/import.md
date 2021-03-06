# @import e @require

Através da diretiva `@import` é possível importar arquivos no seu arquivo principal. Durante o processo de compilação os arquivos importados são unificados gerando um único arquivo CSS. Todas as variáveis ou mixins definidas nos arquivos importados podem ser usados no arquivo principal.

*Observação: Em todos os casos de uso do @import pode ser usado o @require*

Sintaxe:

```
@import 'header.styl'
```

Por padrão a diretiva @import busca por arquivos Stylus, por isso quando se importa arquivos Stylus a extensão é opicional.

Quando usamos o `@import` em um arquivo com a extensão `.css` ele é literal, ou seja ele não inclui e sim escreve. Exemplo:

```
@import 'reset.css'
```

Obviamente será compilado para:

```
@import 'reset.css';
```

Você também pode incluir todos os arquivos de uma pasta usando o caractere `*`. Exemplo:

```
@import 'partials/*'
```

## @import em níveis

Com o Stylus, podemos incluir um arquivo dentro de algum bloco. Suponhamos que você tenha um arquivo `nav.styl` e ele tenha esse conteúdo:

```
ul
	list-style none
	padding 0
	margin 0
	width 100%
	text-align center
	li
		display inline-block
```

Se você quiser incluir ele dentro de um bloco, fica deste modo:

```
nav
	@import 'nav.styl'
```

Aonde será compilado para:

```
nav ul {
	list-style: none;
	padding: 0;
	margin: 0;
	width: 100%;
	text-align: center;
}
nav ul li {
	display: inline-block;
}
```