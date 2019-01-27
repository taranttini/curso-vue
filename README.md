# Curso Básico de Vue (em desenvolvimento...)
Curso básico apresentando um pouco do que, e criando projeto de estudo

### objetivo

- criar planejamento do curso, e definir o que será explanado
- a ideia é apresentar cada seção do curso em 10 minutos, se ultrapassar, deverá ser feita uma quebra do vídeo/conteúdo, devido a limitação dos 10 minutos.
- usar dados da fonte oficial vuejs.org
- pesquisar conteúdo de entusiatas de vuejs
- aplicar exemplos 

---

## O que é Vue?

## Como usar o Vue?

Podemos usar o vue js simplesmente fazendo o download o arquivo vue.js localizado em https://br.vuejs.org/js/vue.js e depois acrescentar o uso da tag ```<script src="caminho do arquivo vue.js"></script>``` dentro do seu arquivo html.

Podemos usar o vue js fazendo a referência a uma **CDN** (Content Delivery Network - Rede de Distribuição de Conteúdo), que seria um servidor que armazena conteúdo em cache (em memória), diversos servidores espalhados pelo mundo, e quando solicitamos um conteúdo (arquivo) ele tenta retornar esse dado do servidor mais próximo a nós, fazendo ser bem rápido suas respostas ao conteúdo solicitado. Mas seria parecido com o modo anterior, tag ```<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.js"></script>``` dentro do seu arquivo html.

Para aplicações de grande escala (muitos arquivos, muitas linhas de código), é recomendado o uso do vue através do **NPM** (Node Package Manager - Gerenciador de Pacotes do Node), que é uma ferramenta de linha de comando que nos ajuda a instalar diversas bibliotecas que possam ser úteis em nosso projeto, e também inclui empacotadores de módulos tais como ***[Webpack](https://webpack.js.org/)*** ou ***[Browserify](http://browserify.org/)*** . Exemplo de uso do npm ```npm install vue``` 

Além do **[CLI oficial](https://github.com/vuejs/vue-cli)**, outra ferramenta de linha de comando, que permite através de poucos comandos criar toda a estrutura de um grande projeto vue, permite criar o projeto para ambiente de desenvolvimento ou produção, e com toda estrutura para realizar testes unitários ou de toda a aplicação, além de plugins para minimizar o código, hotreload (que ao salvar o arquivo ao qual editamos, já podemos ver o resultado em tempo real), validações de erros, entre tantas outras configurações. 

### Exemplo de código

```
arquivo: index.html
``` 

```html
<html>
<head>
  <title>Exemplo, olá mundo Vue</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.js"></script>
</head>

<body>
  <div id="app">
    {{ mensagem }}
  </div>

  <script>
    var app = new Vue({
      el: '#app',
      data: {
        mensagem: 'Exemplo, olá mundo Vue!'
      }
    })
  </script>
</body>
</html>
```

---
## Variáveis

Variáveis são extremamente importantes durante o desenvolvimento de programas, apps, sites e etc, pois através das variáveis alocamos um espaço na memória do computador e guardamos valores para usar posteriormente, esses valores podem ser números, texto, resultado de algum cálculo, imagens ou até documentos, por esse motivo as variáveis são importantes no desevolvimento.
As variaveis em javascript são **"case-sensitive"**, isso quer dizer que uma variável chamada ```nome``` é diferente de outra chamada ```Nome``` ou ```NOME```, e por recomendação devemos utilizar somente letras, números e o caracter "sublinhado" "\_", em alguns casos utilizamos o "cifrão" "$", mas para começar o nome da variável jamais devemos iniciar ela com algum número no nome.

```javascript
  var app = new Vue({
    el: '#app',
    data: {
      variavel_texto: 'texto', //variavel tipo texto'
      variavel_numero_inteiro: 1, //variável tipo número inteiro
      variavel_ponto_flutuante: 1.2345, //variável tipo ponto flutuante / decimal
      variavel_boleana: true, //variável tipo boleana
      variavel_vetor: [1,2,3], //variável tipo vetor
      variavel_objeto: {nome:'usuario', idade: 10}, //variável tipo objeto
      variavel_nula: null, //variável tipo nula
      variavel_indefinida: undefined, //variável tipo indefinida
    }
  })
```

No javascript puro, ou vanilla js, criamos as variáveis usando por exemplo:

- usando o **var** seguido do nome da variável, sinal de igual e depois o valor atribuído
```javascript
  var nome_variavel = 'valor da variável' // texto
  var outra_variavel = 123 // numero
```

- usando o **let** seguido do nome da variável, sinal de igual e depois o valor atribuído, *let* quer dizer que a variável poderá receber um valor ao qual irá modificar durante a execução do seu código
```javascript
  let nome_variavel_let = 'sou uma variavel que muda de valor' // texto
  let outra_variavel_let = false // boleana
 ```

- usando o **const** seguido do nome da variável, sinal de igual e depois o valor atribúido, o *const* quer dizer que a variável não poderá modificar o seu valor durante a execução do seu código
```javascript
  const nome_variavel_const = 'sou uma variavel que nao muda de valor' // texto
  const outra_variavel_const = [1, 2, 3, 4] // vetor
```

> o ***let*** e o ***const*** são palavras chaves recentes no mundo javascript, elas foram incluídas no **[ECMAScript 2015](https://pt.wikipedia.org/wiki/ECMAScript)**
 
No vue js, podemos fazer uso das variáveis acima apresentadas dentro de métodos, mas elas também são apresentadas dentro do objeto ou da função/método `'data'`:

```javascript
...
data() {
  return {
    variavel_a: 1,
    variavel_b: 'nome',
    ...
  }
},
...
```
### Variáveis do tipo texto

São variáveis do tipo texto, quando setamos o valor a ela usando valores entre aspa simples `'valor exemplo'` ou entre aspa dupla `"valor exemplo"`.

>Elas são conhecidas como ***"string"***

***exemplos:***
```javascript
var usuarioPrincipal = 'taranttini';
var usuario_secundario = 'taranttini';
var email = 'taranttini@email.com';
var senha = '123456';
var data_nascimento = '01-01-1900';
var mensagem_inicial = 'olá eu sou uma mensagem de boas vindas, ao acessar o novo sistema que está sendo construido';
```

### Variáveis do tipo número inteiro

São variáveis do tipo número interio, quando setamos o valor de números sem o uso das aspas.

>Elas são apresentadas com ***"integer"***

***exemplos:***
```javascript
var numero_dez = 10;
var numero_negativo = -50;
var ano2000 = 2000;
var dia_1 = 1;
var numero_grande = 123456790;
var numero_maximo_seguro = 9007199254740991;
```

### Variáveis do tipo ponto flutuante / decimal

São variáveis do tipo ponto flutuante, quanto setamos valores com um `'ponto' .` juntamente com os números.

>Elas são conhecidas como ***"float"***

***exemplos:***
```javascript
var valor_pi = 3.14159265359;
// diferente do modelo brasileiro de números, 
// o decimal é utilizado através do ponto 
var dez_reais_e_cinquenta_centavos = 10.50; 
var mil_e_vinte_centavos = 1000.20; 
// diferente do modelo brasileiro de números,
// a milhar não se usa pontuações
var dez_mil_e_um_centavo = 10000.01;
```

### Variáveis do tipo boleana

São variáveis do tipo boleana, quando setamos valores `true` ou `false`, no caso verdadeiro ou falso, ligado ou desligado, sim ou não;

>Elas são conhecidas como ***"boolean"***

```javascript
var verdadeiro = true;
var falso = false;
var ligado = 1; // 1 também pode ser considerado como verdadeiro
var desligado = 0; // 0 também pode ser considerado como falso
```

### Variáveis do tipo vetor

São variáveis do tipo vetor, quando setamos valores entre `'colchetes' [ ... ]`, e dentro dele colocamos inteiros, texto, boleanos, outros vetores, objetos, ponto flutuante, o vetor não precisa receber somente valores do mesmo tipo, eles podem ser variados.

>Elas são conhecidas como ***"array"***

```javascript
var vetor_de_internos = [1,2,3,4];
var vetor_de_boleanos = [true, false, false, true];
var vetor_de_vogais = ['a','e','i','o','u']; 
var vetor_misturado = [1,true,'a',-10,'diversos'];
```

### Variáveis do tipo objeto

São variáveis do tipo objeto, quanto setamos valores entre `'chaves' { ... }`, e dentro dele definimos, parametros e valores, esses valores podem ser inteiros, texto, boleanos, vetores, outros objetos, ponto flutuante, nula ou indefindo. O objeto pode conter 0 ou inúmeros parametros com valores.

```javascript
var objeto_pessoa = {
    nome: 'taranttini',
    site: 'http://github.com',
    ano: 2019,
    mes: 1
};
var objeto_data = { dia: 27, mes: 1, ano: 2019 };
var objeto_documento = { tipo: 'rg', numero: 121231230, valido: true };
var objeto_vaziu = {};
```

>Elas são conhecidas como ***"object"***

### Variáveis do tipo nula

São variáveis do tipo nula, quando elas recebem o valor `null`, usamos ela para limpar a variável, quando por exemplo tinhamos um valor qualquer, e queremos limpar esse valor, ai setamos o `null`.

```javascript
var variavel_nula = null;
var outra_variavel_nula = null;
var nome = 'taranttini';
// agora vamos limpar a variável nome
nome = null;
```

>Elas são conhecidas como ***"null"***

### Variáveis do tipo indefinida

São variáveis do tipo indefinida, quando criamos uma varíavel e não setamos valor algum para ela, ou quando setamos ela com o valor `undefined`, nesse caso queremos dizer que o valor da varíavel é indefinido nesse momento de código.

```javascript
var variavel_indefinida_nao_setada;
var variavel_indefinida = undefined;
// vamos criar um objeto, e tentar localizar uma propriedade;
var pessoa = {};
pessoa.nome; // nesse caso ao tentar chamar o nome da pessoa, ela será considerada "undefined", pois em momento algum definimos o nome a ela.
```

>Elas são conhecidas como ***"undefined"***

---

## Métodos
...
