---
description: Au lieu de gérer et de charger des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
title: Workflow du créateur de règles de classification
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
source-git-commit: 1f97365ada0a182f743b6d920b0605232e030aec
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 87%

---

# Présentation du créateur de règles de classification (hérité)

{{classification-rulebuilder-deprecation}}

Au lieu de gérer et de charger des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Créateur de règles de classification](https://video.tv.adobe.com/v/3434375?captions=fre_fr&quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

## Avis important avant de commencer

Gardez les points suivants à l’esprit lors de l’utilisation de règles de classification :

* Vous pouvez exporter jusqu’à 10 millions de lignes à la fois.
* Lorsque CRB demande une exportation, il extrait les valeurs classifiées ET non classées, avec des valeurs non classées arrivant à la fin de l’exportation. Cela signifie qu’au fil du temps, vous pourriez remplir 10 millions de valeurs classées, sans jamais atteindre les valeurs non classées.
* Comme l’architecture est configurée de manière à ce que le Créateur de règles de classification puisse extraire un nombre « n » de serveurs, cela peut conduire à des incohérences quant aux serveurs sélectionnés et dans quel ordre. C’est pourquoi il est très difficile d’obtenir des valeurs non classées.

C’est la **solution de contournement** pour ceux qui ont plus de 10 millions de valeurs classées pour une dimension : Vous devrez exporter des valeurs non classées via FTP, par lots de 10 millions et les classer manuellement.

## Mise en route avec les règles de classification {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Créateur de règles de classification]**

Vous trouverez, ci-dessous, les étapes de haut niveau pour mettre en œuvre des règles de classification :

| Étape | Emplacement de l’action | Description |
|--- |--- |--- |
| Étape 1 (prérequis) : configurez votre schéma de classification. | [!UICONTROL Admin] > [!UICONTROL Suites de rapports] > [!UICONTROL Modifier les paramètres] > [!UICONTROL Classifications de trafic] ou [!UICONTROL Classifications de conversion] | Choisissez une variable et définissez les classifications à utiliser pour cette variable. <br>Au moins une colonne de classification doit être créée pour les variables pour qu’elles puissent être utilisées dans des règles.<br>Une fois les classifications activées, utilisez l’importateur et le créateur de règles pour classer des valeurs spécifiques. |
| Étape 2 : [Créer un jeu de règles](classification-rule-set.md). | [!UICONTROL Admin] > [!UICONTROL Créateur de règles de classification] > [!UICONTROL Ajouter un jeu de règles] | Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. |
| Étape 3 : Configurer des suites de rapports et des variables. | [!UICONTROL Créateur de règles de classification] > &lt;votre jeu de règles> | Appliquez le jeu de règles aux suites de rapports et aux variables. |
| Étape 4 : [Ajouter des règles de classification au jeu](classification-quickstart-rules.md). | [!UICONTROL Créateur de règles de classification] > &lt;votre jeu de règles> | Fait correspondre une condition à une classification, puis précise l’action à effectuer pour la règle.  Familiarisez-vous avec les informations de la section [Méthode de traitement des règles](classification-quickstart-rules.md). |
| Étape 5 : [Tester un jeu de règles de classification](classification-quickstart-rules.md) | [!DNL Testing Page] | Vous souhaitez tester les règles en vue de leur validation en les modifiant en mode préliminaire. Les règles ne peuvent pas être exécutées dans ce mode.<br>Cette étape est importante lorsque vous utilisez des [expressions régulières](classification-quickstart-rules.md). |
| Étape 6 : [Activer des règles valides](classification-rule-definitions.md). | [!DNL Rules Page] | Une fois les règles valides, activez le jeu de règles.  Vous pouvez, au besoin, remplacer des clés existantes. Reportez-vous à la section [Méthode de traitement des règles](classification-quickstart-rules.md). |
| Étape 7 (Facultatif) : [Supprimer les règles non souhaitées](classification-rule-definitions.md). | [!DNL Rules Page] | Supprime les règles non souhaitées d’un jeu.<br>Remarque : la suppression de règles ne supprime pas les données classifiées chargées. Voir [Supprimer des données de classification](/help/components/classifications/importer/t-delete-classification-data.md) si vous devez supprimer des données classifiées. |

>[!NOTE]
>
>Les groupes autorisés à utiliser l’outil d’importation de classifications peuvent utiliser des règles de classification. Pour obtenir des informations importantes sur le traitement, reportez-vous à la section [Méthode de traitement des règles](classification-quickstart-rules.md).

**Ressources supplémentaires**

**Blog** : pour plus d’informations sur cette fonctionnalité, consultez le blog Digital Marketing : [Classifications selon des règles](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Vidéo** : afficher la vidéo de [Présentation des classifications](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html?lang=fr).

