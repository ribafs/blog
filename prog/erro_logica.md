## Erro de lógica

Como é encarado este código em algumas linguagens
```php
x = 100

if(x = 10){
    print x
}
```
O código acima tem um erro de lógica, que algumas linaguagens ignoram e outras não executam, mostrando um erro.
É importante saber como se comporta a linguagem para ter uma ideia do resultado.


### JavaScript
```php
<script>
x = 100
if(x = 10){
alert(x)
}
</script>
```
Retorna 10


### PHP
```php
<?php
$x = 100;
if( $x = 10 ) {
    print $x;
}
```
Retorna 10


### R
```php
x <- 100

if (x <- 10) {
  print(x)
}
```
Retorna 10


### Ruby
```php
x = 100
if x = 10
   puts x
end
```
Retorna 10


### Java
```php
public class Main {
  public static void main(String[] args) {
    int x = 100;
    if (x = 10) {
      System.out.println(x);
    }
  }
}
```
Retorna o erro:
```php
javac Main.java
Main.java:4: error: incompatible types: int cannot be converted to boolean
    if (x = 10) {
          ^
1 error
```

### Python
```php
x = 100
if x = 10:
print x
```
Retorna o erro:
```php
File "/backup/www/t.py", line 3
    if x = 10:
       ^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

### C++

nano ola.cpp
```php
#include <stdio.h>

int main() {
  int x = 100;
  if (x = 10) {
    printf(x);
  }
  return 0;
}
```
gcc ola.cpp

Não gera o a.out, resulta no erro:
```php
ola.cpp: In function ‘int main()’:
ola.cpp:6:12: error: invalid conversion from ‘int’ to ‘const char*’ [-fpermissive]
    6 |     printf(x);
      |            ^
      |            |
      |            int
In file included from ola.cpp:1:
/usr/include/stdio.h:356:43: note:   initializing argument 1 of ‘int printf(const char*, ...)’
  356 | extern int printf (const char *__restrict __format, ...);
      |                    ~~~~~~~~~~~~~~~~~~~~~~~^~~~~~~~
ola.cpp:6:11: warning: format not a string literal and no format arguments [-Wformat-security]
    6 |     printf(x);
      |     ~~~~~~^~~
```

### C#
```php
using System;

namespace MyApplication
{
  class Program
  {
    static void Main(string[] args)
    {
      int x = 100;
      if (x = 10)
      {
        Console.WriteLine(x);
      }
    }
  }
}
```
Gera o erro:
```php
prog.cs(10,11): warning CS0665: Assignment in conditional expression is always constant. Did you mean to use `==' instead ?
prog.cs(10,11): error CS0029: Cannot implicitly convert type `int' to `bool'
Compilation failed: 1 error(s), 1 warnings
```

### Go

```php
apti golang-go

go version

nano teste.go

package main

import "fmt"

func main() {
    x = 100
    if x = 10 {
        fmt.Println(x)
    }
}

go run teste.go
```
Retorna
```php
go run t.go
# command-line-arguments
./t.go:7:10: syntax error: cannot use assignment (x) = (10) as value
```


