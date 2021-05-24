# Abelhas 🐝 e suas Castas 🍯
Uma página sobre abelhas e suas castas.

![Resultado final da prática das abelhas](https://raw.githubusercontent.com/fegemo/cefet-web/master/images/pratica-abelhas.png)


## Atividade

Crie um pequeno website com 4 páginas informativas sobre as abelhas e suas
castas. Dos 4 arquivos HTML que formam o website das abelhas, 3 já estão
prontinhos e o 4º será criado por você. Além disso, você deve personalizar a
aparência das páginas usando CSS. Procure evitar alterar o HTML da
página, para exercitar os conhecimentos dos seletores CSS 
(a menos que o exercício diga o contrário).

Ao fazer este exercício, fique conferindo, no navegador, como a página
está ficando. Se quiser **parar a música**, veja como fazê-lo no [FAQ](#faq).


### Exercício 0: Estilização inicial

1. Crie um arquivo `estilos.css` na pasta raiz do site e o inclua na
   página `index.html`
   - Lembre-se que, neste arquivo, apenas código CSS é permitido
     - Ou seja, **não é necessário (nem pode)** usar _tags_, como
       **`<style>...</style>`**
   - Ele deve ser incluído dentro do `<head>...</head>`, preferencialmente
     depois do `<title></title>`
1. Configure **o corpo da página**
   - Coloque um fundo em gradiente (escolha as cores)
     - Lembre-se que um gradiente não é o valor para um `background-color`,
       mas para `background-image` (slides sobre [gradientes][gradientes])
     - Escolha as cores e a direção do gradiente de forma a deixar a
       **página bonita**, **sem atrapalhar sua legibilidade**
   - Aumente o tamanho da fonte para algo como `24px`
   - Coloque uma margem lateral diferente de 0
   - Remova a margem vertical (ie, defina como 0)
     - Isso é necessário porque, por padrão, o `body` tem `margin: 8px`
   - Faça com que a página ocupe toda a altura disponível (para evitar que o fundo não ocupe todo o espaço)
1. Alinhe o texto de todos os parágrafos de forma justificada (`justify`)
1. Centralize a logomarca (a primeira imagem, lá no alto)
   - É um bom caso para criar um `id` (use nome descritivo, em minúsculas e substituindo espaços por tracinhos)
     - Para lembrar como estilizar um único elemento, veja a explicação sobre
         [seletor de _tag_ _vs_ seletor de `id`][id-selector]
     - E também relembre como [centralizar imagens][centering-imgs]

Até este ponto, a página inicial deve estar mais ou menos assim:

![Resultado parcial da prática das abelhas após o exercício 2](https://raw.githubusercontent.com/fegemo/cefet-front-end/master/images/pratica-abelhas-passo-1.png)


### Exercício 1: Estilizando as **"curiosidades"**

A página `index.html` possui dois parágrafos com a classe `curiosidade`.
Vamos usar isso para poder estiliza-los de forma diferente dos outros
parágrafos.

Queremos deixá-los assim:

![Estilização dos parágrafos de curiosidades](https://raw.githubusercontent.com/fegemo/cefet-front-end/master/images/pratica-abelhas-curiosidades.png)


1. Configure a imagem de fundo dos favos de mel (ie, `favos-de-mel.png` dentro de `imgs/`)
1. Coloque uma borda de `1px`, sólida, com a cor dos contornos dos favos de mel
   - Como descobrir uma cor? Veja no [FAQ](#faq)
1. Deixe a borda arredondada
   - A propriedade para deixar a borda arredondada é `border-radius` e
     ela recebe 1 tamanho, que pode ser expresso como `5px` (por exemplo)
1. Coloque um espaçamento interno (`padding`) para que o texto não
   fique grudado na borda


Além do parágrafo, há uma imagem de interrogação dentro do parágrafo. Repare
que essa imagem aparece duas vezes na página `index.html` e também
aparece nos outros arquivos, mas ela não possui uma classe que nos
permita estilizar dessa forma. Contudo, é possível usar um seletor
de descendente (ou de filho direto) para estilizá-la. Sendo assim,
estilize "imagens dentro de .curiosidade" de forma que elas:

1. Flutuem à esquerda
1. Tenham um espaçamento externo (_i.e._, margem) à direita para que o
   texto não fique grudado nelas


### Exercício 2: As páginas `operarias.html` e `zangoes.html`

Agora vamos aproveitar que escrevemos o código CSS em um arquivo separado
e vamos simplesmente incluí-lo nas páginas `operarias.html` e `zangoes.html`.

Essas duas páginas possuem uma imagem de uma casta de abelha logo antes
do primeiro parágrafo. Vamos estilizar as duas de forma que elas fiquem
arredondadas e com uma bordinha bacana:

![Estilização das imagens das castas](https://raw.githubusercontent.com/fegemo/cefet-front-end/master/images/pratica-abelhas-castas.png)

- Veja se **as duas imagens possuem uma classe** que podemos usar para
  estilizar ambas (`<img src="..." class="???">`). Então, crie uma regra e:
  1. Arredonde as bordas mas, em vez de colocar um valor em pixels,
     coloque `50%`
     - Isto fará com que a imagem fique circular 😉
  1. Coloque uma bordinha marota. Eu usei `3px double goldenrod`

Agora, vamos colocar a imagem flutuando, para que o texto fique ao redor
dela. Queremos que, na página das `operarias.html`, a imagem flutue à
esquerda e, na página dos `zangoes.html`, ela flutue à direita. Além da
flutuação, coloque também uma margem à direita ou à esquerda (depende do
caso) para que o texto não fique grudado na imagem:

![Estilização das imagens das castas na página das operárias](https://raw.githubusercontent.com/fegemo/cefet-front-end/master/images/pratica-abelhas-operarias.png)
![Estilização das imagens das castas na página dos zangões](https://raw.githubusercontent.com/fegemo/cefet-front-end/master/images/pratica-abelhas-zangoes.png)


**Dica**: você pode (a) criar um `id` para cada uma das duas imagens, ou
então (b - melhor) colocar uma segunda classe em cada imagem (_e.g._,
`<img src="..." class="casta-de-abelha esquerda">` e
`<img src="..." class="casta-de-abelha direita">`) e estilizar usando
essas novas classes, _e.g._:

```css
.esquerda {
  float: left;
  margin-right: 10px;
}
```


### Exercício 3: Topo da página principal

Vamos estilizar a parte superior da página inicial dando a ideia de um 
"cabeçalho" da página. Para isso, altere `index.html` para colocar
a `<img src="imgs/logomarca.png">` dentro de algum elemento **que vimos recentemente**
e que é usado para agrupar outros elementos e/ou estilização apenas 
(não possui semântica). Deve ser um elemento **block**.
Dê um `id` pra ele e estilize-o com:
- Cor de fundo: branco bem transparente (slides sobre [cores transparentes][cores-transparentes])
- Sombra de leve: `box-shadow: 4px 4px 4px #0003`
- Largura: `500px`
- Espaçamento interno: `30px`


### Exercício 4: Outras estilizações

Usando o que foi visto sobre diversos seletores CSS, estilize:

1. Os _hyperlinks_ em seus **4 estados diferentes**:
   - Sugestão: variar as propriedades `color` e/ou `text-decoration: underline` (sublinhado) e `text-decoration: none` (sem sublinhado)
   - Obs: apenas um subconjunto das propriedades CSS pode ser usado ao estilizar hyperlinks em seus 4 estados. Veja o [motivo][motivo-da-restricao-de-estilizacao-de-hyperlinks].
1. **Links externos**
   - Coloque uma cor de fundo nos _hyperlinks_ que apontam para URLs externas
     - _Dica_: o que define um _hyperlink_ para uma URL externa? É um elemento
       `<a ...>...</a>` que aponta (atributo `href`) para um endereço
       que começa com `http`
       - Volte nos slides sobre seletores e veja que existem os
         [**seletores de atributos**][seletores-atributos], que se encaixam
         direitinho neste caso
1. **Último parágrafo** alinhado à direita
   - Crie uma regra CSS para que o último parágrafo da página seja 
     sempre alinhado à direita
     - Há um ou dois seletores bem específicos pra "último elemento" 
       ou "último filho"
     - Lembre-se de [como alinhar texto][alinhamento-de-texto] de um parágrafo
1. **Imagens sem atributo `alt`** (desafiozinho)
   - Crie uma regra para mostrar se alguma imagem da página está
     sem o atributo `alt`
     - Naquelas que se enquadrarem, coloque uma borda vermelha
     - A ideia é fazer isso pra ajudar a detectar imagens sem `alt`
     - Você vai querer usar o [seletor de negação][seletor-negacao] para isso
   - Depois, você mesmo deve escrever um atributo `alt` bem descritivo para 
     a imagem encontrada


### Exercício 5: Criando a página `rainha.html`

Crie a página que está faltando, `rainha.html`, contendo:

- Título de primeiro nível `Rainha`
- Imagem `imgs/rainha.png`
- 1 parágrafo:
  - A função da rainha é pôr ovos e manter a ordem social na colmeia. A rainha
    adulta possui quase o dobro do tamanho de uma operária e é a única
    fêmea fértil da colmeia, apresentando o aparelho reprodutor bem
    desenvolvido.
- 1 curiosidade:
  - **Você sabia??** Se nascem duas rainhas ao mesmo tempo, elas
    lutam até que uma morra.
- 1 parágrafo:
  - A vida reprodutiva da rainha inicia-se com o voo nupcial
    para sua fecundação que ocorre, aproximadamente, 5 a 7 dias depois
    de seu nascimento. A fecundação ocorre com a congregação com
    Zangões. Aí existem de centenas a milhares de zangões voando à espera
    de uma rainha, conferindo assim uma grande variedade genética
    no acasalamento.
- 1 curiosidade:
  - **Você sabia??** A abelha rainha vive até dois anos,
    enquanto as operárias não duram mais que um mês e meio.
- Parágrafo com _link_ para voltar


A imagem da abelha rainha deve flutuar à esquerda, assim como a imagem
das operárias.

**Observação**: dependendo da largura da janela, pode acontecer de `p.curiosidade`
ficar com o fundo atrás da imagem da rainha (por ela estar flutuando).

Para garantir que isso não aconteça, estilize essa "curiosidade" 
(pode dar um `id` a ela) para "cancelar a flutuação" que esteja ocorrendo.
Lembre-se de como [cancelar a flutuação][cancelando-a-flutuacao] nos slides.


### Exercício 6: Incluindo `abelhinhas.js`

Descubra como fazer incluir um arquivo JavaScript e 
inclua o `abelhinha.js` na página. Alunos curiosos 
podem querer apertar <kbd>+</kbd>/<kbd>-</kbd> para fazer algo acontecer.



## FAQ

FAQ é uma sigla para _Frequently Asked Questions_ que, em Português, traduz
em **Perguntas Feitas com Frequência**. A seguir, veja algumas questões que
podem surgir ao fazer este exercício, bem como as suas respostas.


### Como faço para parar a música????

Na página `index.html` há um elemento `<audio></audio>` dentro do corpo. Você
pode remover o atributo `autoplay`, ou então colocar um novo atributo
`controls`.

No primeiro caso (atributo `autoplay`), a música continuará lá, mas não
iniciará automaticamente. No segundo caso (atributo `controls`), sugirão
controles para parar/pausar/iniciar a música dentro da página. Faça o teste!


### Como descobrir uma cor?

Você pode usar um editor de imagens como Paint.NET, Pinta, Gimp, Photoshop. Ou então, você pode abrir as **"ferramentas do desenvolvedor"** do navegador (_e.g._, Chrome, Firefox) e escolher uma cor por lá.

Veja como isso [pode ser feito][escolhendo-cores]. Clique no ícone de
conta-gotas para poder selecionar a cor em um certo pixel.


### Estados dos _hyperlinks_

_Hyperlinks_ podem ser estilizados de maneira diferente em diferentes
  situações (quem chamamos de "estados"). Veja
  [explicação nos slides][seletor-estado]. Para tal, existem os seletores
  de estado, que são os seguintes:

- `a:link` - um link que nunca foi visitado. Exemplo:
   ```css
   a:link {
      color: black;
   }
   ```
- `a:visited` - um link que o usuário já visitou. Exemplo:
   ```css
   a:visited {
      color: orange;
   }
   ```
- `a:hover` - um link quando o mouse está em cima dele. Exemplo:
   ```css
   a:hover {
      color: silver;
   }
   ```
- `a:active` - um link no exato momento em que é "clicado". Exemplo:
   ```css
   a:active {
      color: yellow;
   }
   ```

[gradientes]: https://fegemo.github.io/cefet-web/classes/css1/#gradientes
[id-selector]: https://fegemo.github.io/cefet-web/classes/html2/#seletores-css
[centering-imgs]: https://fegemo.github.io/cefet-web/classes/html2/#centralizando-imagens
[seletor-estado]: https://fegemo.github.io/cefet-web/classes/css1/#desafio-seletor-estado
[seletores-atributos]: https://fegemo.github.io/cefet-web/classes/css1/#desafio-seletor-atributo
[alinhamento-de-texto]: https://fegemo.github.io/cefet-web/classes/html1/#entendendo-estilo-alinhamento-do-texto
[cancelando-a-flutuacao]: https://fegemo.github.io/cefet-web/classes/css1/#problemas-com-flutuacao
[escolhendo-cores]: https://fegemo.github.io/cefet-front-end/classes/css1/#escolhendo-cores
[cores-transparentes]: http://fegemo.github.io/cefet-web/classes/css1/#cores-e-gradientes
[motivo-da-restricao-de-estilizacao-de-hyperlinks]: https://hacks.mozilla.org/2010/03/privacy-related-changes-coming-to-css-vistited/