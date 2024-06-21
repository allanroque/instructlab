# instructlab
Montando um ambiente InstructLAB passo-a-passo, com Modelo e Interface de Chat. Executável em qualquer notebook sem grandes requisitos de hardware.

Instruções para:

[Mac](#no-mac)
[RHEL 9](#no-rhel-9)
[Fedora](#no-fedora)

## No RHEL 9:

~~~
* Como root:
; Para instalar o ferramental de compilação, GCC, CPP, etc
# yum groupinstall "Development Tools"

; Para instalar ambiente com libs mais novas no RHEL via Software Collections
# yum install gcc-toolset-12

* Saia do ambiente root, volte como usuário:
; Ativa o ambiente do Software Collections
$ scl enable gcc-toolset-12 bash

$ mkdir demo
$ cd demo

; Prepara o venv do Python
$ python -m venv venv

; Ativa o venv
$ source venv/bin/activate

; Atualiza o pip
$ python -m pip install --upgrade pip

; Instala o InstructLAB
$ pip3 install instructlab

; Verifica se o Instructlab está funcionando
$ ilab --version

; Prepara o esqueleto do Instructlabs.
$ ilab init
; Na pergunta sobre taxonomy; hit enter
; Na pergunta should i clone? Selecione y

; Troca o modelo de Merlinite para Granite
$ vi config.yaml
:%s/merlinite/granite/g

; Aqui é onde demora. Baixar o modelo (~4.5 GB)
$ ilab model download --repository instructlab/granite-7b-lab-GGUF --filename granite-7b-lab-Q4_K_M.gguf

; Iniciar o servidor. Deixe este terminal executando. Control-C para encerrar.
$ ilab model serve

* Abra um novo terminal
; Ativa o ambiente Software Collections
$ scl enable gcc-toolset-12 bash

$ cd demo

; Ativa o venv
$ source venv/bin/activate

; Abre a interface do chat
$ ilab chat
~~~

## No Fedora:

~~~
* Como root:
; Para instalar o ferramental de compilação, GCC, CPP, etc
# yum groupinstall "Development Tools"

; Instala o compilador C++
# dnf install gcc-c++

* Saia do ambiente root, volte como usuário:
$ mkdir demo
$ cd demo

; Prepara o venv do Python
$ python -m venv venv

; Ativa o venv
$ source venv/bin/activate

; Atualiza o pip
$ python -m pip install --upgrade pip

; Instala o InstructLAB
$ pip3 install instructlab

; Verifica se o Instructlab está funcionando
$ ilab --version

; Prepara o esqueleto do Instructlabs.
$ ilab init
; Na pergunta sobre taxonomy; hit enter
; Na pergunta should i clone? Selecione y

; Troca o modelo de Merlinite para Granite
$ vi config.yaml
:%s/merlinite/granite/g

; Aqui é onde demora. Baixar o modelo (~4.5 GB)
$ ilab model download --repository instructlab/granite-7b-lab-GGUF --filename granite-7b-lab-Q4_K_M.gguf

; Iniciar o servidor. Deixe este terminal executando. Control-C para encerrar.
$ ilab model serve

* Abra um novo terminal
; Ativa o ambiente Software Collections
$ scl enable gcc-toolset-12 bash

$ cd demo

; Ativa o venv
$ source venv/bin/activate

; Abre a interface do chat
$ ilab chat
~~~

## No Mac:

~~~
$ mkdir demo
$ cd demo

; Prepara o venv do Python
$ python -m venv venv

; Ativa o venv
$ source venv/bin/activate

; Atualiza o pip
$ python -m pip install --upgrade pip

; Instala o InstructLAB
$ pip3 install instructlab

; Verifica se o Instructlab está funcionando
$ ilab --version

; Prepara o esqueleto do Instructlabs.
$ ilab init
; Na pergunta sobre taxonomy; hit enter
; Na pergunta should i clone? Selecione y

; Troca o modelo de Merlinite para Granite
$ vi config.yaml
:%s/merlinite/granite/g

; Aqui é onde demora. Baixar o modelo (~4.5 GB)
$ ilab model download --repository instructlab/granite-7b-lab-GGUF --filename granite-7b-lab-Q4_K_M.gguf

; Iniciar o servidor. Deixe este terminal executando. Control-C para encerrar.
$ ilab model serve

* Abra um novo terminal
$ cd demo

; Ativa o venv
$ source venv/bin/activate

; Abre a interface do chat
$ ilab chat
~~~
