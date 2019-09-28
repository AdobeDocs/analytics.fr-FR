---
description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
seo-description: Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.
seo-title: 'Workflow du créateur de règles de classification '
solution: Analytics
subtopic: Classifications
title: 'Workflow du créateur de règles de classification '
topic: Outils d’administration
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Workflow du créateur de règles de classification 

Au lieu de gérer et de transférer des classifications à chaque changement des codes de suivi, vous pouvez créer des classifications automatiques en fonction des règles automatiques, puis les appliquer dans plusieurs suites de rapports. Les règles sont traitées à intervalles réguliers, selon le volume de trafic lié aux classifications.

## Avis important avant de commencer

Gardez ceci à l’esprit avant de commencer à utiliser les règles de classification :

* Notre système de classification actuel ne peut exporter jusqu'à 10 millions de lignes à la fois.
* When classification rule builder (CRB) requests an export, it pulls both classified AND unclassified values, with unclassified values coming through at the end of the export. Cela signifie qu'au fil du temps, vous pourriez remplir 10 millions de valeurs classifiées - sans jamais atteindre les valeurs non classifiées.
* Comme l'architecture est configurée de manière à ce que CRB puisse extraire de "n" nombre de serveurs, cela peut conduire à des incohérences quant aux serveurs sélectionnés et dans quel ordre. C'est pourquoi il est très difficile d'obtenir des valeurs non classifiées.

C’est la **solution** pour ceux qui ont plus de 10 millions de valeurs classées pour une dimension : Vous devrez exporter des valeurs non classées par FTP, par lots de 10 millions de lots, et les classer manuellement.

## Mise en route avec les règles de classification {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; Créateur de règles de **[!UICONTROL classification]**

Here are the high-level steps you take to implement classification rules:

| Étape | Emplacement de l’action | Description |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] &gt; Suites [!UICONTROL de] rapports &gt; [!UICONTROL Modifier les paramètres] &gt; &lt;Classifications du trafic ou Classifications des conversions&gt; | Choisissez une variable et définissez les classifications à utiliser pour cette variable. <br>Au moins une colonne de classification doit être créée pour les variables pour qu’elles puissent être utilisées dans des règles.<br>Une fois les classifications activées, utilisez l’importateur et le créateur de règles pour classer des valeurs spécifiques. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] &gt; [!UICONTROL Créateur de règles de classification] &gt; [!UICONTROL Ajouter un jeu de règles] | Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. |
| Step 3: Configure report suites and variables. | [!UICONTROL Créateur] de règles de classification &gt; &lt;votre jeu de règles&gt; | Appliquez le jeu de règles aux suites de rapports et aux variables. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Créateur] de règles de classification &gt; &lt;votre jeu de règles&gt; | Fait correspondre une condition à une classification, puis précise l’action à effectuer pour la règle.  Familiarisez-vous avec les informations de la section [Comment les règles sont traitées](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Vous souhaitez tester les règles en vue de leur validation en les modifiant en mode préliminaire. Les règles ne peuvent pas être exécutées dans ce mode.<br>Cette étape est importante lorsque vous utilisez des expressions [](../../../components/c-classifications2/crb/classification-quickstart-rules.md)régulières. |
| Étape 6 : [Activez des règles](../../../components/c-classifications2/crb/classification-rule-definitions.md)valides. | [!DNL Rules Page] | Une fois les règles valides, activez le jeu de règles.  Vous pouvez, au besoin, remplacer des clés existantes. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Supprime les règles non souhaitées d’un jeu.<br>Remarque : La suppression des règles n’entraîne pas la suppression des données classées téléchargées.  See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Les groupes autorisés à utiliser l'outil d'importation de classification peuvent utiliser des règles de classification. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Ressources supplémentaires**

**Blog**: For additional information about this feature, see the Digital Marketing Blog: [Rule-based Classifications](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vidéo**: Visitez [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) pour visionner la vidéo Présentation [!UICONTROL des] classifications.
