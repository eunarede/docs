---
title: 'Trust Logo Comodo PositiveSSL'
published: true
date: '20-09-2016 16:43'
publish_date: '20-09-2016 16:43'
taxonomy:
    category:
        - docs
    tag:
        - ssl
        - selo
        - comodo
        - 'trust logo'
        - positivessl
    service:
        - ssl
visible: true
---

Ao adquirir um certificado SSL Comodo junto a EunaRede, você terá direito a instalar o Trust Logo em seu website.

O Trust Logo Comodo é um selo de segurança dinâmico que informa ao seu usuário/visitante que o website está validado com o SSL Comodo. Este selo utiliza um _snippet_ de código _javascript_ que valida junto a Autoridade Certificadora seu SSL instalado.

## Instalação do Trust Logo Comodo

Para realizar a instalação do Trust Logo Comodo em seu website basta escolher o tamanho do selo que você deseja e copiar o código fornecido nas páginas em que desejar que seja exibido.
**Tamanhos disponíveis**: 76px x 26px, 100px x 85px e 113px x 59px
![Selo fundo transparente 76px por 26px](comodo_secure_seal_76x26_transp.png) ![](comodo_secure_seal_100x85_transp.png) ![](comodo_secure_seal_113x59_transp.png)

## Selos Trust Logo Comodo

### 76px por 26px

O _snippet_ de código abaixo fornece o selo Trust Logo Comodo nas dimensões de 76px de largura por 26px de altura:


**Adicione o código abaixo antes do fechamento da tag ```</HEAD>```**

```
<script type="text/javascript"> //<![CDATA[ 
var tlJsHost = ((window.location.protocol == "https:") ? "https://secure.comodo.com/" : "http://www.trustlogo.com/");
document.write(unescape("%3Cscript src='" + tlJsHost + "trustlogo/javascript/trustlogo.js' type='text/javascript'%3E%3C/script%3E"));
//]]>
</script>
```
**Adicione o código abaixo antes do fechamento da tag ```</BODY>```**

```
<script language="JavaScript" type="text/javascript">
TrustLogo("https://assets.eunarede.com/ssl/comodo/comodo_secure_seal_76x26_transp.png", "CL1", "none");
</script>
<a  href="https://www.positivessl.com/" id="comodoTL">Positive SSL</a>
```

### 100px por 85px

O _snippet_ de código abaixo fornece o selo Trust Logo Comodo nas dimensões de 100px de largura por 85px de altura:


**Adicione o código abaixo antes do fechamento da tag ```</HEAD>```**

```
<script type="text/javascript"> //<![CDATA[ 
var tlJsHost = ((window.location.protocol == "https:") ? "https://secure.comodo.com/" : "http://www.trustlogo.com/");
document.write(unescape("%3Cscript src='" + tlJsHost + "trustlogo/javascript/trustlogo.js' type='text/javascript'%3E%3C/script%3E"));
//]]>
</script>
```
**Adicione o código abaixo antes do fechamento da tag ```</BODY>```**

```
<script language="JavaScript" type="text/javascript">
TrustLogo("https://assets.eunarede.com/ssl/comodo/comodo_secure_seal_100x85_transp.png", "CL1", "none");
</script>
<a  href="https://www.positivessl.com/" id="comodoTL">Positive SSL</a>
```

### 113px por 59px

O _snippet_ de código abaixo fornece o selo Trust Logo Comodo nas dimensões de 113px de largura por 59px de altura:


**Adicione o código abaixo antes do fechamento da tag ```</HEAD>```**

```
<script type="text/javascript"> //<![CDATA[ 
var tlJsHost = ((window.location.protocol == "https:") ? "https://secure.comodo.com/" : "http://www.trustlogo.com/");
document.write(unescape("%3Cscript src='" + tlJsHost + "trustlogo/javascript/trustlogo.js' type='text/javascript'%3E%3C/script%3E"));
//]]>
</script>
```
**Adicione o código abaixo antes do fechamento da tag ```</BODY>```**

```
<script language="JavaScript" type="text/javascript">
TrustLogo("https://assets.eunarede.com/ssl/comodo/comodo_secure_seal_113x59_transp.png", "CL1", "none");
</script>
<a  href="https://www.positivessl.com/" id="comodoTL">Positive SSL</a>
```