---
description: Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.
keywords: Analytics Implementation
subtopic: Visitors
title: Identification des visiteurs uniques
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Identification des visiteurs uniques

Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.

## Classement des identifiants visiteur Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics fournit plusieurs mécanismes permettant d’identifier les visiteurs, répertoriés dans le tableau suivant par ordre de préférence :

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présent quand |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](/help/implement/js-implementation/c-unique-visitors/visid-custom.md) | s.visitorID est défini. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](/help/implement/js-implementation/c-unique-visitors/visid-analytics.md) | Le visiteur avait un cookie s_vi existant avant le déploiement du service d’identification des visiteurs ou vous avez configuré une période de grâce d’identification des visiteurs. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ défini par le service d’identification des visiteurs d’Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| ![](assets/step4_icon.png) | [fid (cookie de secours sur H.25.3 ou plus récent ou AppMeasurement pour JavaScript)](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| ![](assets/step5_icon.png) | [Adresse IP, Agent utilisateur, Adresse IP de passerelle](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | Le navigateur du visiteur n’accepte pas les cookies. |

Dans de nombreux scénarios, il se peut qu’il y ait 2 ou 3 identifiants distincts pour un appel ; Analytics utilisera comme identifiant visiteur officiel le premier identifiant présent de cette liste. Par exemple, si vous définissez un identifiant visiteur personnalisé (y compris dans le paramètre de requête « vid »), cet identifiant sera utilisé avant les autres identifiants susceptibles d’être présents pour ce même accès.

> [!NOTE] Chaque identifiant visiteur Analytics est associé à un profil du visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.
