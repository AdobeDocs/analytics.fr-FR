---
title: Identification des visiteurs à l’aide de l’extension de balise Adobe Analytics
description: Identifier correctement les visiteurs lors de l’implémentation de l’extension de balise Adobe Analytics.
exl-id: de534c69-0f43-45eb-86da-20d3cd3f363d
TQID: https://experienceleague.adobe.com/bdm2phkscnH9bSiQqK9K--ySTLguGaf-WLgEc3TL6H8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 2%

---

# Identification des visiteurs à l’aide de l’extension de balise Adobe Analytics

L’extension de balises Adobe Analytics vous permet de mettre en œuvre AppMeasurement à l’aide d’une interface de gestion des balises. Comme cette extension de balise est essentiellement AppMeasurement, elle offre des méthodes similaires pour identifier les visiteurs et nécessite une extension de balise distincte pour le service d’identification des visiteurs.

## Identification des visiteurs à l’aide du service d’identification des visiteurs (recommandé)

Pour utiliser le service d’identification des visiteurs à l’aide de l’extension de balise Adobe Analytics, incluez l’extension du service d’identification Experience Cloud dans votre propriété de balise.

1. Connectez-vous à [Adobe CX Enterprise](https://experience.adobe.com) à l’aide de vos informations d’identification Adobe ID.
1. Accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.
1. Recherchez la propriété de balise de votre choix.
1. Accédez à **[!UICONTROL Extensions]**, puis sélectionnez l’onglet **[!UICONTROL Catalogue]**.
1. Recherchez l’extension **[!UICONTROL Experience Cloud ID Service]**, puis sélectionnez **[!UICONTROL Installer]**.

L’extension de balise obtient automatiquement votre identifiant d’organisation IMS. Aucune configuration supplémentaire n’est donc nécessaire.

## Identification des visiteurs à l’aide du cookie `s_vi` (déconseillé)

>[!IMPORTANT]
>
>Adobe déconseille d&#39;utiliser cette méthode pour identifier les visiteurs.

Si votre organisation n’utilise pas l’extension de balise du service d’identification des visiteurs, l’extension de balise Adobe Analytics utilise sa propre forme d’identification des visiteurs. Lorsqu’un visiteur ou une visiteuse arrive sur votre site pour la première fois, l’extension recherche un cookie [`s_vi`](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/cookies/analytics). Ce cookie est défini sur le domaine correspondant à **[!UICONTROL Serveur de suivi SSL]** (pour HTTPS) ou **[!UICONTROL Serveur de suivi]** (pour HTTP) lors de la [configuration de l’extension de balise](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/analytics/overview).

* Si vous participez au [programme de certificat géré](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/adobe-managed-cert), votre serveur de suivi est généralement un domaine propriétaire, ce qui rend les cookies `s_vi` propriétaires.
* Si vous ne participez pas au programme de certificat géré, le serveur de suivi est généralement un sous-domaine de `adobedc.net`, `omtrdc.net` ou `2o7.net`, ce qui fait du cookie `s_vi` un cookie tiers. En raison des normes modernes de confidentialité des navigateurs, les cookies tiers sont rejetés par la plupart des navigateurs. Une fois rejeté, AppMeasurement tente de définir un cookie de secours propriétaire (`fid`) à la place.

Si vous définissez correctement [!UICONTROL Serveur de suivi SSL], aucune autre mesure d’identification des visiteurs n’est requise.

## Identification des visiteurs à l’aide de `visitorID` (déconseillé)

>[!IMPORTANT]
>
>Adobe déconseille d&#39;utiliser cette méthode pour identifier les visiteurs.

L’utilisation de la variable **[!UICONTROL Identifiant visiteur]** permet à votre entreprise d’effectuer un contrôle indépendant pour identifier les visiteurs. Si vous définissez [!UICONTROL Identifiant visiteur] à l’aide d’un élément de données, notez les restrictions suivantes :

* Chaque accès doit contenir la même valeur [!UICONTROL identifiant visiteur] pour être comptabilisé comme un seul visiteur.
   * Tous les accès qui omettent l’élément de données [!UICONTROL Identifiant visiteur] tentent automatiquement d’utiliser une autre méthode d’identification des visiteurs, en les traitant comme un visiteur distinct.
   * Tous les accès contenant une valeur [!UICONTROL identifiant visiteur] différente d’un accès précédent sont traités comme un visiteur distinct.
   * Adobe ne permet pas d’assembler des accès à l’aide de différents identifiants visiteur dans Adobe Analytics.
* Les audiences partagées, Analytics for Target et les attributs du client ne sont pas pris en charge avec les visiteurs identifiés à l’aide de l’[!UICONTROL identifiant visiteur].

Voir [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour obtenir des instructions d’implémentation à l’aide de cette variable.
