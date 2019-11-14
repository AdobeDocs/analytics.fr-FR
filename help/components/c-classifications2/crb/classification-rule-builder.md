---
description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
solution: Analytics
subtopic: Classifications
title: 'Workflow du créateur de règles de classification '
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Workflow du créateur de règles de classification 

Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.

## Avis important avant de commencer

Gardez ceci à l’esprit avant de commencer à utiliser les règles de classification :

* Notre système de classification actuel ne peut exporter jusqu'à 10 millions de lignes à la fois.
* Lorsque le créateur de règles de classification (CRB) demande une exportation, il extrait les valeurs classifiées ET non classifiées, avec les valeurs non classifiées arrivant à la fin de l’exportation. Cela signifie qu'au fil du temps, vous pourriez remplir 10 millions de valeurs classifiées - sans jamais atteindre les valeurs non classifiées.
* Comme l'architecture est configurée de manière à ce que CRB puisse extraire de "n" nombre de serveurs, cela peut conduire à des incohérences quant aux serveurs sélectionnés et dans quel ordre. C'est pourquoi il est très difficile d'obtenir des valeurs non classifiées.

C’est la **solution** pour ceux qui ont plus de 10 millions de valeurs classées pour une dimension : Vous devrez exporter des valeurs non classées par FTP, par lots de 10 millions de lots, et les classer manuellement.

## Mise en route avec les règles de classification {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; Créateur de règles de **[!UICONTROL classification]**

Vous trouverez ci-dessous les étapes générales que vous suivez pour implémenter des règles de classification :

| Étape  | Emplacement de l’action | Description |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] &gt; Suites [!UICONTROL de] rapports &gt; [!UICONTROL Modifier les paramètres] &gt; &lt;Classifications du trafic ou Classifications des conversions&gt; | Choisissez une variable et définissez les classifications à utiliser pour cette variable. <br>Au moins une colonne de classification doit être créée pour les variables pour qu’elles puissent être utilisées dans des règles.<br>Une fois les classifications activées, utilisez l’importateur et le créateur de règles pour classer des valeurs spécifiques. |
| Step 2: [Create a rule set](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] &gt; [!UICONTROL Créateur de règles de classification] &gt; [!UICONTROL Ajouter un jeu de règles] | Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. |
| Étape 3 : Configurez les suites de rapports et les variables. | [!UICONTROL Créateur] de règles de classification &gt; &lt;votre jeu de règles&gt; | Appliquez le jeu de règles aux suites de rapports et aux variables. |
| Step 4: [Add classification rules to the set](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Créateur] de règles de classification &gt; &lt;votre jeu de règles&gt; | Fait correspondre une condition à une classification, puis précise l’action à effectuer pour la règle.  Familiarisez-vous avec les informations de la section [Comment les règles sont traitées](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Vous souhaitez tester les règles en vue de leur validation en les modifiant en mode préliminaire. Les règles ne peuvent pas être exécutées dans ce mode.<br>Cette étape est importante lorsque vous utilisez des expressions [](/help/components/c-classifications2/crb/classification-quickstart-rules.md)régulières. |
| Étape 6 : [Activez des règles](/help/components/c-classifications2/crb/classification-rule-definitions.md)valides. | [!DNL Rules Page] | Une fois les règles valides, activez le jeu de règles.  Vous pouvez, au besoin, remplacer des clés existantes. See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Supprime les règles non souhaitées d’un jeu.<br>Remarque : La suppression des règles n’entraîne pas la suppression des données classées téléchargées.  See  [Delete classification data](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Les groupes autorisés à utiliser l'outil d'importation de classification peuvent utiliser des règles de classification. See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Ressources supplémentaires**

**Blog**: Pour plus d’informations sur cette fonctionnalité, voir le blog Digital Marketing : Classifications [basées sur des règles](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vidéo**: Visitez [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) pour visionner la vidéo Présentation [!UICONTROL des] classifications.
