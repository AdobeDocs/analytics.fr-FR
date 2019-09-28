---
description: valeur nulle
keywords: Flux de données;tâche;visiteurs;Experience Cloud ID;identifiant visiteur analytics;identifier
seo-description: valeur nulle
seo-title: Identification des visiteurs
solution: Analytics
title: Identification des visiteurs
topic: Reports & Analytics
uuid: 2490b67e-a333-422d-82fa-cb0670ef2e0c
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Identification des visiteurs

Analytics fournit plusieurs mécanismes permettant d’identifier les visiteurs (répertoriés dans [Identification des visiteurs](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**Pour identifier des visiteurs uniques, procédez comme suit :**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5, 8 et 9 sont des lignes récapitulatives téléchargées à l’aide de sources de données. 7 représente les téléchargements de source de données d’identifiant de transaction qui ne doivent pas être inclus dans les comptes de visites et de visiteurs. Reportez-vous à la section [Recherche de sources d’accès](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combinez `post_visid_high` avec `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

Pour déterminer quel mécanisme a été appliqué pour isoler la valeur de l’identifiant visiteur (par exemple, pour calculer l’acceptation des cookies), `post_visid_type` comprend une clé de recherche qui indique quelle méthode d’identification a été utilisée. Les clés de recherche sont répertoriées avec les mécanismes d’identification des visiteurs dans le [tableau ci-dessous](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

L’Experience Cloud ID est reporté dans une colonne distincte, `mcvisid`. Pour cette raison, il n’est pas toujours facile de savoir si Analytics utilise cet identifiant ou un autre identifiant pour identifier un visiteur.

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. Ces champs sont les seuls champs d’identifiant visiteur ayant une valeur sur chaque ligne dans le flux de données.

## Identifiants visiteur Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Il existe plusieurs moyens d’identifier un visiteur dans Analytics (répertoriés dans le tableau ci-dessous par ordre de préférence) :

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Valeur de colonne post_visid_type | Présent quand |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) | 0 | s.visitorID est défini. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_analytics.html) | 3 | Le visiteur avait un cookie s_vi existant avant le déploiement du service d’identification des visiteurs ou vous avez configuré une [période de grâce](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html) d’identification des visiteurs. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ défini par Identity Service)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | Visitor's browser accepts cookies (first-party), and the Identity Service is deployed. |
| ![](assets/step4_icon.png) | [fid (cookie de reprise sur H.25.3 ou plus récent ou AppMeasurement pour JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 4 | Le navigateur du visiteur accepte les cookies (propriétaires). |
| ![](assets/step5_icon.png) | [En-tête des abonnées mobiles HTTP](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_mobile.html) | 2 | Le périphérique est reconnu comme un appareil mobile. |
| ![](assets/step6_icon.png) | [Adresse IP, Agent utilisateur, Adresse IP de passerelle](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 1 | Le navigateur du visiteur n’accepte pas les cookies. |

Dans de nombreux scénarios, il se peut qu’il y ait 2 ou 3 identifiants distincts pour un appel ; Analytics utilisera comme identifiant visiteur officiel le premier identifiant présent de cette liste et répartira cette valeur dans les colonnes `post_visid_high` et `post_visid_low`. Par exemple, si vous définissez un identifiant visiteur personnalisé (y compris dans le paramètre de requête « vid »), cet identifiant sera utilisé avant les autres identifiants susceptibles d’être présents pour ce même accès.
