## Para organizar seu código CSS:

Você tem alguns arquivos:

- reset.css
- format.css
- layout.css

Criar o 

master.css

E nele importar os demais:
```css
@import url("reset.css");
@import url("format.css");
@import url("layout.css");
```
Na página html:
```css
<style type="text/css" media="screen">@import url("master.css")</style>
```
