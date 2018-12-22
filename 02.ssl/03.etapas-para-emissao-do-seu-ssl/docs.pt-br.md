---
title: 'Etapas para Emissão do seu SSL'
published: true
date: '12-06-2018 10:39'
publish_date: '12-06-2018 10:39'
taxonomy:
    category:
        - docs
        - ssl
    tag:
        - ssl
    service:
        - ssl
external_links:
    process: true
visible: true
recaptchacontact:
    enabled: false
---

[MINITOC]

A emissão de um certificado SSL requer algumas informações e procedimentos para a conformidade e validação das informações. Pedimos que você leia com atenção todas as etapas para a correta validação.

## Passo 1: Gerando o CSR

>>> este procedimento é realizado pelo Administrador de Sistemas ou a equipe técnica do seu provedor de hospedagem, para saber mais sobre o que é o arquivo CSR acesse [O que é CSR?](/ssl/o-que-e-csr).

A primeira etapa na solicitação do seu Certificado SSL é a geração do CSR. A geração do CSR depende inteiramente do software de servidor que você utiliza. Selecione o seu software/painel de servidor da lista ao lado depois de ler as instruções abaixo.

* [Apache / ModSSL](/ssl/gerar-csr-no-openssl)
* [OpenSSL](/ssl/gerar-csr-no-openssl)
* CPanel/WHM
* Cobalt RaQ
* Lotus Domino Go 4.6.2.6+
* Lotus Domino server 4.6x e 5.0x
* HSphere
* IBM HTTP Server
* iPlanet 4.x & SunONE Application Server 6.x
* Plesk

## Passo 2: Enviar CRS e dados de contato adminsitrativo

Após a aquisição do seu SSL, você receberá um e-mail com instruções para inserção dos dados do arquivo [CSR](/ssl/o-que-e-csr) e contato adminsitrativo, siga as etapas informadas nesta mensagem. 

## Passo 3: Validação do Domínio

Depois de configurar o seu certificado SSL, você receberá um número de pedido e instruções de como proceder. Guarde este número para futuras interações com nossa equipe de apoio. O processo de validação para emissão do SSL requer a verificação o domínio para garantir que sua empresa tem o direito de uso deste.

Para a Validação de Domínio, a Autoridade Certificadora enviará uma mensagem contendo a chave de verificação para um endereço de e-mail que esteja sob o domínio que se deseja validar. Este endereço de e-mail possui um padrão para verificação. Só serão aceitos os seguintes endereços de e-mail para validação:
* **webmaster**@seudominio.com.br
* **postmaster**@seudominio.com.br
* **admin**@seudominio.com.br
* **hostmaster**@seudominio.com.br
* **administrator**@seudominio.com.br

## Passo 4: Instalando o certificado

A última etapa será a instalação do arquivo CRT em seu provedor de hospedagem. O Arquivo CRT será enviado no endereço especificado no [Passo 3: Validação da sua solicitação](#passo-3-validao-do-domnio)