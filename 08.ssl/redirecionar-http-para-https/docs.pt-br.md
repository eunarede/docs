---
title: 'Redirecionar HTTP para HTTPS'
published: true
date: '12-09-2016 11:34'
publish_date: '12-09-2016 11:34'
taxonomy:
    category:
        - docs
    tag:
        - ssl
        - certificado
        - htaccess
    service:
        - ssl
visible: true
---

Adicione o códido abaixo para redirecionar os acessos do seu website em **HTTP** para **HTTPS** através de regra no arquivo ```.htaccess```

```
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R,L]
```

>>>> caso seu arquivo htaccess já possua configurações e/ou paramêtros de reescrita, insira este código ao final do arquivo existente.