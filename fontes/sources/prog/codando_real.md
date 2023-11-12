## Codando na vida real

Um exemplo prático e real de programação para atender um pedido extra de um cliente

Ao criar um pequeno CRUD para um cliente, após concluir ele me pergunta se eu posso adicionar ao banco alguns registros que ele criou em um arquivo texto.

Era um pequeno cadastro de produtos:

descricao
preco

Os arquivos estavam mais ou menos assim:

Banana prata
3.15

Manga rosa
2.85

...

Num total de 508 linhas.

Acho importante por dois motivos: desafia meus conhecimentos e me ajuda a melhorar minha capacidade de resolver problemas. Além disso, o que é mais importante, ajuda o cliente a evitar trabalho. Imagina digitar 254 registros manualmente?! É importante manter este número em mente (254) para aferir o resultado final.

A solução foi encontrada usando o VSCode e o PHP.

### VSCode

- Abro o VSCode
- Crio um novo arquivo tipo Plain text
- Copio e colo todo o conteúdo do arquivo texto contendo os produtos no VSCode
- Usando expressões regulares remover todas as linhas em branco
- Teclo Ctrl+H para procurar e sobrescrever. Na caixa de texto superior digito "^(?:[\t ]*(?:\r?\n|\r))+" sem as aspas. A de baixo deixo vazia e clico no botão Replace All

Prontinho. Todas as linhas em branco foram removidas

Procurei por uma rotina para manipular o arquivo texto que restou. Neste momento minha preferência é por soluções mais simples. Acho isso importante em si e em especial porque gosto de compartilhar e ensinar o compartilho, portanto a mais simples é a melhor. Encontrei várias soluções, inclusive uma função criada pelo programador no site SitePoint.

A solução mais simples que encontrei para transformar o arquivo texto em um array em PHP foi esta abaixo:
```php
$linhas = file("elias.txt");
```
Agora eu posso varrer todas as linhas do arquivo assim, usando o foreach ou o for. Neste caso o for é mais adequado:
```php
$c = count($linhas);
for($x = 0;$x < $c;$x++){
    print $linhas[$x] . '<br>';
}
```
Assim ele imprimirá cada linha do arquivo texto em uma linha na tela e então poderei pensar em como criar um arquivo .sql pela menipulação de strings do PHP.

Depois de muitas tentativas, veja abaixo o código que me trouxe a solução:
```php
<?php

$linhas = file("elias.txt");
$c = count($linhas);

$values = '';

for($x = 0;$x < $c;$x++){
    if($x < 507) {        
        $login = $linhas[$x];
        $senha = $linhas[$x + 1];
        $x = $x + 1;
    }
    $values .="('$login', '$senha'),<br>";
}

print $values;
```
Ao executar me mostra tudo assim:
```php
('Banana prata ', '3.15 '),
('Manga rosa ', '2.85 '),
('Banana prata ', '3.00 '),
...
```
Veja que existe um espaço em branco ao final de cada campo.

Então copio tudo e salvo em um arquivo do meu editor de texto/código preferido (Xed) e teclo Ctrl+H (isso também funciona inclusive no Bloco de notas no Windows).

Na caixa de cima digito um espaço em branco e o apóstrofo:
 '

Na de baixo digito apenas o apóstrofo
'

Então removo os espaços indesejados.
```php
('Banana prata', '3.15'),
('Manga rosa', '2.85'),
('Banana prata', '3.00'),
...
```
Agora crio o início do arquivo:
```php
INSERT INTO produtos (descricao, preco) VALUES
('Banana prata', '3.15'),
('Manga rosa', '2.85'),
('Banana prata', '3.00'),
...
```
Ao final troco a vírgula pelo ;

E o resultado já pode ser executado para adicionar os registros ao banco.

A criação do CRUD em si ou de um aplicativo é importante, mas geralmente é um código que já conhecemos, depois de ter criado algumas vezes, mesmo que geralmente apareçam problemas. Já este tipo de código geralmente não temos solução pronta e requer conhecimento, raciocínio lógico e empenho. Além de me ajudar a exercitar meus conhecimentos ele resolve um grande problema do cliente. Veja que praticamente não usamos conhecimento de matemática. O quente mesmo foi raciocinar com lógica para entender e resolver o problema. Isso dignifica a programação. Acho que é para isso que ela serve, para facilitar a vida das pessoas, mesmo que para isso precise de alguém que se empenhará para encontrar a solução: eu ou você.

Numa tentativa deixei os campos se duplicarem e a quantidade de registros gerada foi de 508. Então adicionei o $x = $x + 3; para corrigir. Desta vez reduzi os registros e somente quando ajustei para $x = $x + 1 ficou redondo. 

Se analisar com calma, verá que realmente precisamos usar cada linha, que tem a metade de um registro. Então pego o x da primeira linha, junto com o x da segunda e pulo uma linha. Isso é feito com $x = $x + 1, que avisa ao for que o valor do x foi incrementado. Geralmente se usa $x++; mas prefiro como está que fica mais claro.


