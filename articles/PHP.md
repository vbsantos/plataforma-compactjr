# PHP

## Introdução

PHP: Hypertext Preprocessor (**PHP**) is a free, highly popular, open source scripting language. PHP scripts are executed on the **server**.

Just a short list of what PHP is capable of:

- Generating dynamic page content
- Creating, opening, reading, writing, deleting, and closing files on the server
- Collecting form data
- Adding, deleting, and modifying information stored in your database
- controlling user-access
- encrypting data

> PHP has enough power to work at the core of **WordPress**, the busiest blogging system on the web. It also has the degree of depth required to run **Facebook**, the web's largest social network!

### PHP tags

A PHP script starts this way:

```php
<?php
  // PHP code goes here
?>
```

Here is an example of a simple PHP file. The PHP script uses a built in function called "**echo**" to output the text "Hello World!" to a web page.

```php+HTML
<html>
  <head>
    <title>My First PHP Page</title>
  </head>
  <body>
  <?php
    echo "Hello World!";
  ?>
  </body>
</html>
```

> PHP statements end with **semicolons (;)**.

You can also use the shorthand PHP tags, <? ?>, as long as they're supported by the server.

```php+HTML
<?
  echo "Hello World!";
?>
```

> However, **\<?php ?>**, as the official standard, is the recommended way of defining PHP scripts.

HTML markup can be added to the text in the **echo** statement.

```php+HTML
<?php
   echo "<strong>This is a bold text.</strong>";
   //comentarios
   /*
     This is a multi-line comment block
     that spans over multiple lines
   */
?>
```

![img](https://api.sololearn.com/DownloadFile?id=2782)

## Variáveis

A PHP variable starts with a dollar sign (\$), which is followed by the name of the variable.

```php
$variable_name = value;
```

Rules for PHP variables:

- A variable name must start with a letter or an underscore
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and \_ )
- Variable names are case-sensitive ($name and $NAME would be two different variables)

**For example:**

```php
<?php
   $name = 'John';
   $age = 25;
   echo $name;

  // Outputs 'John'
?>
```

> PHP automatically converts the variable to the correct data type, depending on its value.
> Unlike other programming languages, PHP has no command for declaring a variable. It is created the moment you first assign a value to it.

### Constants

To create a constant, use the **define()** function:

```php
define(name, value, case-insensitive)
```

Parameters:
**name**: Specifies the name of the constant;
**value**: Specifies the value of the constant;
**case-insensitive**: Specifies whether the constant name should be case-insensitive. Default is **false;**

```php
<?php
  define("MSG", "Hi SoloLearners!");
  echo MSG;

   // Outputs "Hi SoloLearners!"
?>
```

> No dollar sign (\$) is necessary before the constant name.

### Data Type

Data types supported by PHP: **String**, **Integer**, **Float**, **Boolean**, **Array**, **Object**, NULL, Resource.

> You can join two strings together using the dot ( .) concatenation operator.
> For example: **echo $s1 . $s2**

### Variable Scope

PHP's most used variable scopes are **local**, **global**.
A variable declared outside a function has a **global scope**.
A variable declared within a function has a **local scope**, and can only be accessed within that function.

The **global** keyword is used to access a global variable from within a function.

```php
<?php
  $name = 'David';
  function getName() {
    global $name; //global keyword
    echo $name;
  }
  getName();

  //Outputs 'David'
?>
```

### Variable Variables

With PHP, you can use one variable to specify another variable's name.

```php
<?php
  $a = 'hello';
  $hello = "Hi!";
  echo $$a;

  // Outputs 'Hi!'
?>
```

> **\$\$a** is a variable that is using the value of another variable, **\$a**, as its name. The value of **\$a** is equal to "hello". The resulting variable is **\$hello**, which holds the value "Hi!".

## Operadores

```php
<?php
  $num1 = 8;
  $num2 = 6;

  //Addition
  echo $num1 + $num2; //14

  //Subtraction
  echo $num1 - $num2; //2

  //Multiplication
  echo $num1 * $num2; //48

  //Division
   echo $num1 / $num2; //1.33333333333

   $x++; // post-increment
   $x--; // post-decrement
   ++$x; // pre-increment
   --$x; // pre-decrement
?>
```

### Comparison Operators

Igual JavaScript:

![img](https://api.sololearn.com/DownloadFile?id=2367)

### Logical Operators

![img](https://api.sololearn.com/DownloadFile?id=2368)

## Arrays

```php+HTML
<?php
    $people = array("Alice","Marcus","Eduardo");
 print_r($people) // Array ([0] => Alice [1] => Marcus [2] => Eduardo)
?>
```

## Loops

```php+HTML
<?php
 foreach ($people as $person) {
        echo $person . ' ';
    }
 // Alice Marcus Eduardo
?>
```

## Forms (fora do curso)

index.html

```php+HTML
<html>
    <head>
        <title>Hello World</title>
    </head>
    <body>

        <form action="process.php" method="post">
            <p>Enter your name:</p>
            <input name="name" type="text">
            <input type="submit">
        </form>

    </body>
</html>
```

process.php

```php+HTML
<html>
    <head>
        <title>Hello World</title>
    </head>
    <body>

        <?php
         $name = $_POST["name"];
         echo "Hello, " . $name
        ?>

    </body>
</html>
```

## Functions

```php
function functionName() {
    //code to be executed
}
```

A function name can start with a letter or an underscore, but not with a number or a special symbol.

> Function names are NOT case-sensitive.

## Predefined Variables

PHP's superglobal variables are $\_SERVER, $GLOBALS, $\_REQUEST, $\_POST, $\_GET, $\_FILES, $\_ENV, $\_COOKIE, \$\_SESSION.

\$\_SERVER is an array that includes information such as headers, paths, and script locations. The entries in this array are created by the web server.

```php
<?php
//$_SERVER['SCRIPT_NAME'] returns the path of the current script
echo $_SERVER['SCRIPT_NAME'];
//Outputs "/somefile.php"
echo $_SERVER['HTTP_HOST'];
//Outputs "localhost"
$host = $_SERVER['HTTP_HOST'];
$image_path = $host.'/images/';
require 'config.php';
echo '<img src="'.$image_path.'header.png" />';
?>
```

> The path to your images is now dynamic. It will change automatically, based on the Host header.

![img](https://api.sololearn.com/DownloadFile?id=2378)

### FORMS

The purpose of the PHP superglobals **\$\_GET** and **\$\_POST** is to collect data that has been entered into a form.

```php
<form action="first.php" method="post">
  <p>Name: <input type="text" name="name" /></p>
  <p>Age: <input type="text" name="age" /></p>
  <p><input type="submit" name="submit" value="Submit" /></p>
</form>
```

The **action** attribute specifies that when the form is submitted, the data is sent to a PHP file named **first.php**.

HTML form elements have **names**, which will be used when accessing the data with PHP.

![imsadas](https://api.sololearn.com/DownloadFile?id=2379)

Now, when we have an HTML form with the **action** attribute set to our PHP file, we can access the posted form data using the **\$\_POST** associative array.

```php+HTML
<html>
<body>

Welcome <?php echo $_POST["name"]; ?><br />
Your age: <?php echo $_POST["age"]; ?>

</body>
</html>
```

The **\$\_POST** superglobal array holds key/value pairs. In the pairs, keys are the **names** of the form controls and values are the **input data** entered by the user.

### SESSIONS

Using a **session**, you can store information in variables, to be used across multiple pages. Information is not stored on the user's computer, as it is with **cookies**. By default, session variables last until the user closes the browser.

A session is started using the **session_start()** function.
Use the PHP global **\$\_SESSION** to set session variables.

```php
<?php
// Start the session
session_start();

$_SESSION['color'] = "red";
$_SESSION['name'] = "John";
?>
```

Now, the **color** and **name** session variables are accessible on multiple pages, throughout the entire session.

> The **session_start()** function must be the very first thing in your document. Before any HTML tags.

**Another page** can be created that can access the session variables we set in the previous page:

```php
<?php
// Start the session
session_start();
?>
<!DOCTYPE html>
<html>
<body>
<?php
echo "Your name is " . $_SESSION['name'];
// Outputs "Your name is John"
?>
</body>
</html>
```

### COOKIES

...

## Working with files

```php
<?php
 $myfile = fopen("names.txt", "w");
 $txt = "John\n";
 fwrite($myfile, $txt);
 $txt = "David\n";
 fwrite($myfile, $txt);
 fclose($myfile);
?>
```

Let's create an example of a form that adds filled-in data to a file:

```php+HTML
<?php
if(isset($_POST['text'])) {
  $name = $_POST['text'];
  $handle = fopen('names.txt', 'a');
  fwrite($handle, $name."\n");
  fclose($handle);
}
?>
<form method="post">
  Name: <input type="text" name="text" />
  <input type="submit" name="submit" />
</form>
```

> We did not specify an **action** attribute for the form, so it will submit to itself.

```php
$read = file('names.txt');
$count = count($read);
$i = 1;
foreach ($read as $line) {
  echo $line;
  if($i < $count) {
    echo ', ';
  }
  $i++;
}
```

## Protection against SQL Injection

Retirar todos os caracteres especiais de uma variável:

```php
$senha = "Um teste de or '1='1;";
$resultado = preg_replace('/[^[:alnum:]_]/', '',$senha);
echo $resultado;
```

Outro método é a utilização do PDO (PHP Data Objects) na camada de abstração da aplicação. O PDO utiliza “prepared statements” na formação de suas queries. O que nada mais é que um template que irá nos ajudar a escrever uma instrução. Como é um "template", a estrutura nos permite saber onde exatamente irão entrar os valores para as nossas queries. Por exemplo:

```php
<?php
$pdo = new PDO('mysql:host=localhost;dbname=crud', 'root', '');
$stmt = $pdo->prepare('select * from agenda where nome = :nome');
$stmt->bindValue(':nome', 'kalil');
$run = $stmt->execute();
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
var_dump($result);
?>
```

> Repare na utilização da função **bindValue**, nela passamos a variável e o valor da mesma para nossa query. Desta forma colocamos cada variável no seu devido lugar e qualquer código anormal que entre irá gerar erro.

### Mais sobre PDO

**PDO**(**PHP** Data Objects) é um módulo de **PHP** montado sob o paradigma Orientado a Objetos e cujo objetivo é prover uma padronização da forma com que **PHP** se comunica com um banco de dados relacional. Este módulo surgiu a partir da versão 5 de **PHP**. **PDO**, portanto, é uma interface que define um conjunto de classes e a assinatura dos métodos de comunicação com uma base de dados.

## PHP Orientado a Objetos

```php
class Produto {
  
   private $codigo;
   private $nome;
   private $preco;
  
   public function getCodigo() {
       return $this->codigo;
   }
   public function setCodigo($codigo) {
       $this->codigo = $codigo;
   }
   public function getNome() {
       return $this->nome;
   }
   public function setNome($nome) {
       $this->nome = $nome;
   }
   public function getPreco() {
       return $this->preco;
   }
   public function setPreco($preco) {
       $this->preco = $preco;
   }
}
```

```php
class Assinatura extends Produto {
     private $dataExpiracao;
     public function getDataExpiracao() {
         return $this->dataExpiracao;
     }
     public function setDataExpiracao($dataExpiracao) {
         $this->dataExpiracao = new \DateTime($dataExpiracao);
     }
     public function getTempoRestante() {
         return $this->dataExpiracao->diff(new \DateTime());
     }
  }
```

## PHP^7 features

Se o primeiro valor for NULO "??" atribuirá o segundo valor

```php
$limit = $request->getQueryParams()['limit'] ?? 10;
//se não foi passado um valor limite, será 10
```

## Consumindo uma API

Referências:

- [YouTube UpInside](https://www.youtube.com/watch?v=YF5eP_rZBlg&feature=em-uploademail&t=75s)
- [CanalTI](https://www.canalti.com.br/programacao/web/php/como-consumir-api-com-php-pokemons-listar-dados-file_get_contents-e-curl/)

### file_get_contents

```php
//Consumindo API no PHP com file_get_contents
<?php
$url = "https://www.canalti.com.br/api/pokemons.json";

$pokemons = json_decode(file_get_contents($url));
?>
```

### cURL

```php
<?php
$url = "https://www.canalti.com.br/api/pokemons.json";

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
$pokemons = json_decode(curl_exec($ch));
?>
```

```php
<?php
class Comunicacao {
  public function enviaConteudoParaAPI($cabecalho = array(), $conteudoAEnviar, $url, $tpRequisicao) {
   try{
    //Inicializa cURL para uma URL.
    $ch = curl_init($url);
    //Marca que vai enviar por POST(1=SIM), caso tpRequisicao seja igual a "POST"
    if ($tpRequisicao == 'POST') {
     curl_setopt($ch, CURLOPT_POST, 1);
     //Passa o conteúdo para o campo de envio por POST
     curl_setopt($ch, CURLOPT_POSTFIELDS, $conteudoAEnviar);
    }
    //Se foi passado como parâmetro, adiciona o cabeçalho à requisição
    if (!empty($cabecalho)) {
     curl_setopt($ch, CURLOPT_HTTPHEADER, $cabecalho);
    }
    //Marca que vai receber string
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    /*
    Caso você não receba retorno da API, pode estar com problema de SSL.
    Remova o comentário da linha abaixo para desabilitar a verificação.
    */
    //curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    //Inicia a conexão
    $resposta = curl_exec($ch);
    //Fecha a conexão
    curl_close($ch);
   }catch(Exception $e){
    return $e->getMessage();
   }
   return $resposta;
  }
}
?>
```
