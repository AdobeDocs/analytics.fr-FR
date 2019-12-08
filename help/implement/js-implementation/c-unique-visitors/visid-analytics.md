---
description: Lorsqu’un utilisateur visite votre site, un cookie persistant est défini par le serveur Web d’Adobe en l’incluant dans la réponse HTTP au navigateur. Ce cookie est défini sur le domaine de collecte de données spécifié.
keywords: Analytics Implementation
title: Identifiant visiteur Analytics
topic: Developer and implementation
uuid: fa7737cc-0190-4d27-af1b-87301a715df2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Identifiant visiteur Analytics

Lorsqu’un utilisateur visite votre site, un cookie persistant est défini par le serveur Web d’Adobe en l’incluant dans la réponse HTTP au navigateur. Ce cookie est défini sur le domaine de collecte de données spécifié.

Lors de l’envoi d’une demande au serveur de collecte de données d’Adobe, le cookie de l’identifiant visiteur `s_vi` est recherché dans l’en-tête. S’il est présent dans la demande, il est utilisé pour identifier le visiteur. Dans le cas contraire, le serveur génère un identifiant visiteur unique, le définit comme cookie dans l’en-tête de réponse HTTP, puis le renvoie avec la demande. Le cookie est stocké dans le navigateur et renvoyé au serveur de collecte de données lors des visites ultérieures, ce qui permet d’identifier le visiteur au cours de différentes visites.

## Cookies tiers et enregistrements CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Certains navigateurs, comme Apple Safari, ne stockent plus les cookies définis dans l’en-tête HTTP provenant de domaines qui ne correspondent pas au domaine du site Web actuel (il s’agit d’un cookie utilisé dans un contexte tiers ou d’un cookie tiers). Supposons que vous visitiez le site `mysite.com` et que votre serveur de collecte de données soit `mysite.omtrdc.net`. Dans ce cas, le cookie renvoyé dans l’en-tête HTTP en provenance de `mysite.omtrdc.net` risque d’être rejeté par le navigateur.

Pour éviter ce cas de figure, de nombreux clients ont implémenté des enregistrements CNAME pour leurs serveurs de collecte de données dans le cadre d’une [implémentation de cookies propriétaires](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). Si un enregistrement CNAME est configuré pour associer un nom d’hôte sur le domaine du client au serveur de collecte de données (mappage de `metrics.mysite.com` sur `mysite.omtrdc.net`, par exemple), le cookie Identifiant visiteur est stocké, étant donné que le domaine de collecte de données correspond désormais à celui du site Web. Cela a pour effet d’augmenter la probabilité de stockage du cookie Identifiant visiteur. Cependant, cette méthode s’accompagne d’une surcharge de travail, dans la mesure où vous devez configurer des enregistrements CNAME et gérer des certificats SSL pour les serveurs de collecte de données.

## Cookies sur les périphériques mobiles {#section_7D05AE259E024F73A95C48BD1E419851}

Lorsque vous effectuez le suivi des périphériques mobiles à l’aide de cookies, vous pouvez utiliser certains paramètres pour modifier le mode d’exécution des mesures. La durée de vie par défaut d’un cookie est de 5 ans, mais vous pouvez utiliser la variable de paramètre de requête CL (`s.cookieLifetime`) pour la modifier. Pour définir l’emplacement du cookie pour les implémentations cname, utilisez la chaîne de requête CDP `s.cookieDomainPeriods`. Si aucune valeur n’est spécifiée, le paramètre par défaut est 2 et l’emplacement par défaut est domain.com. Dans le cas des implémentations qui n’utilisent pas CNAME, l’emplacement du cookie Identifiant visiteur est le domaine 207.net.
