## Inicialmente devemos definir:

- Título do site
- Domínio e hospedagem com e-mail
- Objetivos com clareza. O que se pretende alcançar com a construção do site
- Sobre a manutenção: adição de artigos, correções e exclusões. Quem fará e como
- O que o site traz para se justificar a criação deste novo site. Que diferenciais
- Que o site contenha uma seção de contato, onde o usuário encontrará endereço, telefone, whatsapp (caso de empresa), e-mail, facebook, instagran, twitter, etc
- Todas as páginas devem conter um link para a home, melhor ainda, todas as páginas devem conter o menu principal e no topo
- Usar ao menos 80% de conteúdo visual (texto e imagens) nas páginas;
- Usar um layout clean
- Que os links abram páginas internas ou, se externas, abram em outra aba e com um ícone indicando isso
- Obrigatoriamente os sites devem ser responsívos e mobile-first
- O site deve carregar em no máximo 3 segundos
- Se possível crie uma página 404 bem bonita e também uma caixa de busca
- Considere ter uma seção de ajuda no site, com conteúdo explicando sobre como navegar e encontrar. Melhor é que nem seja necessário

### Usar

- Tema com tons variando em uma única cor
- Imagens com boa/ótima resolução e exclusivas
- Redimensionar imagens grandes
- Conteúdo exclusivo, de preferência, bem feito e de agradável leitura
- Fontes com tamanho confortável para ler em geral
- Evite mudar as disposições e padrões que os users já estão acostumados, como:
  - menu principal no topo
  - links sublinhados (caso remova o sublinhado encontre uma forma de mostrar que são links)
- A navegação pelo conteúdo do site deve ser simples e intuitiva
- Rodapé alto e dividido em 3 ou 4 partes contendo algo como o mapa do site. Confira aqui:
  https://pagespeed.web.dev/
- Criar o site tendo em mente uma boa UX (experiência dos usuários)
- Após concluir faça uma checagem geral do site, inclusive do código
- Dependendo do site, um chat é importante e também um blog e um forum
- Fique atento para técnicas de SEO
- Lembre de facilitar a vida de quem dá manutenção no site

### Evitar

- Autoplay de áudio ou vídeo
- Cores muito fortes
- Contraste exagerado entre frente e fundo
- Contrastes que escondam a frante (fonte com cor bem perto da cor de fundo)
- Fontes muito pequenas, que dificultem a leitura
- Fontes muito grandes, que as tornem destoantes
- Algo que torna o site pesado:
  - Imagens muito grandes
  - Vídeos
  - Javascript com muito processamento

- Não usar JS na tag head. Prefira  ao final, logo acima da tag </body>
  

[https://lucasferraz.com.br/blog/boas-praticas-para-criacao-de-sites/](https://lucasferraz.com.br/blog/boas-praticas-para-criacao-de-sites/)

Sempre feche as tags

Use sempre a tag DOCTYPE, lang="pt-BR" e as demais abaixo, veja:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
	<meta charset="UTF-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
Evite usar o CSS inline. Sempre crie um arquivo externo e o inclua no HTML:
```html
<link rel="stylesheet" type="text/css" href="style.css">
```
E dentro da tag <head>
```html
<script type="text/javascript" src="script.js"></script>
</body>
```
Também nunca use javascript inline. Prefira em arquivo separado e importando no HTML

Use e abuse a ferramenta Inspector, com seus vários recursos

Escreva os nomes das tags em minúsculas

Use as tags H1 até H6 e a H1 somente uma vez em cada página

Use as tags semânticas do HTML 5 para organizar melhor seu código

Os frameworks, como bootstrap e jquery já vem com uma forte compatibilidade com os principais navegadores, portanto é uma boa ideia adotá-los. Mas é muito importante que os primeiros sites criados sejam sem usa-los, para que realmente aprenda sobre os assuntos

Um bom editor de código, como o VSCode ajuda na criação de sites

Após a conclusão do sites, as checagens e testes, então é uma boa ideia fazer um backup completo e então comprimir o CSS e o Javascript (versões minificadas) Existem alguns serviços online que fazem isso

Use o atributo alt em todas as imagens
<img src="cornImage.jpg" alt="A corn field I visited." />

Participe de bons grupos de discussão sobre os assuntos abordados: HTML, CSS  e JS

### Use resets de CSS

[http://meyerweb.com/eric/tools/css/reset/index.html](http://meyerweb.com/eric/tools/css/reset/index.html)

### Podemos começar com este:
```css
html, body, div, span, 
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
img, ins, kbd, q, s, samp,
small, strike, strong, 
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td {
        margin: 0;
        padding: 0;
        border: 0;
        outline: 0;
        font-size: 100%;
        vertical-align: baseline;
        background: transparent;
}
body {
        line-height: 1;
}
ol, ul {
        list-style: none;
}
blockquote, q {
        quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
        content: '';
        content: none;
}

table {
        border-collapse: collapse;
        border-spacing: 0;
}
```

Não crie páginas sem a tag <head> e seu precioso conteúdo

Use nas imagens
```html
<figure>
	<img src=“a-man-coding.jpg” alt=“A man working on his computer”>
	<figcaption> This is a picture of a man working on his computer</figcaption>
</figure>
```
Não use div para criar header nem footer, mas estas tags: header e footer

Evite usar <b> e <i>, use <strong> e <em>

O Google Analitcs pode ajudar também mostrando o desempenho do site

Dividir as páginas de conteúdo em duas colunas para facilitar a leitura

Ao usar CSS de algum framework, use o minificado mas mantenha o fonte para o caso de querer editar. Evite editar, para isso crie um style.css com seu código que sobrescreverá o do framework e o insira logo abaixo do css do framework no head.


