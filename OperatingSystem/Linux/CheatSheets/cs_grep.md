# Grep

## Sintaxe e uso

```bash
grep [OPTIONS] [PATTERNS] [FILE]
```

- `grep` busca pelo padrões definidos em cada arquivo passado. Esses padrões são uma string com um ou mais *patterns* *regex* separadas por um caractere "*newline*".
- `grep` fará a busca e imprimirá em tela cada linha que corresponde à *regex*.
- Um "*FILE*" passado como "-" denota o *standard input*. Se nenhum arquivo é especificado, então buscas recursivas examinam o diretório de trabalho enquanto não recursivas buscam no *standard input*.
- Além disso, variantes como `egrep`, `fgrep`e `rgrep` são derivativos do `grep` tradicional.

## Exemplos de opções

| Comando | Descrição |
|---------|-----------|
| `grep ´alias´ <FILENAME>` | encontra todas as ocorrências de uma string |
| `grep -c ´error´ /var/logs/syslog` | conta o número de ocorrências |
| `grep -e ´linux$´ <FILENAME>` | usa regex para buscar linhas terminadas em ´linux´ |
| `grep -f <PATTERN_FILE> .bashrc` | lê as *patterns* de um arquivo |
| `grep -i ´Alias´ .bashrc` | busca ocorrências com letras maiúsculas e minúsculas |
| `grep -l ´alias´ /home/traw/*` | retorna os arquivos com ocorrências |
| `grep -L ´alias´ /home/traw/*` | retorna os arquivos sem ocorrências |
| `grep -r ´error´ /var/log/log.txt` | busca recursiva, incluindo subdiretórios |
| `grep -v ´warning´ /home/traw/log.txt` | seleciona as linhas sem ocorrências |
| `grep -m 3 ´alias´ .bashrc` | limita o output para três linhas |
| `grep -n ´sudo´ .bashrc`  | imprima o número das linhas em que há ocorrências |
| `grep -o ´search string´ .bashrc` | imprime apenas a parte correspondente da string |
| `grep -x ´linux is love´ <FILENAME>` | busca por ocorrências em linhas completas |
| `grep -w ´alias´ <FILENAME>` | busca por ocorrências em palavras completas |
| `grep -A 6 ´error´ erro.log` | imprime seis linhas após a ocorrência |
| `grep -B 2 ´warning´ error.log` | imprime duas linhas antes da ocorrência |
| `grep -C 7 ´info´ error.log` | imprime sete linhas antes e após a ocorrência |
| `grep -E ´b(a\|e)g´ filename` | regex estendido, linhas contendo "bag" ou "beg"|

## Quantificadores

| Quantifier | Descrição |
|---------|-----------|
| `{n}`   | Procura exatamente "n" ocorrências |
| `{n,}`  | Procura "n" ou mais ocorrências |
| `{,m}`  | Procura até "m" ocorrências |
| `{n,m}` | Procura entre "n" e "m" ocorrências |

## Curingas

| Wildcard | Descrição |
|----------|-----------|
| `.` | Busca ocorrência de qualquer caractere, à exceção de "newline" |
| `?` | Busca zero ou uma ocorrência |
| `*` | Busca 0 ou mais ocorrências |
| `+` | Busca 1 ou mais ocorrências |

## Posicionais

| Wildcard | Descrição |
|----------|-----------|
| `^` | ocorrências no início da linha |
| `$` | ocorrências no final da linha |
| `^$` | ocorrências de linhas vazias |
| `\<` | ocorrências no início da palavra |
| `\>` | ocorrências no final da palavra |

## Classes de caracteres

| Notação | Descrição |
|---------|-----------|
| `[A-Za-z]` | Qualquer letra maiúscula ou minúscula |
| `[0-9]` | Qualquer número |
| `[0-9A-Za-z]` | Qualquer número ou letra maiúscula ou minúscula |

## Posix

| Notação | Descrição |
|---------|-----------|
| `[:alpha:]` | Busca ocorrência de qualquer caractere alfabético, maiúsculo ou minúsculo |
| `[:alnum:]` | Busca ocorrência de qualquer caractere alfanumérico |
| `[[:blank:]]` | Busca ocorrência de espaço ou tabulação |
| `[:digit:]` | Busca a ocorrência de dígitos numéricos|
| `[[::]]` | Busca ocorrência de caracteres alfabéticos minúsculos |
| `[[:print:]]` | Busca ocorrências de caracteres imprimíveis |
| `[[:punct:]]` | Busca ocorrências de caracteres de pontuação |
| `[[:upper:]]` | Busca ocorrência de caracteres alfabéticos maiúsculos |

## Basic Regular Expressions (BRE)

A menos que sejam precedidos por uma contra-barra, os caracteres abaixo tem um significado específico em BREs:

```plaintext
ˆ $ . * [ ] \
```

Entretanto, a menos que sejam precedidos por uma contra-barra, os caracteres abaixo não tem um significa especial em BREs:

```plaintext
? + { } | ( )
```

## Extended Regular Expression (ERE)

A menos que sejam "escapados" com uma contra-barra, ERE garante aos caracteres abaixo um significado único:

```plaintext
^ $ . * + ? [ ] ( ) | { }
```

## Perl Compatible Regular Expressions (PCRE)

Ganchos e classes de caracteres adicionais, expressões condicionais, comentários e outras funcionalidades estão disponíveis com PCRE.