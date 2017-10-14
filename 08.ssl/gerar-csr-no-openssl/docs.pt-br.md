---
title: 'Gerar CSR no OpenSSL'
published: true
date: '03-10-2016 10:53'
publish_date: '03-10-2016 10:53'
metadata:
    description: 'Como gerar o arquivo CSR no OpenSSL'
taxonomy:
    category:
        - docs
    tag:
        - ssl
        - openssl
        - csr
    service:
        - ssl
visible: true
---

Este artigo mostra como criar uma **Solicitação de Assinatura de Certificado (_CSR_)** para um Certificado SSL através do **OpenSSL**

## Instalando o OpenSSL

Para a geração da **Solicitação de Assinatura de Certificado (_CSR_)** é necessário a instalação do OpenSSL. Caso seu servidor já tenha-o instalado, pule para a etapa **Gerar o Arquivo CSR**.

### CentOS/Red Hat

Para verificar se o OpenSSL está instalado em um sistema que usa o ```yum``` (como distribuições CentOS ou Red Hat Enterprise Linux), execute o seguinte comando.

``` ssh
rpm -qa | grep -i openssl
```
O comando acima deverá retornar os pacotes similares como abaixo:
```ssh
openssl-1.0.1e-48.el6_8.1.x86_64
openssl-devel-1.0.1e-48.el6_8.1.x86_64
openssl-1.0.1e-48.el6_8.1.i686
```
Se não for retornado nenhum nome de pacote no prompt, instale o OpenSSL executando o seguinte comando:
```ssh 
yum install openssl openssl-devel
```

### Debian/Ubuntu

Para verificar se OpenSSL está instalado em um sistema Debian ou Ubuntu, execute o seguinte comando:

```ssh
dpkg -l |grep openssl
```
Você deve receber a seguinte saída.
```ssh
ii  libgnutls-openssl27:amd64           2.12.23-12ubuntu2.4              amd64        GNU TLS library - OpenSSL wrapper
ii  openssl                             1.0.1f-1ubuntu2.16               amd64        Secure Sockets Layer toolkit - cryptographic utility
```
Se você não ver a saída esperada, instale OpenSSL executando o seguinte comando:
```ssh
apt-get install openssl
```
## Gerar a chave RSA
Execute os seguintes comandos para criar um diretório no qual deseja armazenar a sua chave RSA, substitua o nome de diretório de sua escolha:
``` ssh
mkdir ~/dominio.com.ssl/
cd ~/dominio.com.ssl/
```
Execute o seguinte comando para gerar uma chave privada:
```ssh
openssl genrsa -out ~/dominio.com.ssl/dominio.com.key 2048
```
!!! Recomendamos a geração de chaves 4096 para maior nível de segurança
## Criar o CSR
Digite o seguinte comando para criar um CSR com a chave privada RSA (saída está no formato PEM):
```ssh
openssl req -new -sha256 -key ~/dominio.com.ssl/dominio.com.key -out ~/dominio.com.ssl/dominio.com.csr
```
Quando solicitado, digite as informações necessárias para a criação de um CSR usando as convenções mostradas na tabela a seguir.

| Campo | Explicação | Exemplo |
| ----- | ---------- | ------- |
| Common Name | O nome de domínio totalmente qualificado para o seu servidor web. Este deve ser uma correspondência exata. | Se você pretende garantir a URL https://www.dominio.com, em seguida, nome comum do seu CSR deve ser www.dominio.com. Se você pretende obter um certificado Wild Card, certifique-se de prefixar o seu nome de domínio com um asterisco, por exemplo: \*\.dominio.com.|
| Organization Name | O nome legal de sua organização (Razão Social). **Não abrevie o nome da organização**. **Não utilize acentuação especial** | EunaRede The Hosting Company Servicos de Internet Ltda |
| Organizational Unit | Seção/Setor da organização. | TI |
| City or Locality | A cidade onde sua organização está legalmente localizado. | Curitiba |
| State or Province | O estado ou província em que a sua organização está legalmente localizado. Não use abreviação. | Parana |
| Country | A abreviatura ISO de duas letras para o seu país. | BR |
| Email Address | Endereço de e-mail do contato técnico | webmaster@dominio.com |

!! Deixe o campo challenge password em branco (pressione Enter)

## Verificando o CSR
Execute o seguinte comando para verificar o seu CSR:
```ssh
openssl req -noout -text -in ~/dominio.com.ssl/dominio.com.csr
```
## Enviando o CSR
Submeta o CSR que você criou no Painel de Controle para dar inicio ao processo de emissão do SSL.