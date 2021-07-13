---
description: Problèmes courants lors de l’utilisation du Report Builder avec Power BI.
title: Dépannage de l’intégration de Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 51%

---

# Dépannage de l’intégration de Power BI

Recherchez et résolvez les problèmes courants lors de l’utilisation du Report Builder avec Power BI.

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

## Report Builder doit être autorisé à accéder aux ressources de votre organisation. Cet accès ne peut être accordé que par un administrateur. Demandez à un administrateur de vous accorder l’autorisation.

Demandez à l’administrateur Microsoft de vérifier le paramètre &quot;Les utilisateurs peuvent enregistrer une application&quot; sous : **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Principale Directory]** > **[!UICONTROL Les paramètres utilisateur autorisent les options]**. Si cette option est définie sur Non, cet administrateur peut enregistrer ces types d’applications.

Les utilisateurs peuvent accorder l’accès en utilisant le [lien](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US) suivant.

Les administrateurs ont accordé l’accès à chacun en utilisant le [lien](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US) suivant.
