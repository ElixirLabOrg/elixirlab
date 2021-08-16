+++
title = "Comandos do terminal para iniciantes"
description = "Quando começamos a programar, muitas vezes precisamos usar o terminal. Aqui estão os comandos mais usados no meu dia a dia"
author = "Rachel Curioso"
date = "2021-08-13"
tags = ["terminal", "tutorial"]
categories = ["terminal", "tutorial", "windows"]
[[images]]
  src = "img/terminal-iniciante/cover.jpg"
  alt = "Imagem de um terminal com fundo preto e tela verde"
  stretch = "cover"
+++

# Comandos Úteis do terminal para iniciantes
## Navegação
| Comando                           | Função                                         |
| --------------------------------- | ---------------------------------------------- |
| cd `NOME DA PASTA`                | Navega para a pasta em questão✳️               |
| cd ..                             | Volta uma pasta no diretório                   |
| ll (são 2 L minusculos)           | lista todos os arquivos da pasta               |
| `tecla tab`                       | Auto complete ✳️✳️                             |
| rm `nome_do_arquivo ou pasta`     | Remove o arquivo/pasta (se ela tiver vazia)    |
| rm -rf `nome_do_arquivo ou pasta` | remove arquivo/pasta e tudo que tem dentro     |
| mkdir `nome_da_pasta`             | Cria uma pasta no diretorio que você está      |
| touch `arquivo.extensao_qualquer` | Cria um arquivo em branco no dir que você está | 

✳️ você tem acesso apenas as pastas adjacentes. Se você quiser acessar uma pasta que está dentro de outra pasta, vai precisar entrar nela priemeiro. ex:
Pasta 1 > Pasta 2
Se eu estou na pasta 1 e quero ir até a pasta 2, eu posso fazer `cd Pasta 1 **enter** cd Pasta 2 **enter**` 
ou `cd Pasta 1/Pasta 2`
Como nem sempre é claro o caminho de diretorios que precisamos percorrer, é interessante aliar o `cd` com o comando `ll`e a tecla `tab` no seu teclado
✳️✳️ exemplo: cd `**tab**` vai mostrar todas as pastas disponiveis.
✳️✳️ outro exemplo: cd doc `**tab**` vai mostrar todos as pastas disponiveis que começam com "doc"

## Elixir/Phoenix
💧 <- Comandos que vão rodar em qualquer pasta desde que você tenha o elixir instalado
💦 <- Comando que vai rodar em qualquer projeto elixir 
🐣 <- Comandos que vão funcionar em projetos phoenix


| Comando                  | Função                                                |
| ------------------------ | ----------------------------------------------------- |
| 💧 iex                   | abre o elixir iterativo (ctrl+c 2x pra sair)          |
| 💦 iex -S mix            | abre o elixir iterativo, com acesso aos arquivos✳️    |
| 💦 mix test              | Começa servidor phoenix                               |
| 💦 mix format            | Vai formatar seu código pra deixar bonito             | 
| 🐣 mix phx.server        | Roda todos os testes da sua aplicação                 |
| 🐣 iex -S mix phx.server | Roda seu phoenix no modo iterativo                    |
| 🐣 mix ecto.create       | Cria sua tabela no banco, se você estiver usando ecto |
| 🐣 mix ecto.migrate      | Roda as migrations do seu banco                       |
| 🐣 mix ecto.drop         | Vai apagar todo o seu banco de dados                  |
✳️ Ele vai compilar os arquivos da pasta pra você, e você vai ter acesso a todo o código do seu projeto no elixir iterativo


## Miscelania
| comando                | Função                                 |
| ---------------------- | -------------------------------------- |
| code .                 | Abre a pasta que você ta no vscode ✳️  |
| code `NOME DO ARQUIVO` | Abre o arquivo em questão no vscode ✳️ |

✳️ O mesmo vale para outros editores. `vim .`, ou `atom .`, por exemplo

*Imagem da capa por [Jake Walker](https://unsplash.com/@jakewalker)*