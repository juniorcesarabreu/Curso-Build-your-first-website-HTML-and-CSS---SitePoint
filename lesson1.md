BEM - block, element, module

BEM - Technology for creating web applications
http://bem.info/

About HTML semantics and front-end architecture
http://nicolasgallagher.com/about-html-semantics-front-end-architecture/

MindBEMding – getting your head ’round BEM syntax
http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/

convenção de nomes de classes classes

Princípios
---------------------------------

+ Consistente
  Há uma metodologia comum?
+ Confiável
  Ao que ele relaciona?
+ Reconhecível
  Qual o propósito da classe?

Modules
-------------------------------

A classe primária para qualquer padrão é chamado um "module"

É recomendável evitar CamelCase para facilitar a leitura. Múltiplas palavras são unidas com um único hífen.

```css
/* Module */
.module-name { }
```

Module modifiers
---------------------------------

Se um module precisa ser modificado ou extendido, um "module modifier" deveria ser usado.

Como estamos usando um único hífens para nossos nomes de classes de module, nós diferenciaremos nossos nomes de classes modifiers ao usar dois hífens

```css
/* Module */
.module-name { }

/* Module modifier */
.module-name--modifier-name { }
```

Module descendant
-----------------------------------

Se um module tem elementos filhos que precisem ser estilizados, um "module descendant" poderia ser usado. Nós poderíamos usar dois underscore para mostrar que isto é uma classe descendente.

```css
/* Module */
.module-name { }

/* Module modifier */
.module-name--modifier-name { }

/* Module descendant */
.module-name__descendant-name { }
```

Porque usar nomes de classes para elementos descendentes quando nós poderíamos usar seletores descendentes?

```css
/* Selector descendant */
.module-name h3 { }
```

Se nós usarmos seletores descendentes, nós estaremos confiando que o HTML permanecerá o mesmo - o que pode não ser o caso. Usar nomes de classes dá-nos maior estabilidade e flexibilidade.

Jonathan Snook chama isto de desacoplar o HTML e o CSS. https://www.smashingmagazine.com/2012/04/decoupling-html-from-css/

Esta convenção de nomes básica pode ser extendida para modificadores descendentes também. embora estes tipos de nome de classes deveria raramente ser necessário.

```css
/* Module */
.module-name { }

/* Module modifier */
.module-name--modifier-name { }

/* Module descendant */
.module-name__descendant-name { }

/* Module descendant modifier */
.module-name__descendant-name--modifier-name { }
```

Você poderia também criar nomes de classes que são "descendentes de descendentes", porém isto torna muito coplexo e confuso.

```html
<!-- HTML markup -->
<div class="callout-box__content">
  <h3 class="callout-box__content__heading"></h3>
</div>
```

Para módulos realmente complexos, pode ser mais fácil quebrá-los dentro de módulos menores, de modo que as convenções de nome podem permanecer simples.

Podemos quebrar a regra e usar seletores em alguns lugares.

Nomes de classes sen seletores descendentes é mais eficiente para navegadores, e mais fácil para fazer manutenção.

```html
<!-- HTML markup -->
<div class="callout-box">
  <h3 class="callout-box__heading"></h3>
  <h3 class="callout-box__content"></h3>
</div>
<div class="callout-box callout-box--help">
  <h3 class="callout-box__heading"></h3>
  <h3 class="callout-box__content"></h3>
</div>
```

```css
/* Module */
.callout-box { }

/* Module modifier */
.callout-box--help { }

/* Module descendant */
.callout-box__heading { }
.callout-box__content { }
```
