Criado inicialmente para contar usuários de um site (1.0)
Sua segunda versão já servia como um interpretador de formulários (2.0)
PHP passou a significar PHP Hypertext Processor (3.0)

## AMP:
- **A**pache (Servidor que roda a aplicação PHP)
- **M**ySQL (Banco de dados)
- **P**HP (Linguagem de programação)

Atribuição de dados por coerção (Interpreta o tipo pelo dado atribuído, como no Python, mas pode forçar o type da variável por meio do typecast do PHP).

## Valores aritméticos:
- `abs()` -> Valor absoluto (módulo)
- `pow()` -> Potenciação
- `sqrt()` -> Radiciação
- `round()` -> Arredondamento
- `ceil()` -> Arredondamento sempre pra cima
- `floor()` -> Arredondamento sempre para baixo
- `intval()` -> Pega a parte inteira
- `number_format()` -> Formatação de valores

## Variáveis de variáveis

Exemplo:
```php
\(site = 'google';\)\$site = 'amazon';
```

Na memória ficaria algo como:
- `$site` -> 'google'
- `$google` -> 'amazon'

## Operador Ternário

Sintaxe: `(expressão) ? (verdadeiro) : (falso)`

Exemplo 1:
```php
\$maiorValor = a > b ? a : b;
```
A expressão acima faz uma comparação se `$a` é maior que `$b`. Se for verdadeiro, `$maiorValor` vale `$a`, senão vale `$b`. Funciona como um `if/else` simplificado.

Exemplo 2:
```php
situacao = media < 7 ? 'reprovado' : 'aprovado';
```
Se `$media` for menor que 7, `$situacao` recebe 'reprovado', senão recebe 'aprovado'.

**Operadores lógicos:**
- **E:** `and`, `&&`
- **OU:** `or`, `||`
- **OU Exclusivo:** `xor`
- **NÃO:** `not`

`isset()` -> Método que verifica se uma variável existe e se ela não é nula.

### Diferença entre echo e print
O `print` aceita apenas um argumento e retorna sempre o valor 1. Isso significa que o `print` em condicionais sempre retorna 1 (que significa true), já o `echo` na mesma situação vai dar um erro de sintaxe.

> [!TIP]
> Preferencialmente usar sempre o `echo` ao invés do `print` devido a performance melhor e sintaxe mais simples.

---

## Manipulação de Strings

### Substring
Serve para poder ler apenas um pedaço específico da string.

```php
\$frase = ' Esta frase é para testes.';
fraseCortada = substr(frase, 5, 10);
```
O valor de `$fraseCortada` vai ser igual a `'frase é p'`.

Existe também o `mb_substr` que se difere do `substr` porque serve para leitura de strings com acentos e emojis. É ligeiramente mais lento, mas é mais seguro para UTF-8 e lê os caracteres reais da string, enquanto o `substr` lê os bytes.
*Lembrando que o segundo índice refere-se ao número de caracteres extraídos ao invés do índice final.*

### Explode e Implode
O `explode` permite que seja criado um array a partir de uma string:

```php
\$str_lugares = 'trabalho,faculdade,escola';
lugares = explode(',', str_lugares);
// \$lugares passa a valer ['trabalho', 'faculdade', 'escola']
```
O `explode` ainda tem um parâmetro opcional que define o limite de valores. O uso de uma string vazia `''` como separador retorna `false`.

O método `implode` faz exatamente o contrário:

```php
\$lugares = ['casa', 'faculdade', 'trabalho'];
\(str_lugares = implode(',',\)lugares);
// \$str_lugares devolve 'casa,faculdade,trabalho'
```

### String Replace
Usado por meio do método `str_replace(procurar, substituir, variavel)`.

```php
\$a = 'texto de exemplo';
echo str_replace('o', '0', \$a);
// No terminal aparecerá: 'text0 de exempl0'
```
Existe um quarto parâmetro opcional que indica quantas substituições serão feitas. Quando não é passado, ele faz todas sem limite.

### Strstr
Serve para retornar o resto de uma string a partir do ponto definido.

```php
\$string = 'ola tudo bem';
echo strstr(\$string, 't'); // Mostra: 'tudo bem'
```
Esse método tem um terceiro parâmetro booleano que faz o inverso (retorna o começo excluindo o ponto definido):

```php
echo strstr(\$string, 't', true); // Mostra: 'ola '
```

### Strpos (String Position)
Serve para encontrar o índice da **primeira** aparição de uma string dentro de outra.

```php
\$string = 'ola tudo bem com você?';
\$position = strpos(string, 't'); // position recebe 4
```
É possível passar um terceiro parâmetro para delimitar o início da busca:
```php
\$position = strpos(string, 'e', 11); // position retorna 18
```

* `strrpos()` -> Segue o mesmo princípio do `strpos`, mas encontra a **última** ocorrência.
* `stripos()` e `strripos()` -> Funcionam de forma idêntica aos anteriores, mas são **case-insensitive** (ignoram maiúsculas e minúsculas).

---

## Recursos de Terminal

### Number Format
Método `number_format()` possui até 4 parâmetros:
1. Valor a ser formatado.
2. Número de casas decimais.
3. Caractere separador da parte decimal.
4. Caractere separador de milhares.

### $argv
Serve para ler valores de variáveis enviadas pelo terminal. Pouco usado no desenvolvimento de APIs Rest porque os dados vêm nas requisições via body, path variables, query variables ou headers.

### $argc
Serve para mostrar a quantidade de parâmetros que foram enviados pelo terminal.


## DateTime

- Manipulação de datas
- Instânciado com new DateTime

## Timestamp
- Também é uma biblioteca de manipulação de dadas, permitindo a contagem em segundos a partir do dia 1 de janeiro de 1970 as 00h00min00sec

