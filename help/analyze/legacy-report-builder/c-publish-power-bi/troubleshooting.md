---
description: Problèmes courants rencontrés lors de l’utilisation de Report Builder avec Power BI.
title: Dépannage de l’intégration de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 40%

---

# Dépannage de l’intégration de Power BI

{{legacy-arb}}

Recherchez et résolvez les problèmes courants rencontrés lorsque vous utilisez Report Builder avec Power BI.

## Échec de la publication sur Power BI

Les classeurs planifiés qui nécessitent une publication Power BI dépendent de la disponibilité et de l’exécution des services Power BI. Deux raisons principales expliquent l’échec de la publication :

* Il se peut que les services Power BI soient en panne.
* L’utilisateur qui a planifié le classeur ne dispose plus d’informations d’identification de compte Microsoft valides.

Chaque tâche planifiée par le Report Builder bénéficie de trois tentatives par exécution planifiée :

* Après la première tentative infructueuse, vous recevrez le message suivant : « Nous n’avons pas pu publier ce classeur planifié sur Microsoft Power BI. Nous réessayerons dans quelques instants. »
* Après la deuxième tentative infructueuse, vous n’obtiendrez aucun message.
* Après la troisième tentative infructueuse, vous recevrez le message suivant : « Nous n’avons pas pu publier ce classeur sur Power BI. »

## Visualisations corrompues dans Power BI

Voici les principales raisons pour lesquelles vous pourriez obtenir des visualisations corrompues suite à la publication de requêtes du Report Builder sur Power BI :

* Vous avez modifié une requête dans le Report Builder, par exemple vous avez modifié des mesures ou des dimensions, puis vous l’avez à nouveau publiée sur Power BI. La modification des requêtes peut interrompre vos visualisations.
* Vous avez supprimé une requête qui était utilisée dans une visualisation.

>[!IMPORTANT]
>
>Report Builder requiert un administrateur pour autoriser l’accès aux ressources de votre organisation. Si vous avez besoin d’un accès, demandez à un administrateur de vous accorder l’autorisation.
> Un administrateur Microsoft peut consulter le paramètre *Les utilisateurs peuvent enregistrer l’application* disponible sous : **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Les paramètres utilisateur permettent d’activer les options]**. Si cette option est définie sur **Non**, l’administrateur peut enregistrer ces types d’applications.

Les utilisateurs peuvent accorder l&#39;accès en se connectant à leur compte Microsoft Power BI [&#128279;](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Les administrateurs peuvent accorder l’accès à chaque en se connectant à leur [compte Power BI Microsoft de l’administrateur](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Atteindre la limite d’API

La création de rapports dans Power BI fonctionne avec l’API de création de rapports d’Analytics. Des limites de seuil d’API s’appliquent donc.
