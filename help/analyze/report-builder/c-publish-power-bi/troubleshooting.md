---
description: Problèmes courants rencontrés lors de l’utilisation de Report Builder avec Power BI.
title: Dépannage de l’intégration de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: b98fbf52ab9fefef9c19e82f440ca9f5a81f933f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 66%

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

## Report Builder doit être autorisé à accéder aux ressources de votre organisation. Cet accès ne peut être accordé que par un administrateur. Demandez à un administrateur de vous accorder l’autorisation.

Demandez à un administrateur Microsoft de revoir le paramètre « Les utilisateurs peuvent enregistrer l’application » sous : **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Paramètres utilisateur - Options dʼautorisation]**. Si cette option est définie sur Non, cet administrateur peut enregistrer ces types d’applications.

Les utilisateurs peuvent accorder l’accès via le lien suivant : [lien](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Les administrateurs peuvent accorder lʼaccès à tout le monde via le lien suivant : [lien](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Atteindre la limite de l’API

La création de rapports dans Power BI fonctionne avec l’API de création de rapports d’Analytics, de sorte que les limites de l’API s’appliquent. Pour les API Analytics 2.0, la limite de ralentissement est définie à 120 appels par minute, par utilisateur, quelle que soit la suite de rapports ou la société. Lorsque la limite de ralentissement est franchie, le serveur renvoie un état HTTP 429 à l’utilisateur avec le contenu du message suivant :

```
too many requests
{"error_code":"429050","message":"Too many requests"}
```

Adobe vous recommande de *adhérer à* les instructions suivantes :

* Effectuez plusieurs requêtes plus petites au lieu d’une requête unique volumineuse.
* Demandez les données une seule fois et mettez-les en cache.
* N’interrogez pas les nouvelles données plus rapidement qu’un intervalle de 30 minutes.
* Extrayez les données historiques et incrémentez-les régulièrement au lieu de demander l’ensemble du jeu de données.

Adobe vous recommande de *éviter* les éléments suivants :

* Demander autant de données que possible dans une seule requête
* Demandez chaque jour une année de données avec une granularité quotidienne pour obtenir une fenêtre variable de 12 mois. Adobe recommande de demander les données du nouveau jour et de les fusionner avec les données existantes des jours précédents.
* Conduire une page web avec un widget de performance de site en effectuant une requête API chaque fois que la page web est chargée
* Migration depuis la version 1.4
