# Markdown, oq é? 

>Markdown Syntax é uma sintaxe usada para padronizar e facilitar formatação de texto na web, utilizada em aplicativos como Slack e GitHub. Textos estilizados com Markdown são, na maioria dos casos, apenas texto com caracteres não-alfabéticos, como #, \* e ![](), usados para a configuração de títulos, listas, itálico, negrito e inserção de imagens.

# Comandos

### Usamos o "#" para títulos

 >  * "#"  = Do Maior 
 >  * "##" 
 >  * "###" 
 >  * "####"  
 >  * "#####" 
 >  * "######" = Ao Menor

### Ênfase
 
 * **Negrito**: adicione dois asteriscos `**texto**` ou dois traços-baixos `__texto__ `no início e no fim do conteúdo.

 * **Itálico**: adicione apenas um asterisco `*texto*` ou um traço-baixo `_texto_` no início e no fim do conteúdo.

 ### Links

 Texto-âncora: utilize os caracteres `[]()`, adicionando entre chaves o texto que você quer que apareça, e entre os parênteses, o endereço de destino, no formato `[exemplo]``(https://exemplo.com/)`.

Link direto: envolva o endereço da web em chaves `<>`. O endereço ficará visível e será clicável pelo usuário. O endereço em forma de link direto tem o formato `<https://exemplo.com/>`.

Exemplo:

[Link Em Formato de Texto](https://github.com/051Guilherme)                            
Link Direto: <https://github.com/051Guilherme>

### Lista

Para listas não ordenadas, utilize um asterisco `*` na frente to item da lista.         
Para listas ordenadas, `utilize o número do item seguido de ponto .`

### Imagens

O código para inserir uma imagem no conteúdo é semelhante ao código de inserir links-âncora, adicionando um ponto de exclamação ! no início do código.

> `![Alt ou título da imagem](URL da imagem)`

![CS](https://developer.valvesoftware.com/w/images/0/05/Counter-Strike_-_Background.jpg)

### Citação 
Para transformar um texto em uma citação ou comentário, semelhante ao código HTML `<blockquote>`, utilize o sinal > no início da linha que será formatada

~~~~
>Este é um *blockquote*. O sinal usado abre e fecha este código no HTML              
>Para adicionar mais uma linha à citação, basta teclar Enter para um novo            
>código sinal. Isso gerará um novo parágrafo dentro do `*blockquote*`.               
>Códigos de `**negrito**`, `_itálico_` e `<https://links.com>` funcionam aqui.
~~~~

#### Fica Assim:

>Este é um *blockquote*. O sinal usado abre e fecha este código no HTML              
>Para adicionar mais uma linha à citação, basta teclar Enter para um novo            
>código sinal. Isso gerará um novo parágrafo dentro do `*blockquote*`.               
>Códigos de `**negrito**`, `_itálico_` e `<https://links.com>` funcionam aqui.

### Código

* Código em linha (inline): adicione um acento grave ˋ no início e no final do código.
* Múltiplas linhas de código: envolva as linhas de código com três acentos graves ˋˋˋ ou três tils ~~~.

### Tabela

Escolha os títulos das colunas e use | para delimitar as colunas. Depois, utilize hífen - na segunda linha para indicar que acima estão os títulos das colunas, usando novamente o | para delimitar colunas.

~~~
Exemplo   | Valor do exemplo
--------- | ------
Exemplo 1 | R$ 10
Exemplo 2 | R$ 8
Exemplo 3 | R$ 7
Exemplo 4 | R$ 8
~~~
#### Fica Assim:
Exemplo   | Valor do exemplo
--------- | ------
Exemplo 1 | R$ 10
Exemplo 2 | R$ 8
Exemplo 3 | R$ 7
Exemplo 4 | R$ 8

Para especificar o tipo de alinhamento que deseja ter nas tabelas, utilize : ao lado do campo horizontal de hífens ---, na segunda linha da sua tabela.

* Alinhado a esquerda: usar : no lado esquerdo (alinhamento padrão);
* Alinhado a direita: usar : no lado direito;
* Centralizado: usar : dos dois lados.

### Cores
~~~
<span style="color:red">
Texto Colorido
</span>
~~~

<span style="color:red">
Texto Colorido
</span>

### Fonte
~~~
<span style="font-size:18px">
Este texto é maior que o normal.
</span>
~~~

<span style="font-size:18px">
Este texto é maior que o normal.
</span>