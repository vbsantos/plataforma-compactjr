---
Autor: Vinícius Bohrer dos Santos
---

# Design Patterns

[https://pt.wikipedia.org/wiki/Padrão_de_projeto_de_software](https://pt.wikipedia.org/wiki/Padrão_de_projeto_de_software)



## Facade Pattern

fetch -> getFetch

fetch -> axios

não precisa mudar o getFetch

https://www.youtube.com/watch?v=fHPa5xzbpaA

## Factory Pattern

Criar objetos é a especialidade do [Factory Pattern](http://en.wikipedia.org/wiki/Factory_(software_concept)). A grande vantagem desse pattern é que ele reduz a duplicação das tarefas de inicialização em objetos similares, além de permitir abstrair construções que podem ser complexas.

Exemplo simples de uma "fábrica de usuários":

```javascript
/**
 * The User.build factory can be called with two distict signatures:
 * — An object representing the attributes.
 * — Two arguments representing the name and e-mail.
 */
User.build = function(attrs) { // User Factory
	if (arguments.length === 2) {
		attrs = {
        	name: arguments[0],
			email: arguments[1]
        };
    }
	return new User(attrs);
};
```

```javascript
const Animal = (name) => { // Animal Factory
    const animal = {};
    animal.name = name;
    animal.walk = function(){
        console.log(this.name + " walks");
    }
    return animal;
};
```

In a nutshell, if we implement instance creation inside the function itself and don’t require user to use Object.create or new keyword, then we have a factory.

https://www.tutorialspoint.com/design_pattern/factory_pattern.htm

## Observer Pattern

Um método é o "***Subject***" e outros são "***Observers***". "***Subject***" propaga um <u>comando</u> para qqr "***observer***" que queira "ouvir"/interpretar/etc. Os "***observers***" podem variar dependendo do <u>estado</u> atual, pode ter uma lista de "***observers***" para cada <u>estado</u>.

<u>Comando</u> pode ser um **keypress** propagado pelo ***Subject*** para os ***Observers*** que são interpretam e fazem algo com isso. 

Um "***Observer***" pode pegar o **keypress**, checar se as regras do jogo são cumpridas e <u>executar um comando</u>.

Outro "***Observer***" pode mudar o <u>estado do jogo</u> se certar regras forem cumpridas.

https://www.devmedia.com.br/design-patterns-observer/16875

https://www.tutorialspoint.com/design_pattern/observer_pattern.htm

https://www.youtube.com/watch?v=4OLCrClb_So

## Proxy Pattern

Funciona fazendo a ponte entre uma API, podendo fazer o **http request** na API somente quando necessário (sem span) e armazenar valores em uma cache (evitando que erros de conexão apareçam).

Exemplo de Proxy pra uma API de Cryptocurrencies:

https://www.youtube.com/watch?v=SFTpSFQNPts

## Command Pattern

Todos os comandos e metodos da classe tem um "***do***" e "***undo***". Dae o classe em si pode ter um histório de comandos e a opção de "***undo***" que olharia o histórico e rodaria o undo da última função. Usado bastante em editores de texto.

Exemplo de Command para uma calculadora simples:

https://www.youtube.com/watch?v=GQzfF5EMD7o

## Null Object Pattern

Ao invés de sempre testar se um objeto retornado por uma função (de busca no banco de dados, por exemplo) é **NULL**, fazer essa função retornar um ***null object*** no lugar de **NULL** (contendo todos os métodos que o objeto correto teria), o que <u>não geraria erros</u> no código (em princípio).

Por exemplo, ao buscar uma imagem (que não existe) de um banco de dados. Ao invés de gerar um erro, trára uma imagem padrão com todos os métodos que existiriam na imagem correta.

https://www.youtube.com/watch?v=D4Dja5WSZoA

## Decorator Pattern

https://nandovieira.com.br/design-patterns-no-javascript-decorator

## Builder Pattern



## Singleton Pattern

