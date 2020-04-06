---
description: Étiqueter les données de la suite de rapports signifie que vous attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports donnée. Assurez-vous de bien vous familiariser avec les étiquettes et leurs définitions.
title: Étiqueter les données d’une suite de rapports
uuid: a694851c-8933-496e-9118-113cc38cba8a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Étiqueter les données d’une suite de rapports

Étiqueter les données de la suite de rapports signifie que vous attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports donnée. Assurez-vous de bien vous familiariser avec les étiquettes et leurs définitions.

>[!NOTE] Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une réimplémentation de vos applications mobiles ou sites Web peut modifier la manière dont les variables existantes sont utilisées, ce qui peut également nécessiter des mises à jour des étiquettes.

## Attribuer ou modifier des étiquettes de suites de rapports {#section_39F829F35A274EACA532E2F6FF392996}

**Exemple** : en tant que contrôleur des données, vous prévoyez de collecter des adresses électroniques et des ID de cookie auprès des sujets des données pour traiter leurs demandes relatives à la Confidentialité des données. Ces ID de cookie sont stockés dans une suite de rapports dans Adobe Analytics. Pour créer une étiquette pour les adresses électroniques et les identifiants de cookie, vous devez utiliser la structure DULE (Data Usage Labeling &amp; Enforcement) de la plateforme Adobe Cloud dans Analytics.

1. Dans Analytics, accédez à **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]** > **[!UICONTROL (select report suite)]**![](assets/privacy_rs_settings.png)

1. Sélectionnez le groupe de variables à étiqueter.

   ![](assets/variables.png)

   * **Dimensions** standard (dimensions prêtes à l’emploi d’Adobe Analytics)
   * **Mesures** standard (mesures prêtes à l’emploi d’Adobe Analytics)
   * **Événements de conversion** (Succès personnalisés)
   * **Dimensions de conversion de marchandisage** (eVars de marchandisage)
   * **Dimensions** de conversion (eVars non merchandising)
   * **Dimensions** de trafic personnalisé (props)
   * **Dimensions et événements relatifs aux solutions** (Dimensions/événements relatifs à des solutions telles que Mobile, Vidéo, Activity Map, etc., et intégrations à des solutions telles qu’Adobe Campaign, Adobe Experience Manager, Advertising Cloud, etc.)
   * **Dimensions de traitement des données** (variables non directement exposées à la génération de rapports via l’interface utilisateur Adobe Analytics, mais disponibles via les demandes Flux de données et/ou Data Warehouse)

1. (Facultatif) Cliquez sur l’icône d’informations (i) en regard de chaque variable pour mieux comprendre ses valeurs les plus courantes au cours des 90 derniers jours. (Cette fonctionnalité n’est pas disponible pour les dimensions de traitement des données, car elles ne sont pas disponibles dans l’interface utilisateur d’Analytics.)

   ![](assets/info.png)

1. Select one or more variables by clicking their checkbox, then select the **[!UICONTROL Edit]** icon (to the right) to edit one or more variable(s).

   ![](assets/edit.png)

1. La boîte de dialogue Etiquettes des données **d’** identité s’ouvre automatiquement. Ces étiquettes classent les données pouvant être utilisées seules ou en combinaison avec d’autres données afin d’identifier ou de permettre un contact direct avec un individu. Pour plus d’informations sur ces options, reportez-vous à [Étiquettes de données d’identification (DULE).](/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels)

   >[!NOTE]
   >
   >Le cadre DULE (Data Usage Labeling &amp; Enforcement) est conçu pour fournir un moyen uniforme au sein des Solutions/Services/Plateformes pour capturer, communiquer et utiliser les métadonnées relatives aux données dans Adobe Experience Cloud. Les métadonnées aident les contrôleurs des données à indiquer quelles données sont des informations personnelles, des données sensibles et à définir les restrictions contractuelles associées aux données.

   ![](assets/identity_labels.png)

1. Ouvrez la section **Données sensibles** pour définir les étiquettes des données sensibles qui catégorisent les données de géolocalisation. Pour plus d’informations sur ces options, reportez-vous à [Étiquettes de données sensibles (DULE).](/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels)

   ![](assets/sensitive_data.png)

1. Ouvrez la section Confidentialité des données pour définir les étiquettes de **gouvernance des données**. Utilisez cette section pour enseigner à Adobe comment traiter chaque variable pour les demandes d’accès et de suppression relatives à la Confidentialité des données, et pour définir les variables à analyser pour trouver les ID des sujets de données pour ces demandes. Pour plus d’informations sur ces options, reportez-vous à [Étiquettes de gouvernance des données (Confidentialité des données).](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)

   ![](assets/privacy_labels.png)

1. Click **[!UICONTROL Apply]** once you have completed all labeling.

## Copier des étiquettes dans une ou plusieurs suites de rapports {#section_7C6FDAFF049F4126B84F6261F72668EE}

Si vous souhaitez appliquer les mêmes paramètres DULE/Confidentialité des données à plusieurs suites de rapports, vous pouvez procéder comme suit :

1. Sélectionnez le groupe de variables (Dimensions standard, Dimensions de conversion, etc.) contenant la variable à copier. Notez que vous ne pouvez copier les libellés que pour un groupe de variables à la fois.
1. Sélectionnez une partie ou la totalité des variables de ce groupe.
1. Cliquez **[!UICONTROL Copy Labels to Report Suite(s)]** dans la partie supérieure droite de la boîte de dialogue Gouvernance des données.

   ![](assets/apply_as_template.png)

1. Either check **[!UICONTROL Select All]** to copy labels for the selected variables to all report suites or select the individual report suites that you want to copy the labels to.

   >[!IMPORTANT]
   >
   >Gardez à l’esprit que toutes les suites de rapports que vous sélectionnez doivent être mappées à votre organisation Experience Cloud.

   Lorsque vous copiez les étiquettes pour une variable ou un groupe de variables dans une autre suite de rapports, la copie a lieu sur la variable se trouvant à la même position dans la suite de rapports de destination. Pour les dimensions standard, les mesures standard, les dimensions de la solution et les dimensions de  et de traitement des données, les étiquettes seront copiées dans la variable avec le **même nom** dans la suite de rapports de destination.

   Toutefois, pour les variables de conversion (eVars), les dimensions de conversion de marchandisage et les dimensions de trafic personnalisé (props), la copie sera envoyée à la variable avec le **même nombre** dans la suite de rapports de destination. Par exemple, l’eVar12 sera copiée dans l’eVar12 dans toutes les suites de rapports de destination. Les noms de ces variables seront ignorés lors de la détermination du  de la copie. Si la variable correspondante n’est pas activée dans la suite de rapports de destination, la copie échoue pour cette variable.

   Lors de la copie des libellés des classifications définies pour une variable, les libellés sont copiés dans une classification de la variable correspondante dans la suite de rapports de destination (eVar7 à eVar7, par exemple) dont le nom est identique à celui de la classification copiée. Sinon, la copie des étiquettes de cette classification échouera.

   Un message d’état s’affiche après l’application d’un ensemble de libellés. Le message d’état inclut les noms des variables ou classifications de destination et de leurs suites de rapports pour lesquelles la copie a échoué.

   >[!IMPORTANT]
   >
   >Vous devez toujours vérifier les suites de rapports de destination pour vous assurer que les étiquettes sont copiées correctement. Ceci est particulièrement important pour les variables possédant des étiquettes ID ou DEL.

1. Cliquez sur **[!UICONTROL Apply]**.

