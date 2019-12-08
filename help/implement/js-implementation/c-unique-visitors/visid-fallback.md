---
description: Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.
keywords: Analytics Implementation
title: Méthodes d’identifiant de secours
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Méthodes d’identifiant de secours

Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.

## Méthode d’identification des visiteurs de secours {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). Auparavant, lorsqu’un cookie ne pouvait pas être défini, les utilisateurs étaient identifiés à l’aide d’une combinaison de l’adresse IP et de la chaîne de l’agent utilisateur lors de la collecte des données.

Avec cette mise à jour, si le cookie `s_vi` standard n’est pas disponible, un cookie de secours est créé sur le domaine du site Web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé `s_fid`, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours. Cette modification devrait entraîner une exactitude accrue de la comptabilisation des visites et des visiteurs dans les cas où le cookie principal (`AMCV_` ou `s_vi`) ne peut pas être défini.

Le total des visites inclut tous les visiteurs qui sont identifiés par le cookie `s_vi` ou à l’aide d’une méthode de secours.

## Adresse IP, Agent utilisateur, Adresse IP de passerelle {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si les cookies `AMCV_`, `s_vi` ou `s_fid` ne peuvent pas être définis, les visiteurs sont identifiés à l’aide d’une combinaison de l’adresse IP et de l’agent utilisateur.
