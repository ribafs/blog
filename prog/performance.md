## Performance

Minimizar as requisições HTTP

80% do tempo gasto pelo usuário no site é no front-end. A maior parte deste tempo é gasto baixando os componentes da página: imagens, CSS, scripts, etc. Reduzindo os componentes reduzirá as requisições HTTP necessárias para renderizar a página.

### Esta é a chave das páginas rápidas.

- Combine arquivos reduzirá as requisições HTTP
  - Juntar todos os arquivos CSS em um único 
  - Juntar os scripts Javascript

- Minificar CSS e jS

- Usar sprites de imagens com CSS

- Mapas de images. Combine algumas imagens em uma única

40 a 60% dos usuários que chegam aos sites estão com caches vazios

CDN (content delivery network) - podem tornar mais rápido o site, pois são servidores bem rápidos e com arquivos otimizados.

Adicione um Expires ou um Cache-Control ao Header

### Caso use Apache, então use:
```php
ExpiresDefault "access plus 10 years"
Accept-Encoding: gzip, deflate
Content-Encoding: gzip
```
Usando gzip reduz em 70% o tamanho da resposta

Deixe o CSS na tag head/topo

Deixe o javascript ao final, logo acima da tag </body>

Evite expressões CSS

Não use CSS nem JS no HTML, mas em arquivos externos

Evite redirecionamentos

Remova scritps e outros arquivos dupliciados

Evite scripts pesados de preload

Reduza o número de elementos DOM

Evite iframes

Reduza cookies no site

Cuidado com código com grandes processamentos do JS

Otimize:

- imagens:
- CSS

Use favicon pequeno

Mantenha os componentes em no máximo 25KB

Evite imagens vazias, src=""

[https://developer.yahoo.com/performance/rules.html](https://developer.yahoo.com/performance/rules.html)


