---
description: Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.
keywords: Mise en œuvre d’Analytics
seo-description: Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.
seo-title: Méthodes d’identifiant de secours
solution: Analytics
title: Méthodes d’identifiant de secours
topic: Développeur et mise en œuvre
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Méthodes d’identifiant de secours

Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.

## Méthode d’identification des visiteurs de secours {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement pour JavaScript 1.x et JavaScript H.25.3 (publié en janvier 2013) contient une nouvelle méthode d’identification des visiteurs de secours destinée aux visiteurs dont le navigateur bloque le cookie défini par les serveurs de collecte d’Adobe (appelé `s_vi`). Auparavant, lorsqu’un cookie ne pouvait pas être défini, les utilisateurs étaient identifiés à l’aide d’une combinaison de l’adresse IP et de la chaîne de l’agent utilisateur lors de la collecte des données.

Avec cette mise à jour, si le cookie `s_vi` standard n’est pas disponible, un cookie de secours est créé sur le domaine du site Web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé `s_fid`, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours. Cette modification devrait entraîner une exactitude accrue de la comptabilisation des visites et des visiteurs dans les cas où le cookie principal (`AMCV_` ou `s_vi`) ne peut pas être défini.

Le total des visites inclut tous les visiteurs qui sont identifiés par le cookie `s_vi` ou à l’aide d’une méthode de secours.

## Adresse IP, Agent utilisateur, Adresse IP de passerelle {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si les cookies `AMCV_`, `s_vi` ou `s_fid` ne peuvent pas être définis, les visiteurs sont identifiés à l’aide d’une combinaison de l’adresse IP et de l’agent utilisateur.
