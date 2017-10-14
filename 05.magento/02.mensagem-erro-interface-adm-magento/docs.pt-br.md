---
title: 'Mensagem de erro no Magento:  ''Your web server is configured incorrectly'''
external_links:
    process: true
    title: false
    no_follow: true
    mode: active
    target: _blank
---

Ao acessar a interface de administração do magento encontro uma mensagem de erro: 
> Your web server is configured incorrectly

Este artigo aborda um problema que pode ocorrer quando você tenta acessar o painel de administração do Magento, bem como a forma de resolvê-lo.

===

## Problema

Quando você tenta acessar o painel de administração do Magento, você recebe a seguinte mensagem de erro no seu navegador:

> Seu servidor web está configurado incorretamente.  Como resultado, os arquivos de configuração com informações confidenciais são acessíveis a partir do exterior.  Entre em contato com o seu provedor de hospedagem. 

> Your web server is configured incorrectly. As a result, configuration files with sensitive information are accessible from the outside. Please contact your hosting provider.

## Causa

Esse problema ocorre porque as permissões de arquivos estão incorretas, ou porque há um arquivo _.htaccess_ faltando no subdiretório app da instalação Magento.

## Resolução

Para resolver este problema, siga estes passos abaixo:
1. Confirmar que existe um arquivo _.htaccess_ no subdiretório app da instalação Magento. Se o arquivo _.htaccess_ está faltando, criar um novo arquivo _.htaccess_ no subdiretório aplicativo que contém as seguintes diretrizes:
```
Order deny,allow
Deny from all
```
    
2. Confirmar se as permissões dos arquivos estão definidas corretamente. Geralmente, os diretórios devem ter permissões definido para `755` (ler, escrever e executar permissões para o usuário, e ler e executar permissões para o grupo e mundo). Os arquivos devem ter permissões definidas para `644` (ler e escrever permissões para o usuário, e ler permissões para o grupo e mundo). 

Você pode alterar as permissões para todos os arquivos e diretórios em sua instalação Magento usando a linha de comando via SSH. Para fazer isso, siga estes passos:
+ Faça login na sua conta usando SSH.
+ No prompt de comando, mude para o diretório onde você instalou Magento. Por exemplo, se Magento é instalado no diretório raiz do documento, exemplo `cd ~ / public_html`.
+ Digite o seguinte comando: 
```find . -type f -exec chmod 644 {} \;```
+ Em seguida, Digite o seguinte comando: 
```find . -type d -exec chmod 755 {} \;```