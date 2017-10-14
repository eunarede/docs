---
title: 'Instalando WebSphere MQ Client e PHP mqseries no CentOS CloudLinux'
published: true
date: '14-08-2017 20:31'
publish_date: '14-08-2017 20:34'
taxonomy:
    tag:
        - servidores
        - websphere
        - 'websphere mq client'
        - 'php mqseries'
external_links:
    process: true
    no_follow: true
    target: _blank
visible: true
---

## Instalando o WebSphere MQ Client

> O IBM WebSphere MQ (também chamado de MQ) é um middleware da IBM orientado a mensagem. Ele permite que aplicações independentes e potencialmente não concorrentes, rodando em sistemos heterogêneos, se comuniquem entre si. É suportado em mais de 20 plataformas de ambientes diferentes.

Baixe a versão necessária do WebSphere MQ Client em [https://www-01.ibm.com/software/integration/wmq/clients/](https://www-01.ibm.com/software/integration/wmq/clients/) (para este tutorial é recomendado a utilização do WebSphere MQ V7.5 client em ambiente 64bits).

Crie um diretório chamado websphere em seu servidor e suba o binário do cliente:

```shell
cd ~
mkdir websphere
```

Descompacte o binário

```shell
tar -xvzf 7.5.0.8-WS-MQC-LinuxX64.tar.gz
```

Antes de iniciar a instalação dos arquivos rpm, será necessário aceitar a licença de utilização imposta pela IBM, para isso, rode os seguintes comandos:

```shel
./mqlicense.sh -accept
```

Instale o IBM WebSphere MQ. Os componentes mínimos que você deve instalar são o MQSeriesRuntime e o MQSeriesClient. Você precisará instalar o "MQSeriesSDK" para obter as bibliotecas corretas no local para compilar a extensão do PHP.

```shell
rpm -ivh MQSeriesRuntime*.rpm
rpm -ivh MQSeriesClient*.rpm
rpm -ivh MQSeriesSDK*.rpm
```

estes comandos instalarão as três bibliotecas necessárias no diretório padrão **_/opt/mqm_**. Agora você deve configurá-lo como a instalação principal. Digite o seguinte comando no prompt de comando:

```shell
/opt/mqm/bin/setmqinst -i -p /opt/mqm/
```
Você pode ter apenas uma instalação principal em um sistema. Se já existe uma instalação primária no sistema, você deve desatualizá-lo antes de poder configurar outra instalação como a instalação principal.

## Instalando o PHP mqseries

Para a compilação e instalação da biblioteca **mqseries** para o PHP, é necessário verificar a existência ou realizar a instalaçaão das seguintes dependências:

```shell
yum install php-devel
yum install gcc
yum install re2c
```
Baixe a versão mais recente da extensão do php 'mqseries':

```shell
wget -N https://pecl.php.net/get/mqseries-0.15.0.tgz
tar -zxvf mqseries-0.15.0.tgz
cd mqseries-0.15.0
```
Compile o módulo mqseries executando os seguintes comandos:

**CentOS**
```shell
phpize
./configure --with-libdir=lib64
```

**CloudLinux**
```shell
/opt/alt/php5X/usr/bin/phpize
./configure --with-php-config=/opt/alt/php5X/usr/bin/php-config
```
!!! Substitua o diretório _php5X_ pelo diretório da versão para o qual deseja compilar o mqseries

Crie o arquivo .so:
```shell
make
```

Copie o módulo de extensão mqseries pata o local dos módulos php:

**CentOS**
```shell
cp modules/mqseries.so /usr/lib64/php/modules/
```

**CloudLinux**
```shell
cp -rp modules/*.so /opt/alt/php5X/usr/lib64/php/modules/
```
!!! Substitua o diretório _php5X_ pelo diretório da versão para o qual deseja copiar o arquivo mqseries.so

Configure o **php.ini** 

**CentOS**
Crie o arquivo ```/etc/php.d/mqseries.ini``` com o comando ```vi /etc/php.d/mqseries.ini``` e adicione a extensão:
```shell
; Enable mqseries extension module
extension=mqseries.so
```

**CloudLinux**

Adicione um arquivo ini para o módulo em ```/opt/alt/php5x/etc/php.d.all``` com o comando ```vi /opt/alt/php5x/etc/php.d.all/mqseries.ini```
```shell
; Enable mqseries extension module
extension=mqseries.so
```
rode em seguida ```cagefsctl --setup-cl-selector``` para atualizar o cagefs

Bibliotecas de referência:
- [mqseries-php](https://github.com/bariton3/mqseries-php)

Fontes de referência:
- [http://techish.io/blog/2013/06/how-to-connect-websphere-mq-from-php/](http://techish.io/blog/2013/06/how-to-connect-websphere-mq-from-php/)
- [https://pecl.php.net/package/mqseries](https://pecl.php.net/package/mqseries)
- [https://pt.wikipedia.org/wiki/WebSphere_MQ](https://pt.wikipedia.org/wiki/WebSphere_MQ)
- [http://php.net/manual/pt_BR/book.mqseries.php](http://php.net/manual/pt_BR/book.mqseries.php)
- [https://blog.phpdeveloper.org/2009/07/29/mqphp-linking-ibms-websphere-mq-to-php/](https://blog.phpdeveloper.org/2009/07/29/mqphp-linking-ibms-websphere-mq-to-php/)
- [https://docs.cloudlinux.com/index.html?compiling_your_own_extensions.html](https://docs.cloudlinux.com/index.html?compiling_your_own_extensions.html)
- [Installing WebSphere MQ client on Linux](https://www.ibm.com/support/knowledgecenter/en/SSFKSJ_7.5.0/com.ibm.mq.ins.doc/q009010_.htm)