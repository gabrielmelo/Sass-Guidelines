# Sass Guidelines
Boas práticas para o desenvolvimento front-end.
O objetivo deste documento não é estabelecer uma regra para escrita do CSS. Entretanto, buscamos definir diretrizes de código - uma maneira de escrever, afim de promover consistência no desenvolvimento individual e em equipe, de forma que o código se torne legível, elegante e rápida manutenção.


## Referências
- [CSS Guideline](http://cssguidelin.es/)
- [Sass Guideline](https://sass-guidelin.es/)


## Sintaxe e Formatação

- Utilize quadro(4) espaço para indentação, no tabs;
- 80 caracteres por coluna;
- Multi-linhas CSS;
- Utilizar espaços em branco entre regras de 

```
// Sempre
.foo {
	display: block;
	overflow: hidden;
	padding: 0 1em;
}

// Nunca
.foo {
	display: block; overflow: hidden;
	
    padding: 0 1em;
}

```

### Strings (Melhorar)
Strings devem são sempre envolvidas com aspas simples ('') em Sass


```
// Sempre
$direction: 'left';

// Nunca
$direction: left;
```

### URLs
URLs devem ser citadas também envolvidas com aspas simples ('')

```
// Sempre
.foo {
	background-image: url('/images/kittens.jpg');
}

// Nunca
.foo {
	background-image: url(/images/kittens.jpg);
}

```


## Numbers
Número é um tipo de dados que inclue tudo, desde número sem unidade a comprimentos, duração, frequência, ângulos e etcs.

### Zeros
```
// Sempre
.foo {
	padding: 2em;
	opacity: 0.5;
}

// Nunca
.foo {
	padding: 2.0em;
	opacity: .5;
}
```

### Unidades

Quando for utilizar valores relacionados a cumprimentos, um valor 0 não deve ter uma unidade.

```
// Sempre
$length: 0;

// Nunca
$length: 0em;
```

Para adicionar uma unidade para um número, you tem que multiplicar este número por 1 unidate. Exemplo:

```
$value: 42;

// Sempre
$length: $value * 1px;

// Nunca
$length: $value + px;
```

Para remover a unidade de uma valor, você tem que dividí-lo por uma unidade de seu tipo. Exemplo: 

```
$length: 42px;

// Sempre
$value: $length / 1px;
// -> 42

// Nunca
$value: str-slice($length + unquote(''), 1, 2);
```

## Cálculos

Cálculo numérico deve sempre ser envolvido em parentes.

```
// Sempre
.foo {
 	width: (100% / 3);
}

// Nunca
.foo {
 	width: 100% / 3;
}
```

## Colors
