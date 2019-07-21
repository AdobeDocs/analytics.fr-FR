---
description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
seo-description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
seo-title: Flux de travaux du créateur de règles de classification
solution: Analytics
subtopic: Gestionnaire
title: Flux de travaux du créateur de règles de classification
topic: Outils d’administration
uuid: edb 1 f 07 e-fa 86-4055-8 f 4 b-cce 2 d 370 edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# Flux de travaux du créateur de règles de classification

Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.

## Avis important avant de commencer

Gardez ce point à l'esprit avant de commencer à utiliser les règles de classification :

* Notre système de classification actuel peut exporter jusqu'à 10 millions de lignes à la fois.
* Lorsque le créateur de règles de classification (CRB) demande une exportation, il extrait les valeurs classées ET non classifiées, avec des valeurs non classées qui arrivent à la fin de l'exportation. Cela signifie que, au fil du temps, vous pouvez remplir 10 millions de valeurs classées sans accéder aux valeurs non classifiées.
* Etant donné que l'architecture est configurée de la manière dont CRB peut provenir de n'importe quel nombre de serveurs, cela peut donner des incohérences quant aux serveurs sélectionnés et dans l'ordre. C'est pourquoi il est très difficile d'obtenir des valeurs non classifiées.

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## Mise en route avec les règles de classification {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; **[!UICONTROL Créateur de règles de classification]**

Voici les étapes générales que vous effectuez pour implémenter des règles de classification :

| Étape | Emplacement de l’action | Description |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL Admin] &gt; [!UICONTROL Report Suites] &gt; [!UICONTROL Modifier les paramètres] &gt; &lt; Classifications de trafic ou Classifications des conversions &gt; | Choisissez une variable et définissez les classifications à utiliser pour cette variable. <br>Au moins une colonne de classification doit être créée pour les variables pour qu’elles puissent être utilisées dans des règles.<br>Une fois les classifications activées, utilisez l’importateur et le créateur de règles pour classer des valeurs spécifiques. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] &gt; [!UICONTROL Créateur de règles de classification] &gt; [!UICONTROL Ajouter un jeu de règles] | Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. |
| Étape 3 : Configuration des suites de rapports et des variables | [!UICONTROL Créateur de règles de classification] &gt; &lt; votre jeu de règles &gt; | Appliquez le jeu de règles aux suites de rapports et aux variables. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Créateur de règles de classification] &gt; &lt; votre jeu de règles &gt; | Fait correspondre une condition à une classification, puis précise l’action à effectuer pour la règle.  Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Vous souhaitez tester les règles en vue de leur validation en les modifiant en mode préliminaire. Les règles ne peuvent pas être exécutées dans ce mode.<br>Cette étape est importante lors de l'utilisation [d'expressions régulières](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Une fois les règles valides, activez le jeu de règles.  Vous pouvez, au besoin, remplacer des clés existantes. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Supprime les règles non souhaitées d’un jeu.<br>Remarque : La suppression des règles n’entraîne pas la suppression des données classées téléchargées.  See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Les groupes autorisés à utiliser l'outil d'importation de classification peuvent utiliser des règles de classification. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Ressources supplémentaires**

**Blog**: Pour plus d'informations sur cette fonctionnalité, consultez le blog Digital Marketing : [Classifications selon des règles](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vidéo**: Visitez [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) pour visionner [!UICONTROL la vidéo Présentation] des classifications.
