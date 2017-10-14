---
title: 'O que é um Certificado de Comunicações Unificadas (UCC)?'
published: true
date: '06-10-2016 19:02'
publish_date: '06-10-2016 19:02'
taxonomy:
    category:
        - docs
    tag:
        - ssl
        - certificado
    service:
        - ssl
visible: true
---

Um UCC (Unified Communications Certificate, Certificado de comunicações unificadas) é um certificado SSL que protege vários nomes de domínio e vários nomes de host em um nome de domínio. Um SSL UCC permite que você proteja um nome de domínio principal e até 99 SANs (Subject Alternative Names, Nomes alternativos de assunto) adicionais em um único SSL. Por exemplo, você pode usar um UCC para proteger www.domains1.com, www.domains2.net e www.domains3.org.

UCCs são compatíveis com hospedagem compartilhada e ideais para Microsoft® Exchange Server 2007, Exchange Server 2010, e Microsoft Live® Communications Server. UCCs são compatíveis com hospedagem compartilhada. No entanto, as informações de "emissão para" de selo e certificado do site relacionarão somente o nome de domínio principal. Observe que qualquer conta de hospedagem secundária será relacionada no certificado também; caso você não queira que sites apareçam como "conectados" entre si, você não deve usar esse tipo de certificado.