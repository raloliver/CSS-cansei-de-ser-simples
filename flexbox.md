# FLEXBOX

Normalmente usariámos:

`display: inline-block;
vertical-align: middle; margin-left: 830px; float: right;`

E para enviar o elemento totalmente para a esquerda, usaríamos um "número mágico", no exemplo 830px ou se for usar % (100%) também não é correto e o elemento sai do container.

Da pra usar o float também, mas o conteúdo abaixo acaba subindo.

## COMO USAR O FLEXBOX

1. Quem são os elementos que eu quero alinhar? 
1. E quem é o pai desses elementos?

`.pai { display: flex; align-items: center; justify-content: space-between;}`

Ao usar space-between, movemos o espaço vazio entre os elementos.

**Detalhe: ao inserir um `display: flex` no elemento pai, a altura dos elementos filhos também são unificadas.**

Diferente do space-between, temos o space-arround, que coloca o espaço em volta dos elementos.

> Existem também a propriedade `flex-direction` que determina a direção dos elementos. Por padrão é utilizado o valor `row` que dispõe os elementos em linha, e o valor `column` que distribue os elementos em colunas.

`flex-wrap: wrap` quebra o elemento para a próxima coluna (_lembre-se de determinar uma altura para o elemento_).

>**Para unir as duas propriedades citadas anteriormente, utilize o atributo `flex-flow: column wrap`.**

Existe um gargalo caso utilize numa listagem o `justify-content`, os itens do final vão sempre ficar desalinhados, já que o flexbox foi criado para layouts unidimensionais, para outros mais complexos (bidimensionais) existe o grid layout `display: grid`.

Para resolver isso, utilize apenas a propriedade margin, utilizando a pseudo-classe `nth-child(4n)`.

>**Que fique claro a diferença entre as propriedades do 'flex container' e do 'flex items'**.

O `flex-grow` é um propriedade do 'flex items' que incorpora o espaço branco no elemento escolhido, exemplo: `flex-grow: 1`. Essa propriedade coleta o espaço em branco dos itens e adiciona ao elemento seleciona, caso existam dois, três, etc... ele vai diminuir pela soma dos valores.

O `flex-shrink` faz o efeito contrário do `flex-grow` ele diminui o tamanho, ou se seja, é invesamente proporcional ao `flex-grow`.

> A propriedade display: flex pode ser usada nos dois. Se for usada em um flex item esse elemento será tanto um flex item quanto um flex container.

## RESPONSIVIDADE

Ao atribuir o valor flex para a propriedade display, todo o elemento se transforma num 'flex container' e os itens internos são os 'flex items' que se dividem em eixo horizontal/principal (`justify-content`) e eixo vertical/cruzado (`align-items`). ATENÇÃO: ao mudar a direção (`flex-direction`) os eixos mudam.

Para inverter a ordem, você pode usar `order: -1` esse propriedade se refere aos 'flex items' apenas.

## DICAS EXTRAS

- `flex-grow`: a divisão é sempre feita com base no espaço vazio que sobre dentro do elemento. O valor padrão dessa propriedade é 0.
- `flex-shrink`: o valor padrão é 1, sempre que aumentamos, o elemento diminue a quantidade inserir. Tudo isso com base na largura do elemento.
- `flex`: define o grow e o shrink, exemplo `flex: 1 1 40%`. O primeiro é o grow, o segundo o shrink o terceiro é o basis.
- `flex-basis`: define a largura padrão para determinado flex item.

### Referências:
1. [Acelerando o tempo com CSS Grid Layout e senna.js](https://goo.gl/yTu3s5)
1. [Usando CSS flexible boxes (Caixas Flexíveis)](https://goo.gl/m33OSB)
1. [A Complete Guide to Flexbox](https://goo.gl/WySM2z)