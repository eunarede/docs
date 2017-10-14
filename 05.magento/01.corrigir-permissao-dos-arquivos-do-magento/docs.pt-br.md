---
title: 'Corrigir Permissão dos Arquivos do Magento'
published: true
date: '28-06-2016 00:00'
publish_date: '28-06-2016 00:00'
external_links:
    process: true
    title: true
    no_follow: true
    mode: active
    target: _blank
taxonomy:
    service:
        - hospedagem
    tag:
        - magento
        - permissao
        - arquivos
    category:
        - docs
---

Quando há mudanças ou migração do Magento de um servidor ou provedor de hospedagem para outro, as permissões dos arquivos do Magento podem sofrer alterações em suas configurações.

===

O problema mais comum é a alteração das permissões de escrita e de leitura nos diretórios e arquivos do Magento. O Magento possuí uma estrutura de permissões de arquivos e diretórios rígida para sua segurança.

Resetar as permissões dos arquivos e diretórios é bem simples através do `SSH` já que com apenas duas linhas de comando iremos ordernar a alteração recursiva de arquivos e diretórios.

! Caso você não saiba se possui acesso SSH em sua hospedagem na EunaRede, por favor, contate nosso time de suporte.

### Corrigindo Permissão de Arquivos

Acesse através do terminal `SSH` o diretório raiz do Magento, exemplo:

    cd /home/usuario/public_html/magento

Então execute os seguintes comandos:

    find . -type f -exec chmod 644 {} \;
    find . -type d -exec chmod 755 {} \;

O comando `find . -type f -exec chmod 644 {} \;` busca recursivamente todos os arquivos presentes no diretório raiz do Magento e diretórios adjacentes e altera a permissão para `644`.

Já o comando `find . -type d -exec chmod 755 {} \;` altera a permissão de cada diretório para `775`