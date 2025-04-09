# Curl

## Sintaxe

```bash
curl [parametros] [URL]
```

## Operações básicas

| Comando         | Descrição                                |
| --------------- | ---------------------------------------- |
| `curl [URL]`    | Busca o conteúdo da URL                  |
| `curl -O [URL]` | Download do arquivo na URL               |
| `curl -L [URL]` | Busca a URL e segue os redirecionamentos |

## Transferência de dados

| Comando                                             | Descrição                                |
| --------------------------------------------------- | ---------------------------------------- |
| `curl -d "key1=value1&key2=value2" [URL]`           | Post com as informações dadas            |
| `curl -d '{"key1"="value1","key2"="value2"}' [URL]` | Post com as informações dadas em um JSON |
| `curl -F "file=<FILE_PATH>" [URL]`                  | Upload de um arquivo                     |

## Autenticação & Headers

| Comando                                   | Descrição                                   |
| ----------------------------------------- | ------------------------------------------- |
| `curl -u <USERNAME>:<PASSWORD>`           | Autenticação HTTPS básica                   |
| `curl -H "Authorization: Bearer <TOKEN>"` | Adiciona valores ao cabeçalho da requisição |

## Outras opções

| Comando                         | Descrição                                                     |
| ------------------------------- | ------------------------------------------------------------- |
| `curl --limit-rate 1M -O [URL]` | Download de arquivo com taxa limite de transferência definida |
| `curl -C - -O [URL]`            | Retoma download interrompido                                  |
| `curl -x [PROXY] [URL]`         | Utiliza um proxy para a requisição                            |

## Informações & Debug

| Comando         | Descrição                  |
| --------------- | -------------------------- |
| `curl -v [URL]` | Modo verboso               |
| `curl -I [URL]` | Retorna apenas o cabeçalho |

## SSL (Secure Socket Layer)

| Comando                        | Descrição                              |
| ------------------------------ | -------------------------------------- |
| `curl -k [URL]`                | Pula a verificação de certificados SSL |
| `curl --cert <CERT.PEM> [URL]` | Utiliza o certificado na requisição    |

## Flags comuns

| Comando                      | Descrição                                           |
| ---------------------------- | --------------------------------------------------- |
| `-d`, `--data <data>`        | HTTP post data                                      |
| `-f`, `--fail`               | Falha rápida sem saídas HTTP error                  |
| `-1, --include`              | Inclui os cabeçalhos na resposta                    |
| `--output <file>`             | Escreve a saída em um arquivo ao invés do stdout    |
| `-O`, `--remote-name`        | escreve a saída em um arquivo nomeado como o remoto |
| `--silent`                   | modo silencioso                                     |
| `-T`, `--upload-file <file>`   | Upload de um arquivo local para o remoto            |
| `<user:password>`            | Nome de usuário e senha do servidor                 |
| `-A`, `--user-agent <name>`  | Enviaan User-Agentpar o servidor                    |
