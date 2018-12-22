---
title: 'WHMCS Iugu Cartão PRO'
published: true
date: '05-01-2018 00:36'
publish_date: '05-01-2018 00:37'
taxonomy:
    category:
        - docs
    tag:
        - whmcs
        - iugu
        - modulo
    service:
        - app
external_links:
    process: true
    no_follow: true
visible: true
recaptchacontact:
    enabled: false
---

Realize transações por cartão de crédito de forma transparente com o módulo [WHMCS] Iugu Cartão PRO.

O Módulo WHMCS Iugu Cartão PRO é um módulo de pagamento para o intermediador [Iugu] que possibilita a utilização do método de pagamento por cartão de crédito de forma transparente dentro do [WHMCS].

Aprimore a experiência de compra do seu cliente no WHMCS com o Iugu Cartão PRO. Com este módulo seus clientes realizarão o pagamento através de cartão de crédito de forma transparente e sem redirecionamento.

Além do pagamento transparente, tenha em mãos todo o poder da recorrência de pagamentos do [WHMCS] integrada com a Iugu. O módulo WHMCS Iugu Cartão PRO possibilita a realização de cobrança recorrente automática no cartão de crédito diretamente através do [WHMCS]. Receba as faturas em dia e conte com todo o poder e flexibilidade de faturamento e captura que o [WHMCS] dispõe integrada a sua conta Iugu.

## Principais Recursos

O Módulo WHMCS Iugu Cartão PRO dispões dos seguintes recursos:

* Pagamento transparente por cartão de crédito, sem redirecionamento do cliente;
* Integração completa com os recursos nativos de captura de cartão de crédito do WHMCS;
* Sem necessidade de modificações no tema;
* Tokenização do cartão de crédito (DDS PCI Compliance);
* Captura remota automática de faturas em sua data de vencimento;
* Notificação de expiração do cartão de crédito;
* Modificação e atualização do cartão de crédito (pela area do cliente e também pela area administrativa);
* Atualização de token quando cartão de crédito é atualizado;
* Chargeback de faturas reembolsadas (_em breve_);
* Reembolso automático da cobrança no reembolso do(s) produto(s)/serviço(s) (_em breve_);
* Cobrança de cartões de créditos internacionais (_em breve_);


## Recursos Adicionais

* Sincronização dos dados do cliente WHMCS na Iugu para armazenamento e gestão dos pagamentos e formas de pagamento;
* Atualização de dados cadastrais do cliente WHMCS para a Iugu;
* Sincronizar dados dos clientes já existentes no WHMCS para a Iugu;
* Ativação do modo _sandbox_ para testes de integração;
* Habilitar utilização de cartões de crédito de teste (modo _sandbox_);

### Pagamentos Transparentes

Com o módulo WHMCS Iugu Cartão PRO você poderá fornecer uma melhor experiência de compra ao seu cliente, diminuindo as etapas e redirecionamentos necessários para a conclusão do pedido. Seu cliente terá o pagamento aprovado imediatamente após a conclusão do pedido, de forma simples e transparente.

![Finalização do Pagamento com Cartão de Crédito](https://assets.eunarede.net/products/whmcs/iugu/cartao/insercao-cc-clientarea.gif)

### Captura Automática de Faturas

Capture as faturas dos clientes automaticamente através do recurso de captura remota do WHMCS. O módulo WHMCS Iugu Cartão PRO habilita a captura automática dos valores de faturas/faturamento de forma transparente para clientes que tenham optado pelo pagamento via cartão de crédito. A captura é realizada de duas formas: no momento da chamada da CRON de tarefas do WHMCS, capturando faturas que estão dentro da data de vencimento e captura manual através da interface do administrador.

[plugin:youtube](https://youtu.be/WzmhsbJRqV0)


### Atualização do Cartão de Crédito

O Módulo WHMCS Iugu Cartão PRO utiliza-se de todo o poder do WHMCS na gestão de dados do cartão de crédito. Como ele, é possível seu cliente atualizar os dados do cartão de forma simples pela área do cliente ou mesmo o administrador, acessando o perfil do usuário.

> em nenhum momento será possível visualizar ou recuperar os dados reais do cartão de crédito graças ao recurso de [tokenização](tokens).

![Atualização do cartão](https://raw.githubusercontent.com/wiki/eunarede/iugu-whmcs-pro/imgs/giphy.gif)

### Segurança, Tokenização e _Compliance_

O Módulo WHMCS Iugu Cartão PRO foi desenvolvido seguindo as regras e normativas para armazenagem de dados sensíveis de cartão de crédito _PCI-DSS_. O módulo se baseia no recurso de [tokenização](tokens) disponível na Iugu para a geração de um token único não identificável e criptografado no momento da inserção dos dados do cartão pelo cliente.

> A tokenização permite a utilização dos dados do cartão do portador de forma segura e compliant com as normas do PCI-DSS. O conceito básico consiste em enviar os dados do cartão do cliente diretamente do browser dele para a iugu e então receber de volta um código (token) que representa o cartão em questão.

![Tokenização do Cartão de Crédito](https://assets.eunarede.net/products/whmcs/iugu/imagens/iugu-whmcs-cartao-diagrama-token.png)

### Sincronização e atualização de dados cadastrais

Além de contar com os recursos de cobrança transparente do cartão de crédito, o Módulo WHMCS Iugu Cartão PRO conta com a funcionalidade de cadastramento e sincronização dos dados do cliente do WHMCS diretamente na plataforma Iugu, possibilitando a gestão de faturas e pagamentos emitidos de forma simples e automatizada.

![Sincronização dos Dados de Cliente](https://assets.eunarede.net/products/whmcs/iugu/cartao/sincronizando-cliente-whmcs.gif)

Assista um video demonstrando as funcionalidades do módulo cartão de crédito:

[plugin:youtube](https://youtu.be/UT5ZHAKBWkQ)

[EunaRede]: https://www.eunarede.com
[Iugu]: https://iugu.com
[WHMCS]: https://www.whmcs.com/members/aff.php?aff=4571
[tokens]: https://dev.iugu.com/docs/tokenizacao
