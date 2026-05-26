---
title: Configurer Les Paramètres Pour Report Builder
description: Découvrez comment configurer les paramètres de Report Builder.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
TQID: https://experienceleague.adobe.com/aHEmYs37KDXtaoAbFiI6WBCvmdhN0RrMWDl-CeEotKw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 33bb8dc51fa1e0365fbf2b4ef10fd0f044f5e368
workflow-type: tm+mt
source-wordcount: 285
ht-degree: 24%

---

# Paramètres de Report Builder


Utilisez le volet **Paramètres** pour configurer les paramètres au niveau de l’application, tels que la langue affichée par l’interface utilisateur ou si vous souhaitez travailler ou non en mode hors ligne. Les paramètres sont appliqués immédiatement et ils sont définis pour toutes les sessions suivantes jusqu’à ce qu’ils soient modifiés.

Pour modifier les paramètres de Report Builder

1. Sélectionnez l’icône **Paramètres**.

1. Apportez des modifications à [activer ou désactiver le mode hors ligne](#off-line-mode), [sélectionner une langue](#language) ou [activer le dépannage](#troubleshooting).

1. Sélectionnez **[!UICONTROL Appliquer]**.

   ![Volet de période Report Builder affichant le bouton Annuler et appliquer.](./assets/report-builder-settings.png){zoomable="yes"}

## Mode hors ligne

Lorsque vous créez et modifiez un bloc de données en mode hors ligne, les données ne sont pas récupérées. Au lieu de cela, des données de simulation sont utilisées afin que vous puissiez travailler rapidement sans attendre que la requête s’exécute. Lorsque vous êtes de retour en ligne, sélectionnez ![Actualiser](/help/assets/icons/Refresh.svg) **[!UICONTROL Actualiser le bloc de données]** ou ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Actualiser tous les blocs de données]** pour actualiser les blocs de données avec les données réelles.

Pour activer le mode hors ligne

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).

1. Activez le bouton (bascule) **[!UICONTROL Activer le mode hors ligne]**.

1. Saisissez un entier positif dans le champ **[!UICONTROL Afficher les données de mesure]**.

1. Sélectionnez **[!UICONTROL Appliquer]**.


## Langue

Vous pouvez choisir la langue de l’interface de Report Builder. Toutes les langues Customer Journey Analytics prises en charge sont disponibles.

Pour sélectionner la langue utilisée dans l’interface de Report Builder :

1. Sélectionnez une langue dans le menu déroulant **[!UICONTROL Langue]**.

1. Sélectionnez **Appliquer.**

## Résolution des problèmes

Pour résoudre les problèmes et résoudre les problèmes liés aux tickets d’assistance, activez la fonction permettant de consigner les demandes Report Builder. Dans le panneau **** :

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).
1. Sélectionnez **[!UICONTROL Enregistrer le ou les blocs de données de requête du Report Builder dans la console web]**. <br/>Les requêtes sont envoyées à la console de votre navigateur web. Reportez-vous à la documentation de votre navigateur web pour savoir comment ouvrir le journal de la console dans le cadre des outils de développement du navigateur web.

