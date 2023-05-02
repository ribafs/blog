## Tornar sites responsivos

Para que se adaptem adequadamente a qualquer dispositivo que os acessem.

As media queries são um recurso muito importante para isso.

### Para pequenos dispositivos:

- Coluna única
- Menu hamburger

Aqui, vamos definir uma classe que só será carregada quando a largura de tela do dispositivo for de 900 pixels ou meno4. E, ainda, vai alterar a largura da classe ".menu" para 100% do tamanho da tela do navegador. 

Um media query que permite fazer isso deve se parecer com este código abaixo:
```css
@media only screen and (max-device-width: 900px) {
/* .menu { width:100%; } */
}
```
Alguns elementos da página não mudam ao serem acessados por dispositivos diferentes:

- background-color
- color
- ...

Algumas propriedades quase sempre mudam:

- height
- width
- margin
- padding
- ...

Uma boa alternativa de medida é a % (em imagens usemos somente na width) mas existem outras.

Também é possível configurar larguras fixas para larguras particulares de tela. Por exemplo, configurar a largura de menu para 600 pixels se a to tamanho da tela do dispositivo for de 900 pixels. Veja abaixo códigos que você pode usar para aplicar essas mudanças. 

Exemplos
    • Se o tamanho da tela for 900 pixels ou menor, é possível configurar uma classe de largura de menus para 600 pixels usando: 
```css
@media only screen and (max-device-width: 900px) {
/* .menu { width:600px; } */
}
```
    • Se o tamanho da tela for 700 pixels ou menor, é possível configurar uma classe de largura de menus para 400 pixels usando: 
```css
@media only screen and (max-device-width: 700px) {
/* .menu { width:400px; } */
}
```
O tráfego de dispositivos móveis na web ultrapassou os 51% tornando-se assim muito importante que a página se adapte a ele, caso contrário perderemos visitação.

Dicas:
```css
img{
    width: 80%;
}

.img-full{
    width: 100%;
}

@media screen and (min-width: 780px) {
.full-width-img {
margin: auto;
width: 90%;
}
```
Importante usar srcset

Para servir diferentes versões escalonadas para diferentes dispositivos, você precisa usar o atributo HTML srcset em suas tags img, para especificar mais de um tamanho de imagem para escolher.
```css
<img srcset="large-img.jpg 1024w,
middle-img.jpg 640w,
small-img.jpg  320w"
src="small.jpg"
/>
```
### Tamanhos de tela comuns

    • Móvel: 360 x 640 
    • Móvel: 375 x 667 
    • Móvel: 360 x 720 
    • iPhone X: 375 x 812 
    • Pixel 2: 411 x 731 
    • Tabuleiro: 768 x 1024 
    • Portátil: 1366 x 768 
    • Laptop ou desktop de alta resolução: 1920 x 1080 


### Available breakpoints

Bootstrap includes six default breakpoints, sometimes referred to as grid tiers, for building responsively. These breakpoints can be customized if you’re using our source Sass files.
```css
Breakpoint 	Class infix 	Dimensions
X-Small 	None 	        <576px
Small 	    sm 	            ≥576px
Medium 	    md 	            ≥768px
Large 	    lg 	            ≥992px
Extra large	xl 	            ≥1200px
Extra extra large 	xxl 	≥1400px
```css
[https://getbootstrap.com/docs/5.0/layout/breakpoints/](https://getbootstrap.com/docs/5.0/layout/breakpoints/)

Principais
```css
Small 	    sm 	            ≥576px
Medium 	    md 	            ≥768px
Large 	    lg 	            ≥992px
Extra large	xl 	            ≥1200px

PX vs EM vs REM vs Viewport Units para projeto responsivo
    • PX – um único pixel 
    • EM – unidade relativa com base no tamanho da fonte do elemento. 
    • REM – unidade relativa com base no tamanho da fonte do elemento. 
    • VH, VW – % da altura ou largura do viewport. 
    • % – a porcentagem do elemento pai. 
```
### Unidades relativas do CSS

    • %
    • em
    • rem
    • vw
    • vh

Podemos dizer que se a largura da tela for maior que 768 px use um estilo diferente
```css
@media (max-width: 768px) {
    .myImage {
        width: 100%
    }
}
```
O 768px é um breakpoint, menor ou igual use o media querie, maior não use.

### Flexbox

O display: flex transforma o <nav> em uma caixa flexível, e o justify-content: space-around informa ao navegador que os itens dentro da caixa flexível devem ter espaço ao redor deles. Assim, o navegador distribui todo o espaço restante igualmente entre os três itens.
```css
nav {
    display: flex;
    justify-content: space-around;
}
```
### Tipografia responsiva
```css
@media (max-width: 768px) {
    nav {
        font-size: 14px;
    }
    h1 {
        font-size: 28px;
    }
}

h1 {
    font-size: 2rem;
}

nav {
    font-size: 1rem;
}

@media (max-width: 768px) {
    html {
        font-size: 14px
    }
}
```


