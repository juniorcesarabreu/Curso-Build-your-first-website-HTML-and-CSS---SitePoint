Para nossos arquivos CSS, nó iremos seguir o princípio SMACSS que quebra os arquivos CSS em:

base.css
layout.css
modules.css
states.css
themes.css

base.css
------------------------------
É usado para todos os estilos básicos -tais como seletores de elementos... h1, blockquote, table etc...

layout.css
-----------------------------
É usado para definir os grids gerais e componentes de layout.

modules.css
-----------------------------
É usado para as partes modulares, reusáveis de nosso design. Eles são os callouts, as seções laterais, listas de produtos, navegação e assim por diante.

normalize.css
------------------------------
É usado para fazer navegadores renderizar todos os elementos mais consistentemente e em linha com os padrões modernos.


HTML5Shiv habilita-nos a estilizar elementos HTML5 em versões de Internet Explorer anteriores a versão 9, que não permite elementos desconhecidos serem estilizados sem JavaScript.

respond.min.js é um Polyfill peso leve que força Internet Explorer 6-8 a suportar Media Queries CSS3 min/max-width.

Media Queries são uma extensão para os tipos de media CSS2. Eles dão-nos muito mais controle sobre como nós entregamos CSS para diferentes dispositivos.

```css
/* CSS @media rule */
@media (min-width: 38em) {

  /* Estas regras deveriam ser aplicadas somente por dispositivos que tenham um viewport mínimo de 38em */
}
