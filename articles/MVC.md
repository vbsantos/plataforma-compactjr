# Model-View-Controller

Tradicionalmente usado para [interfaces gráficas de usuário](https://pt.wikipedia.org/wiki/Interface_gráfica_do_usuário) (GUIs), esta arquitetura tornou-se popular para projetar [aplicações web](https://pt.wikipedia.org/wiki/Aplicações_web) e até mesmo para aplicações móveis, para desktop e para outros clientes.[[6\]](https://pt.wikipedia.org/wiki/MVC#cite_note-6) Linguagens de programação populares como [Java](<https://pt.wikipedia.org/wiki/Java_(linguagem_de_programação)>), [C#](https://pt.wikipedia.org/wiki/C), [Ruby](https://pt.wikipedia.org/wiki/Ruby), [PHP](https://pt.wikipedia.org/wiki/PHP) e outras possuem frameworks MVC populares que são atualmente usados no desenvolvimentos de aplicações web.

![1571690076648](/home/armitage/.config/Typora/typora-user-images/1571690076648.png)

## Model

Sempre que você pensar em manipulação de dados, pense em model. Ele é **responsável** pela **leitura** e **escrita** de **dados,** e também de suas **validações**.

## View

Simples: a camada de interação com o usuário. Ela apenas faz a **exibição** dos **dados**, sendo ela por meio de um **html** ou **xml**.

## Controller

O responsável por **receber** todas as **requisições** do **usuário**. Seus métodos chamados actions são responsáveis por uma página, controlando qual model usar e qual view será mostrado ao usuário.

<img src="https://raw.githubusercontent.com/diegoeis/tableless-static-images/master/2015/02/laravel-introducao.jpg" alt="img" style="zoom: 67%;" />

## Vantagens

1. Como o modelo MVC gerencia múltiplos views usando o mesmo modelo é fácil manter, testar e atualizar sistemas compostos;
2. É muito simples adicionar novos clientes apenas incluindo seus views e controles;
3. Torna a aplicação escalável;
4. É possível ter desenvolvimento em paralelo para o modelo, visualizador e controle pois são independentes;
5. Facilita o reuso do código;
6. Melhor nível de sustentabilidade, pois facilita a manutenção da aplicação;
7. Melhor performance, graças a separação em camadas;
8. Fácil transformação da interface, sem que haja necessidade de modificar a camada de negócio;
9. Melhor desempenho e produtividade, graças a estrutura de pacotes modulares;
10. A arquitetura modular permite aos desenvolvedores e designers desenvolverem em paralelo;
11. Partes da aplicação podem ser alteradas sem a necessidade de alterar outras.

## Desvantagens

1. Necessita de um tempo maior para explorar e modelar o sistema;
2. Requer mão-de-obra especializada;
3. À medida que o tamanho e a complexidade do projeto crescem, a quantidade de arquivos e pastas continuará aumentando também. Os interesses de UI (interface do usuário) (modelos, exibições, controladores) se localizam em várias pastas, que não são formadas em grupos por ordem alfabética.

## O diálogo das camadas

**View**: Fala Controller ! O usuário acabou de pedir para acessar o Facebook ! Pega os dados de login dele ai. **Controller**: Blz. Já te mando a resposta. Ai model, meu parceiro, toma esses dados de login e verifica se ele loga. **Model**: Os dados são válidos. Mandando a resposta de login. **Controller**: Blz. View, o usuário informou os dados corretos. Vou mandar pra vc os dados dele e você carrega a página de perfil. **View**: Vlw. Mostrando ao usuário…

## Referência

[Wikipédia](https://pt.wikipedia.org/wiki/MVC)
