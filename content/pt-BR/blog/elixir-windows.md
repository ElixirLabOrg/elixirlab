+++
title = "Como instalar elixir no windows"
description = "Nesse tutorial ensinaremos como instalar elixir no windows usando wsl e asdf!"
author = "Rachel Curioso"
date = "2021-08-08"
tags = ["elixir", "tutorial"]
categories = ["elixir", "tutorial", "windows"]
[[images]]
  src = "img/elixir-windows/cover.jpg"
  alt = "Nuvens em tons de azul, rosa e roxo"
  stretch = "cover"
+++

## 1. Instalação do WSL

O primeiro passo é instalar o WSL (windows system for Linux) na sua máquina.

1. Se o seu windows está em português, vai em Windows > recursos do windows. Caso seu windows esteja em inglês, procure por “Windows Features” ao invés de “Recursos do windows”.

![um print screen do menu inicial do windows com evidenciando o aplicativo 'ativar ou desativar recursos do Windows'](/img/elixir-windows/01.png)

2. Marcar a opção “Subsistema do Windows para Linux”. Caso seu windows esteja em inglês, a opção se chama “Windows Subsystem for Linux”

![Uma imagem da janela de recursos do windows evidenciando a opção 'subsistema do windows para linux', que é a sexta opção de baixo pra cima](/img/elixir-windows/02.png)

3. Abrir a Microsoft Store.

4. Procurar a sua distro (distribuição Linux) de preferência. Algumas das distros disponíveis são:
* Ubuntu
* OpenSuse
* Kali Linux
* Debian
* Alpine WSL

5. Instale a Distro da sua preferência. Para esse tutorial, usarei a versão mais recente do Ubuntu, que nesse momento é a 20.04.

![a imagem mostra a janela da microsoft store, com o app 'ubuntu 20.04 lts' a amostra. A imagem também evidencia o botão de instalar, no canto superior direito da janela](/img/elixir-windows/03.png)

Dando certo, o botão da direita vai virar “iniciar” e você poderá usar o ubuntu no seu windows
Se você procurar no menu do windows pelo nome da distro que você instalou, já deverá estar disponível pra você.

6.  Abra a distro que você instalou.

Na primeira vez que você acessa o seu subsistema linux, aparece uma notificação que ele está instalando e, um pouco depois, ele pede para você cadastrar sua conta no linux, com o nome do seu usuário e senha. 
Esses dados não necessariamente são iguais aos do windows. Você pode colocar o que quiser. 

![imagem do terminal do ubuntu no windows depois de instalar o ubuntu, pedindo usuário e senha para primeira configuração](/img/elixir-windows/04.png)

Dando tudo certo, deve aparecer no terminal algo como “seuUsuario@seuComputador:”

![Imagem do terminal do ubuntu no windows, depois de dar certo, exibindo o texto que pede para o usuario atualizar usando 'sudo apt update'](/img/elixir-windows/05.png)

7. Faça a atualização do seu ubuntu com o comando `sudo apt update`.

8. Aconselho a instalar também o windows terminal que você encontra na Microsoft Store. Depois de instalar e abrir o windows terminal, se você apertar na seta apontada para baixo, tem a opção de abrir um prompt linux. (É possível ir nas configurações e determinar o ubuntu como seu prompt padrão).

![Imagem do windows terminal. O terminal possui uma aba aberta com o ubuntu para linux, e um menu drop-down do lado direito das abas com opções dos diversos tipos de terminal disponiveis e opções de configuração](/img/elixir-windows/06.png)

## 2. Instalando o asdf

O asdf é um gerenciador de versões de linguagens de programação. Com ele, conseguimos instalar o suporte a diversas linguagem no nosso computador, bem como gerenciar diferentes versões delas.

O ideal é seguir o tutorial com o site do próprio asdf aberto - [https://asdf-vm.com/#/](https://asdf-vm.com/#/)

Pode reparar que no site não tem tutorial para windows, mas como nós usamos WSL, seguiremos o tutorial para linux.

1. Primeiro instalamos as dependências. No site aparecem algumas opções, como Aptitude, DNF, Pacman e Zypper. No ubuntu nós usamos Aptitude, então faremos a instalação com `sudo apt install curl git`.

2. Agora que instalamos as dependências, podemos instalar o asdf. O próprio asdf recomenda usar git, então é o que iremos usar.

3. Nesse próximo passo é importante saber qual o Shell que você tem. Hoje podemos usar o padrão do sistema, que é o bash, ou instalar um novo como o fish ou o zsh. Como o ubuntu é recém instalado, não fiz nenhuma modificação nele, o que significa que ele está com o padrão, que é o bash.

4. Com essas informações em mãos, posso dizer que estou usando bash & git.

5. No print abaixo ele pede para abrirmos o arquivo `~/.bashrc` e adicionarmos alguns comandos. Se você estiver usando o zsh ou o fish, o arquivo e os comandos são outros.

![A imagem foi tirada diretamente do site do asdf e mostra o menu de como instalar usando 'bash & git', no qual ele pede para adicionar duas linhas no arquivo .bashrc](/img/elixir-windows/07.png)

6. Vamos abrir o arquivo solicitado no terminal, usando o vim. Para isso digitamos `vim ~/.bashrc` no terminal.

7. Usando as setas do teclado vamos ao final do documento, apertamos a tecla i para entrar no modo de inserção, e colamos os dois comandos solicitados.

8. Depois disso, precisamos salvar o arquivo. Pressionamos esc > digamos :wq > enter.

9. Para as alterações funcionarem, é preciso reiniciar o shell. Podemos fazer isso fechando e abrindo o terminal.

Para saber se funcionou, digitamos `asdf`. Uma tela similar a esta deve aparecer:

![A imagem é uma captura de tela do terminal mostrando a documentação do asdf que aparece logo após digitarmos asdf no terminal](/img/elixir-windows/07.png)

## 3. Instalando o erlang

1. Antes de instalar o plugin do erlang, precisamos instalar as dependências. Conseguimos a lista dessas dependências no repositório do plugin do erlang para asdf - [https://github.com/asdf-vm/asdf-erlang#before-asdf-install](https://github.com/asdf-vm/asdf-erlang#before-asdf-install)

2. Nessa lista devemos procurar nosso sistema operacional e versão. No exemplo estamos usando o ubuntu 20.04, então encontramos [essa lista de dependências](https://github.com/asdf-vm/asdf-erlang#ubuntu-2004-lts).

3. Lembrando que para instalar coisas no linux, precisamos usar `sudo` antes dos comandos de instalação. Então copiarmos o comando acima, porém adicionando um sudo na frente. Então ficaria algo como `sudo apt-get -y install (....)`.

Deixo o alerta que esse é um processo bastante demorado.
Dá tempo de fazer um café ou um chá.

4. Agora que instalamos as dependências, instalamos o plugin do erlang usando `asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git` (o commando também pode ser encontrado no repositório do asdf-erlang)

5. Agora que temos o plugin propriamente instalado, precisamos instalar uma versão. Vamos usar a ultima. `asdf install erlang latest` - Esse processo também leva um tempo, mas costuma a ser mais rápido do que o passo anterior. Se quisermos instalar outra versão, precisamos repetir apenas esse passo, mas ao invés de digitarmos `asdf install erlang latest`, digitamos `asdf install erlang <versao>` 

6. Depois da instalação, precisamos definir qual a versão do erlang nós queremos usar. Esse passo é importante porque comumente temos mais de uma versão instalada. Pra isso digitamos `asdf global erlang latest`. (Caso queremos usar uma versão específica em uma pasta apenas, navegamos para dentro da pasta escolhida e digitamos `asdf local erlang latest`)

7. Uma das formas de ver se funcionou é digitar `asdf list erlang`. Se deu certo, a versão instalada deve aparecer pra você

8. Outra forma de ver se funcionou, digitamos `erl` no terminal e deve aparecer uma tela como essa

![A imagem é um print screen do terminal com a imagem do erlang iterativo, que aparece quando digitamos o comando 'erl'](/img/elixir-windows/08.png)

(para sair dela, basta apertar ctrl+c duas vezes)

## 4. Instalando elixir

1. Os passos que seguimos no elixir são bem similares aos da instalação do erlang. A diferença é que é muito muito muito mais rápido, e elixir não tem pré-requisitos de instalação no sistema. 

2. Vamos instalar o plugin de elixir do asdf com `asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git` e depois, `asdf plugin add elixir`.

3. Vamos instalar a última versão digitando `asdf install elixir latest`

4. Vamos definir a versão que queremos usar de elixir com `asdf global elixir latest`

Para checar se deu certo, podemos usar o `asdf list elixir`

Ou entrar no elixir iterativo usando `iex` (e assim como erlang, para sair dele, apertamos ctrl+c duas vezes.

Podemos também digitar no terminal `elixir -v` para verificar a versão do elixir e do erlang instaladas.

## 5. Opcionalmente instalando o nodejs.

1. NodeJS vai ser necessário caso você resolva trabalhar com phoenix um dia. Você pode pular esse passo, mas é possível que você precise instalar. O processo é igual ao do elixir.

2. Vamos instalar o plugin do nodejs do asdf com `asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git `, e depois com `asdf plugin add nodejs`

3. Vamos instalar a última versão digitando `asdf install nodejs latest`

4. Vamos definir a versão que queremos usar de nodejs com `asdf global nodejs latest`

Para checar se deu certo, podemos usar o `asdf list nodejs` ou com `node -v`

## 6. Uma explicação sobre versões de elixir

Quando instalamos as últimas versões de elixir e erlang, geralmente elas são compativeis entre si, mas na hora que precisamos instalar uma versão mais antiga, precisamos prestar atenção se a versão do elixir é compatível com a versão do erlang que nós instalamos. Como eu faço isso?
Quando digitamos o comando `asdf list elixir all` vai aparecer uma lista com as diversas versões disponíveis para instalação.

![A imagem é uma captura da tela do terminal mostrando algumas versões de elixir](/img/elixir-windows/09.png)

Se você prestar atenção, existem várias versões iguais, porém com um `otp-algo` no final. Se prestarmos atenção na versão 1.12.2 do print acima, por exemplo, vemos que ela existe como `1.12.2, 1.12.2-otp-22, 1.12.2-otp-23 e 1.12.2-otp-24`. Como eu sei qual escolher?

O número que vem depois do “otp” é a versão do erlang que aquela versão do elixir suporta.

Então se você está usando uma versão 22.x.x do erlang, você deve optar pela `1.12.2-otp-22`, por exemplo.

Parabéns, agora você já tem o elixir instalado no seu computador

![gif animado que mostra um cachorro golden retriver, com um jaleco e oculos de scientista. No lugar das patas do cachorro você consegue ver uma mão humana, e uma delas balança um Erlenmeyer com um liquido verde](/img/elixir-windows/10.gif)

*Imagem da capa por [Tadas Sar](https://unsplash.com/@stadsa)*