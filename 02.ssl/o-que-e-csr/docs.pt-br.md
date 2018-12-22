---
title: 'O que é CSR?'
published: true
date: '11-08-2016 10:34'
publish_date: '11-08-2016 10:34'
taxonomy:
    category:
        - docs
    tag:
        - ssl
        - certificado
        - csr
    service:
        - ssl
visible: true
---

## O que é um CSR (Certificate Signing Request)?

CSR é a sigla de "_Certificate Signing Request_" (Requisição para Assinatura de Certificado), que é um arquivo de texto criptografado, gerado pelo servidor web do seu site, contendo as informações para a solicitação do seu Certificado Digital.

O CSR contém as informações da sua empresa (nome, departamento, cidade, estado, país) e a URL onde o certificado SSL será utilizado (Common Name). Caso não possua empresa e esteja comprando um certificado de validação rápida, informe o seu nome nos campos "Organization" e "Organizational Unit".

Ao gerar o CSR no seu servidor web utilize as seguintes informações:
* **Common name** (server domain name): domínio onde o certificado vai ser utilizado (ex: seudominio.com.br, sub.dominio.com.br).
* **Organization**: Nome oficial da empresa, igual ao existente no cartão do CNPJ.
* **Organizational Unit**: Departamento ou setor da empresa (ex: TI, Informática, Segurança da Informação).
* **City or Locality**: Cidade Sede da empresa.
* **State or Province**: Seu estado por extenso e sem abreviações ou caracters especiais (ex: ~~São~~ Sao Paulo).
* **Country**: País com 2 caracteres, **BR** para Brasil.

## Informações para a geração do CSR
* Ao gerar o CSR não utilize caracteres especiais, acentos e cedilha (" ' ! @ # $ % ¨ & * _ - + = § ¬ ¢ £ ³ ² ¹ ` ´ [ ] { } ( ) ª º ^ ~ ? / \ ; : . , < > |).
* Gere o CSR com uma chave de **4096 bits**, para que os navegadores utilizem uma **criptografia de até 256 bits**.
* Na geração do CSR, o seu servidor web cria um par de chaves: uma chave pública (CSR) e outra privada. Faça uma cópia de segurança do par de chaves em local seguro.
* Configure o ítem "Common Name" com a exata url onde o certificado vai ser utilizado. Por exemplo, se deseja utilizar o certificado em https://www.eunarede.com utilize como "Common Name" www.eunarede.com.
Lembre-se que www.eunarede.com é diferente de eunarede.com (sem o www).
* Depois de gerado, abra o arquivo CSR com um editor de texto simples, copie todo o conteúdo incluindo as linhas:
` "-----BEGIN NEW CERTIFICATE REQUEST----" e "-----END NEW CERTIFICATE REQUEST-----",`
 e cole no campo CSR do formulário de pedido do certificado.

>>> Os **certificados com WWW** poderão ser utilizados para validação do domínio **sem WWW**. Emita seu CSR do domínio **incluindo WWW.**, ex.: **www.**eunarede.com