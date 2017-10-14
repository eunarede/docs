---
title: '''500 Internal Server Error'' durante a execução do PHP'
published: true
date: '28-06-2016 00:00'
publish_date: '28-06-2016 00:00'
external_links:
    process: true
    title: false
    no_follow: true
    mode: active
    target: _blank
taxonomy:
    service:
        - hospedagem
    tag:
        - permissao
        - php
        - hospedagem
        - 'erro 500'
        - 'internal server error'
    category:
        - docs
---

Este artigo descreve maneiras de minimizar a ocorrência de mensagens de "500 Internal Server Error".

===

## Problema

Os visitantes do seu site receberem mensagens "500 Internal Server Error" quando eles acessam uma página que usa PHP.

## Resolução

Quase todos os nossos servidores rodam PHP como um binário CGI. Um dos efeitos colaterais de rodar o PHP como um binário CGI é que os erros internos do servidor pode ocorrer se as permissões de arquivos e diretórios estão definidos incorretamente. erros internos do servidor também pode ocorrer se houver certas diretivas PHP definidas em um arquivo `.htaccess`.

Se o seu site está tendo erros internos do servidor, a primeira coisa que você deve fazer é verificar os logs do servidor. Os logs do servidor fornece informações valiosas sobre quais arquivos estão causando os erros, e as causas potenciais.

Se você tem uma conta de hospedagem compartilhada, você pode visualizar logs de erros do seu site no cPanel . Se você tem um VPS ou servidor dedicado, você pode visualizar os arquivos de log do seu site diretamente para os seguintes caminhos:

```
/usr/local/apache/logs/error_log
/usr/local/apache/logs/suphp_log
```

### Definir as permissões corretas

Se as configurações de permissão estão causando erros internos do servidor, você pode ver entradas nos logs do servidor semelhantes a qualquer uma das seguintes linhas:

```
SoftException in Application.cpp:357: UID of script "/home/username/public_html/.htaccess" is smaller than min_uid

SoftException in Application.cpp:146: Mismatch between target UID (511) and UID (510) of file "/home/username/public_html/index.php"

SoftException in Application.cpp:256: File "/home/username/public_html/index.php" is writeable by others
```
Esses erros são causados por problemas de permissão. As duas primeiras linhas indicam que o proprietário ou grupo do arquivo é definido incorretamente. Por exemplo, se o proprietário de um arquivo PHP é nobody ou root em vez de sua conta de usuário, os visitantes recebem um erro interno do servidor ao tentar visualizar a página.

Se você tem uma conta de hospedagem compartilhada, o nosso time de suporte pode alterar os proprietários e grupos para seus arquivos. Se você precisar de mais ajuda, por favor, abra um ticket de suporte com o nosso Guru no Portal do Cliente.

A terceira linha indica que as permissões de arquivo para o arquivo index.php são demasiado permissiva. Por exemplo, se o seu site tem um diretório ou arquivo cujas permissões estão definidas para 777 (permissões totais), qualquer pessoa pode ler, escrever, ou executá-lo.

Além disso, os visitantes recebem um erro interno do servidor ao tentar visualizar a página. Para resolver este problema, altere as permissões para 755 para diretórios e 644 para arquivos. Por exemplo, para definir as permissões corretas para todos os diretórios e arquivos no diretório public_html, digite os seguintes comandos:

```bash
cd public_html
find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;
```

### Verifique diretivas .htaccess

Servidores que executam o PHP como um binário CGI não pode usar as directivas php_flag ou php_value em um arquivo .htaccess. Se directivas em um arquivo `.htaccess` estão causando erros internos do servidor, você verá entradas nos logs do servidor semelhante à seguinte linha:

```
/home/username/public_html/.htaccess: Invalid command 'php_flag', perhaps misspelled or defined by a module not included in the server configuration
```

Para resolver esse problema, você deve colocar quaisquer diretivas do PHP em um arquivo de costume php.ini na sua conta, e remover ou comentar quaisquer diretivas do PHP no arquivo .htaccess.