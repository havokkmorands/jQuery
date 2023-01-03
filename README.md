# jQuery
"write less, do more"
- Biblioteca de JavaScript
- Carregamento rápido
- Converte para JS (ECMAScript) padrão 
- Crossbrowser: funciona em diversos navegadores
- Escrever um código para todos os navegadores
- Rápida captura e transmissão de dados 
- Manipula o DOM
- Facilita a consulta (query) a elementos
- Extensível com plugins
- Instalação: https://jquery.com/download/

##Seletores no jQuery

O jQuery para fazer sua biblioteca funcionar, exerce uma função parecida ao CSS, que utiliza de elementos ou atributos no HTML para adicionar suas funções.

Podemos adicionar uma vasta possibilidade de atividades na página, simplificando bem o uso do Javascript. O que poderia se tornar uma grande função de laço de repetição pode ser
reduzido para apenas uma linha. Vejamos no exemplo a seguir:

Temos a página que estará disponibilizada no Github, que contém 9 produtos. Cada produto tem um título, com o elemento <h4>. Podemos alterar, com Javascript, seus títulos!
Com o comando executado via console:

```
let titulos = document.querySelectorAll('h4')
```

Essa variável que estamos criando será usado como base da criação de um laço de repetição For, que será explicado mais abaixo.

```
for (let i = 0; i < titulos.length; i++) {
titulos[i].textContent = "titulo qualquer"
}
```

Esse comando acima, fará várias alterações, pode parecer a nossa vista de uma vez só, mas ele pecorre toda a página, um elemento h4 de cada vez, e fará a substituíção de cada um desses
elementos.

Mas ao invés de ter todo esse trabalho com um código grande, pesando mais a página, podemos reduzir para apenas UMA linha com o jQuery, para isso, basta recarregar a página, e novamente
no console, digitar:

```
jQuery('h4').text('titulo qualquer');
```

Ok! Agora que sabemos como o jQuery funciona na prática, devemos ter cuidado com conflitos!

Como visto nos exemplos acima, podemos ocasionar mudanças onde não desejamos. E se fosse apenas necessária a mudança no primeiro título?

Para isso, podemos evitar os conflitos com a separação correta dos seletores. Como dito anteriormente, os seletores do jQuery são bem similares ao do CSS, podemos ver abaixo:

###Seletores Simples
Seletores que podemos alterar apenas um específico elemento ou atributo: 

```
jQuery (function($){

  $('h4') //Seletor para elemento
  $('.featured-item') //Seletor para Class
  $('#featured') //Seletor para ID
}
```


###Seletores compostos 
Aqui podemos fazer alteração em mais de um elemento ou atributo, dependendo também da hierarquia que você deseja alterar:

```
$('h4, h6') //alterará elementos h4 e h6
$('div h4') //Alterará apenas elementos nessa hierarquia, ou seja, títulos h4 dentro de uma div.
```


Com uma simples linha, podemos fazer essa alteração em todo o código! É claro que o jQuery não se limita a apenas isso. Vejamos outros exemplos, dessa vez, algo que pode ser
melhor utilizado:

Temos uma lista de atividades a serem realizadas, onde caso a gente tenha terminado algum item da lista, basta clicar no item que desejamos marcar como feito, e pronto!
Código fonte (html e jQuery), também disponível no material do exercício:


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista</title>
    <style type="text/css">
        div {
          width: 200px;
          height:  100px;
          border: 1px solid #000;
          margin: 20px;
        }
      </style>
</head>
<body>
    <h1>Lista de Tarefas!</h1>
    <p>Arrumar as roupas.</p>
    <p>Ir para o supermercado.</p>
    <p>Enviar o exercício para EBAC.</p>
</body>
<script src="https://code.jquery.com/jquery-3.6.1.min.js"></script>
<script type="text/javascript">
    $(document).ready(function() {
      $('p').click(function(){
        $(this).css('background', 'red');
        });
      });
</script>
</html>
```
###Código (Apenas jQuery):

```
    $(document).ready(function() {
      $('p').click(function(){
        $(this).css('background', 'red');
        });
      });
```
Nesse código, já começamos a ter a ideia de jQuery na página em si. Quando atribuído $(document).ready, significa que assim que a página estiver pronta e preparada, será carregada
a função abaixo. A função trata-se de, ao clicar em um parágrafo, será acrescido ao seu CSS um fundo de cor vermelho. Para evitar que seja marcado todos os elementos que estão
presentes com o elemento p, utiliza-se o this.

This refere-se ao elemento próprio em que foi chamado, ou seja, aquele que começou a função do click, o que foi clicado primeiro. Ele fará apenas para aquele, e não fará em todos.

