---
title: Règles VISTA dans Adobe Analytics
description: En savoir plus sur les règles VISTA et leurs fonctionnalités.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 57%

---

# Règles VISTA dans Adobe Analytics

Les règles VISTA sont une autre forme de modification des données personnalisées que vous pouvez appliquer entre la collecte et le traitement de données. Consultez la section [Ordre de traitement](processing-order.md) pour plus d’informations sur l’étape exacte de l’application des règles VISTA dans le pipeline de données. Les règles VISTA n’affectent que les données actives lors de leur collecte. Elles ne modifient pas les données existantes.

Voici quelques cas d’utilisation courants des règles VISTA :

* Copier un accès Analytics d’une suite de rapports vers une autre, en modifiant éventuellement les données dans la suite de rapports copiée.
* Exclusion d’adresse IP personnalisée qui dépasse les cas d’utilisation proposés par [Exclure par adresse IP](/help/admin/tools/exclude-ip.md).
* Modifier de manière conditionnelle ou globale toute valeur de variable.
* Dupliquer des valeurs de variable vers d’autres variables.
* Télécharger des fichiers sur un site FTP Adobe pouvant avoir un impact sur les valeurs de variable.

De nombreux cas d’utilisation des règles VISTA sont déjà proposés par [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md), [Règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), [Suites de rapports virtuelles](/help/components/vrs/vrs-about.md) ou simplement en mettant à jour votre implémentation Adobe Analytics. Adobe ne recommande les règles VISTA qu’en dernier recours.

>[!IMPORTANT]
>
>L’implémentation et la configuration des règles VISTA nécessitent un accord payant entre votre entreprise et Adobe Professional Services. Contactez l’équipe chargée de votre compte Adobe si vous souhaitez créer ou mettre à jour une règle VISTA.
>
>Remarque :
>
>* La création de règles VISTA inclut uniquement l’implémentation initiale. La maintenance continue ou les mises à jour des règles VISTA nécessitent un engagement payant distinct.
>
>* Les règles VISTA reposent sur des conditions spécifiques dans vos données. Par exemple, des modifications apportées à votre implémentation Adobe Analytics, aux types de données ou à la longueur des chaînes collectées, aux tables utilisées pour DB VISTA ou à d’autres modifications apportées aux modèles de données d’entrée peuvent entraîner l’arrêt prévu d’une règle VISTA. Adobe recommande de consulter régulièrement vos règles VISTA pour déterminer si des mises à jour ou des suppressions sont nécessaires.

## Créer une règle VISTA {#create}

Vous devez travailler avec Adobe Professional Services pour créer une règle VISTA. Contactez l’équipe chargée de votre compte Adobe si vous souhaitez créer une règle VISTA.

## Afficher les règles VISTA existantes {#see}

Adobe ne propose pas d’interface utilisateur pour afficher les règles VISTA existantes. Contactez votre équipe de compte Adobe ou l’assistance clientèle avec la suite de rapports souhaitée pour récupérer une liste des règles VISTA existantes.
