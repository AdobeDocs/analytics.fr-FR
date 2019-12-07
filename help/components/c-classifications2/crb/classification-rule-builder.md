---
description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
subtopic: Classifications
title: Workflow du créateur de règles de classification
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Workflow du créateur de règles de classification

Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.

## Avis important avant de commencer

Gardez ceci à l’esprit avant de commencer à utiliser les règles de classification :

* Notre système de classification actuel ne peut exporter que jusqu’à 10 millions de lignes à la fois.
* Lorsque le Créateur de règles de classification (CRB) demande une exportation, il extrait les valeurs classifiées ET non classées, avec des valeurs non classées arrivant à la fin de l’exportation. Cela signifie qu’au fil du temps, vous pourriez remplir 10 millions de valeurs classées, sans jamais atteindre les valeurs non classées.
* Comme l’architecture est configurée de manière à ce que le Créateur de règles de classification puisse extraire un nombre « n » de serveurs, cela peut conduire à des incohérences quant aux serveurs sélectionnés et dans quel ordre. C’est pourquoi il est très difficile d’obtenir des valeurs non classées.

C’est la **solution de contournement** pour ceux qui ont plus de 10 millions de valeurs classées pour une dimension : Vous devrez exporter des valeurs non classées via FTP, par lots de 10 millions et les classer manuellement.

## Mise en route avec les règles de classification {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; **[!UICONTROL Créateur de règles de classification]**

Vous trouverez, ci-dessous, les étapes de haut niveau pour mettre en œuvre des règles de classification :

| Étape | Emplacement de l’action | Description |
|--- |--- |--- |
| Étape 1 (condition préalable requise) : [Configurer votre schéma de classification](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] &gt; [!UICONTROL Suites de rapports] &gt; [!UICONTROL Modifier les paramètres] &gt; &lt;Classifications de trafic ou Classifications des conversions&gt; | Choisissez une variable et définissez les classifications à utiliser pour cette variable. <br>Au moins une colonne de classification doit être créée pour les variables pour qu’elles puissent être utilisées dans des règles.<br>Une fois les classifications activées, utilisez l’importateur et le créateur de règles pour classer des valeurs spécifiques. |
| Étape 2 : [Créer un jeu de règles](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] &gt; [!UICONTROL Créateur de règles de classification] &gt; [!UICONTROL Ajouter un jeu de règles] | Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. |
| Étape 3 : Configurer des suites de rapports et des variables. | [!UICONTROL Créateur de règles de classification] &gt; &lt;votre jeu de règles&gt; | Appliquez le jeu de règles aux suites de rapports et aux variables. |
| Étape 4 : [Ajouter des règles de classification au jeu](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Créateur de règles de classification] &gt; &lt;votre jeu de règles&gt; | Fait correspondre une condition à une classification, puis précise l’action à effectuer pour la règle.  Familiarisez-vous avec les informations de la section [Méthode de traitement des règles](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Étape 5 : [Tester un jeu de règles de classification](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Vous souhaitez tester les règles en vue de leur validation en les modifiant en mode préliminaire. Les règles ne peuvent pas être exécutées dans ce mode.<br>Cette étape est importante lorsque vous utilisez des [expressions régulières](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Étape 6 : [Activer des règles valides](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Une fois les règles valides, activez le jeu de règles.  Vous pouvez, au besoin, remplacer des clés existantes. Reportez-vous à la section [Méthode de traitement des règles](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Étape 7 (Facultatif) : [Supprimer les règles non souhaitées](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Supprime les règles non souhaitées d’un jeu.<br>Remarque : La suppression des règles n’entraîne pas la suppression des données classées téléchargées.  Reportez-vous à la section [Supprimer des données de classification](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) si vous devez supprimer des données classées. |

>[!NOTE]
>
>Les groupes autorisés à utiliser l’outil d’importation de classifications peuvent utiliser des règles de classification. Pour obtenir des informations importantes sur le traitement, reportez-vous à la section [Méthode de traitement des règles](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

**Ressources supplémentaires**

**Blog** : pour plus d’informations sur cette fonctionnalité, consultez le blog Digital Marketing : [Classifications selon des règles](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vidéo** : rendez-vous sur [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) pour consulter la vidéo [!UICONTROL Présentation des classifications].
