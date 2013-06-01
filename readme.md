#Vagrant

Existem alguns passos necessários para instalar o [Vagrant](http://www.vagrantup.com/) usando o [VirtualBox](https://www.virtualbox.org/) com o ambiente ruby já configurado.

##A - Pré requisitos

**Certifiqie-se de que seu ambiente possua todas asferramentas abaixo instaladas antes de seguir para o próximo passo.**

Se você usa Windows, [aqui](http://zamboni.readthedocs.org/en/latest/topics/install-zamboni/vagrant-on-windows.html) está um tutorial detalhado de como instalar o Vagrant no ambiente Windows. Pare de segui-lo após isntalar o Vagrant **não instale o zamboni**, reinicie o computador e siga os próximos passos.

###Requisitos:

* [**Vagrant**](http://docs.vagrantup.com/v2/installation/index.html), para construir o ambiente de desenvolvimento ;
* [**Vagrant-vbguest**'](https://github.com/dotless-de/vagrant-vbguest/blob/master/Readme.md), um plugin para o Vagrant que adicionará alguns Hosts ;
* [**Librarian-Chef**](http://docs.vagrantup.com/v2/installation/index.html), um bundler para a infra-estrutura baseado no chef ;
* [**VirtualBox**](https://www.virtualbox.org/wiki/Downloads), uma ferramenta para criar e gerenciar máquinas virtuais ;
* [**Ruby**](http://www.ruby-lang.org/en/) including [**RubyGems**](http://rubygems.org/pages/download) ;
* [**git**](http://git-scm.com/), um sistema distribuido de controle de versão. Para windows, use [**mysysgit**](http://code.google.com/p/msysgit/downloads/list) que possibilita o uso do git no terminal (necessário para o Vagrant) ;

e, para usuários de Windows apenas:

* [**putty**], para permitir conexãoatravés do console por SSH.


##B - Instalação

**Abra o terminal (ou console de comandos) e digite os seguintes `comandos`:**

> NO windows, para abrir o console, abra o menu "Iniciar", clique em "Executar" e então digite "cmd". No Windows 8, para abrir o "Executar", abra o menu "Iniciar" e digite  "R"

###1 - Baixando os arquivos de configuração do Vagrant

Crie um diretório que irá conter seus projetos, e dentro dele:

* digite `git clone git@github.com:barboza/my-vagrant.git`
* entre no novo dretório com o comando `cd my-vagrnt`

###2 - Adicionando algumas ferramentas à sua VM

Dentro da pasta `my-vagrant`:

* Digite `librarian-chef install` para instalar o nodeJS, app e outros.
* Digite `gem install vagrant-vbguest`

###3 - Montando o Vagrant de acordo com as configurações do ambiente

* Rode o comando para levantar o Vagrant: `vagrant up`, e como não há uma VM ativa você será guiado através do processo de configuração e download da VM. Após isso, a VM será iniciada (sem todo o processo de configuração) assim como acontecerá todas as vezes que for iniciada.
* Instale algumas ferramentas extras: digite `vagrant provision`

##C - Use sua nova VM!

Da pasta `my-vagrant`, digite:

* `vagrant up` para iniciar a VM
* `vagrant-halt` para parar a VM

Para acessar a VM digite `vagrant ssh`, com isso você terá acesso ao console de comandos da sua VM.

###Acessando seu aplicativo

Crie seu aplicativo em uma pasta dentro da pasta `my-vagrant` na sua máquina. Para acessar a pasta do seu aplicativo dentro da VM, digite `cd /vagrant/pasta-do-seu-aplicativo`.

Para acessar um servidor rodando dentro da VM, abra um navegador web e digite na barra de endereços `http://localhost:3000`

###Editando os arquivos do seu projeto

Para acessar os arquivos, basta acessar a pasta `my-vagrant` na sua máquina.

 