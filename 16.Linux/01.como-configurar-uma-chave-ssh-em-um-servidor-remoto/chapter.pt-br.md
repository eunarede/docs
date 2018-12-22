---
title: 'Como Configurar uma chave SSH em um Servidor Remoto'
date: '16-08-2018 10:45'
taxonomy:
    category:
        - segurança
        - 'linux básico'
        - linux
    tag:
        - linux
        - segurança
        - ssh
        - 'configurar ssh'
        - 'segurança servidor'
---

## 1 - Criar o par de chaves RSA

O primeiro passo é criar o par de chaves na máquina do cliente (há uma boa chance de que este seja apenas o seu computador):

```bash
ssh-keygen -t rsa
```

## 2 - Armazenar as chaves e senha

Depois de inserir o comando Gen Key, você receberá mais algumas perguntas:

```bash
Enter file in which to save the key (/home/demo/.ssh/id_rsa):
```
Você pode pressionar _enter_ aqui, salvando o arquivo na home do usuário (nesse caso, meu usuário de exemplo é chamado demo).

```bash
Enter passphrase (empty for no passphrase):
```
Cabe a você se você quer usar uma frase secreta. Inserir uma senha tem seus benefícios: a segurança de uma chave, não importa o quanto criptografada, ainda depende do fato de que ela não é visível para ninguém. Se uma chave privada protegida por frase secreta cair em uma posse não autorizada de usuários, eles não conseguirão fazer login em suas contas associadas até descobrirem a frase secreta, o que levará algum tempo extra ao usuário hackeado. A única desvantagem, é claro, de ter uma frase secreta, é então digitar cada vez que você usar o par de chaves.

The entire key generation process looks like this:

```bash
ssh-keygen -t rsa
```
```bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/demo/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/demo/.ssh/id_rsa.
Your public key has been saved in /home/demo/.ssh/id_rsa.pub.
The key fingerprint is:
4a:dd:0a:c6:35:4e:3f:ed:27:38:8c:74:44:4d:93:67 demo@a
The key's randomart image is:
+--[ RSA 2048]----+
|          .oo.   |
|         .  o.E  |
|        + .  o   |
|     . = = .     |
|      = S = .    |
|     o + = +     |
|      . o + o .  |
|           . o   |
|                 |
+-----------------+
```

## 3 - Copiando a chave pública para o servidor remoto

Quando o par de chaves é gerado, é hora de colocar a chave pública no servidor que queremos usar.

```bash
cat ~/.ssh/id_rsa.pub | ssh demo@198.51.100.0 "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >>  ~/.ssh/authorized_keys"
```