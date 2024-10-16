---
description: Problèmes courants rencontrés lors de l’utilisation de Report Builder avec Power BI.
title: Dépannage de l’intégration de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 64%

---

# Dépannage de l’intégration de Power BI

Recherchez et résolvez les problèmes courants rencontrés lorsque vous utilisez Report Builder avec Power BI.

## Échec de la publication sur Power BI

Les classeurs planifiés qui nécessitent une publication sur Power BI dépendent du bon fonctionnement des services Power BI. Les deux principales raisons d’un échec de publication sont :

* Les services Power BI sont peut-être arrêtés.
* L’utilisateur qui a planifié le classeur ne dispose plus d’Informations d’identification valides pour son compte Microsoft.

Chaque tâche planifiée par le Report Builder bénéficie de trois tentatives par exécution planifiée :

* Après l’échec de la première tentative, vous obtenez le message suivant : « Nous n’avons pas pu publier ce classeur planifié sur Microsoft Power BI. Une nouvelle tentative sera effectuée prochainement. »
* Après l’échec de la deuxième tentative, vous n’obtenez aucun message.
* Après l’échec de la troisième tentative, vous obtenez le message suivant : « Nous n’avons pas pu publier ce classeur planifié sur Microsoft Power BI. »

## Visualisations corrompues dans Power BI

Voici les principales raisons pour lesquelles vous pourriez obtenir des visualisations corrompues suite à la publication de requêtes du Report Builder sur Power BI :

* Vous avez modifié une requête dans le Report Builder, par exemple vous avez modifié des mesures ou des dimensions, puis vous l’avez à nouveau publiée sur Power BI. La modification des requêtes peut entraîner la corruption de vos visualisations.
* Vous avez supprimé une requête qui était utilisée dans une visualisation.

>[!IMPORTANT]
>
>Report Builder nécessite qu’un administrateur autorise l’accès aux ressources de votre organisation. Si vous avez besoin d’un accès, demandez à un administrateur de vous accorder cette autorisation.
> Un administrateur Microsoft peut consulter le paramètre *Les utilisateurs peuvent enregistrer l’application* situé sous : **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Les paramètres utilisateur autorisent des options]**. Si cette option est définie sur **Non**, l’administrateur peut enregistrer ces types d’applications.

Les utilisateurs peuvent accorder l’accès en se connectant à leur [compte de Power BI Microsoft](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Les administrateurs peuvent accorder l’accès à chacun en se connectant à leur [compte de Power BI Microsoft de l’administrateur](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Atteindre la limite de l’API

La création de rapports dans Power BI fonctionne avec l’API de création de rapports d’Analytics, de sorte que les limites de l’API s’appliquent. Pour plus d’informations, voir [Codes d’erreur des services web](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
