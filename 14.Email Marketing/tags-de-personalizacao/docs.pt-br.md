---
title: 'Tags de Personalização'
published: true
date: '10-05-2017 14:08'
publish_date: '10-05-2017 14:08'
taxonomy:
    category:
        - docs
    tag:
        - email
        - marketing
    service:
        - email-marketing
visible: true
---

Use as tags a seguir em seu assunto, texto simples ou código HTML, e elas serão automaticamente formatadas quando a sua campanha for enviada. Quanto às tags de "versão web" e "cancelamento de assinatura", você pode estilizá-las usando CSS inline.

## Tags essenciais (apenas HTML)

As tags a seguir podem ser usadas **apenas na versão HTML**.

#### Link para a versão web

````<webversion>Ver a versão para web</webversion>````

#### Link de cancelamento de assinatura

````<unsubscribe>Cancele sua assinatura aqui</unsubscribe>````

## Tags essenciais (Texto e HTML)

As tags a seguir podem ser usadas tanto no **texto simples** quando na versão **HTML**.

#### Link para a versão web 

````[webversion]````

#### Link de cancelamento de assinatura

````[unsubscribe]````


## Tags de personalização

As tags a seguir podem ser usadas tanto no texto simples quando na versão HTML.

#### Nome 

````[Name,fallback=]````

#### E-mail 

````[Email]````

#### Dia do mês com dois dígitos

(ex. 01 a 31)

````[currentdaynumber]````

#### Representção textual do dia 

(ex. Sexta-feira)

````[currentday]````

#### Representação do mês com dois dígitos 

(ex. 01 a 12)

````[currentmonthnumber]````

#### Nome do mês completo 

(ex. Maio)

````[currentmonth]````

#### Representação do ano com quatro dígitos 

(ex. 2014)

````[currentyear]````


## Tags de campos personalizados

Você também pode usar campos personalizados para personalizar a sua newsletter, ex.: 

````[Country,fallback=Qualquer lugar do Mundo].````

Para gerenciar ou ter uma referência das tags para os campos personalizados, entre em qualquer lista de assinantes. Depois, clique no botão 'Campos personalizados' no topo, à direita.