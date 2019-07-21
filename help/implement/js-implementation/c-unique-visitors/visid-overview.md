---
description: Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.
keywords: Mise en œuvre d’Analytics
seo-description: Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.
seo-title: Identifier les visiteurs uniques
solution: Analytics
subtopic: Visiteurs
title: Identifier les visiteurs uniques
topic: Développeur et mise en œuvre
uuid: ed 4 dee 75-ecfb -4715-8122-461983 c 7 dd 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identifier les visiteurs uniques

Adobe utilise un cookie pour effectuer le suivi des navigateurs/périphériques uniques.

## Classement des identifiants visiteur Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics fournit plusieurs mécanismes permettant d’identifier les visiteurs, répertoriés dans le tableau suivant par ordre de préférence :

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présent quand |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | s.visitorID est défini. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | Le visiteur avait un cookie s_vi existant avant le déploiement du service d’identification des visiteurs ou vous avez configuré une période de grâce d’identification des visiteurs. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ défini par le service d’identification des visiteurs d’Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| ![](assets/step4_icon.png) | [fid (cookie de secours sur H.25.3 ou plus récent ou AppMeasurement pour JavaScript)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| ![](assets/step5_icon.png) | [Adresse IP, Agent utilisateur, Adresse IP de passerelle](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | Le navigateur du visiteur n’accepte pas les cookies. |

Dans de nombreux scénarios, il se peut qu’il y ait 2 ou 3 identifiants distincts pour un appel ; Analytics utilisera comme identifiant visiteur officiel le premier identifiant présent de cette liste. Par exemple, si vous définissez un identifiant visiteur personnalisé (y compris dans le paramètre de requête « vid »), cet identifiant sera utilisé avant les autres identifiants susceptibles d’être présents pour ce même accès.

>[!NOTE]
>
>Chaque identifiant visiteur Analytics est associé à un profil visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.
