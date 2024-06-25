# InstructLab: Explorando a Inteligência Artificial no seu Notebook

![Banner](https://github.com/allanroque/instructlab/blob/main/assets/instructlab-banner.png)

### O que é o InstructLab?
O InstructLab é uma ferramenta poderosa que transforma seu terminal em um laboratório de inteligência artificial. Utilizando a interface de linha de comando (CLI), você pode baixar, configurar e conversar com Modelos de Linguagem de Grande Escala (LLMs), que são sistemas avançados capazes de entender e gerar textos de forma inteligente.

### Por que usar o InstructLab?
1) **Acessibilidade:** Projetado para ser utilizado em computadores comuns, o InstructLab permite que qualquer pessoa explore o mundo da IA sem necessidade de equipamentos caros.
2) **Facilidade de Uso:** Comandos simplificados e uma estrutura clara facilitam o aprendizado e a execução das tarefas, mesmo para iniciantes.
3) **Flexibilidade:** Se você deseja experimentos mais robustos, o InstructLab também é capaz de operar em hardware mais sofisticado, permitindo a geração de dados e afinação de modelos com alta fidelidade.

### Primeiros Passos com InstructLab
A instalação e utilização do InstructLab são feitas diretamente pelo terminal do seu sistema operacional, seja macOS ou Linux. Os passos incluem a instalação de ferramentas de desenvolvimento, preparação de um ambiente Python virtual, e comandos simples para iniciar a interação com o modelo de IA. Você será guiado passo a passo pelo próprio sistema do InstructLab, garantindo que não fique perdido durante o processo.

### Comece a Explorar a IA Hoje Mesmo!
Quer você seja um estudante, um entusiasta da tecnologia, ou alguém curioso sobre inteligência artificial, o InstructLab oferece uma porta de entrada acessível e poderosa para o mundo da IA. Experimente, aprenda e crie com o InstructLab no conforto do seu notebook!

Para mais detalhes e guias de instalação, visite nossa [página oficial](https://github.com/instructlab/instructlab/tree/main?tab=readme-ov-file#instructlab--ilab).

# instructlab
Montando um ambiente InstructLAB passo-a-passo, com Modelo e Interface de Chat. Executável em qualquer notebook sem grandes requisitos de hardware.

Instruções para:

## [Mac](#no-mac)
## [RHEL 9](#no-rhel-9)
## [Fedora](#no-fedora)

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
