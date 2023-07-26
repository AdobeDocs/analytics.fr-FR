---
description: La boîte de dialogue Étiquetage de confidentialité pour la gouvernance des données offre un aperçu des étiquettes de confidentialité et des espaces de noms d’une suite de rapports. Vous pouvez également exporter les paramètres vers un fichier .csv à partir de cet emplacement.
title: Afficher/gérer l’étiquetage de confidentialité pour la gouvernance des données
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: af3bdcf3eedecc6b670e51dcb2f6980e75982077
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 89%

---

# Afficher/gérer l’étiquetage de confidentialité pour la gouvernance des données

La boîte de dialogue **[!UICONTROL Étiquetage de confidentialité pour la gouvernance des données]** offre un aperçu des étiquettes de confidentialité et des espaces de noms d’une suite de rapports. Vous pouvez également exporter les paramètres vers un fichier .csv à partir de cet emplacement.

## Afficher les étiquettes de confidentialité {#view-privacy}

1. Connectez-vous à Adobe Experience Cloud.
2. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Gouvernance des données]**.

   >[!NOTE]
   >
   >Si cet élément de menu ne s’affiche pas, vous devez être ajouté à une [profil de produit dans Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=fr) avec les autorisations d’accès à cette fonctionnalité ou l’accès à une suite de rapports dans le Admin Console.

3. Dans la partie supérieure droite, sélectionnez les suites de rapports dont vous souhaitez afficher ou gérer les étiquettes de confidentialité.

   ![](assets/privacy_labeling.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Nom du composant]** | Cette colonne répertorie tous les composants (dimensions, mesures) qui font partie de cette suite de rapports. |
| **[!UICONTROL Identité]** | Les étiquettes « I » pour les données d’identification sont utilisées pour classer les données qui peuvent servir à identifier ou à contacter une personne spécifique. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-identity-labels) |
| **[!UICONTROL Sensibilité]** | Les étiquettes « S » pour les données sensibles sont utilisées pour classer les données sensibles telles que les données géographiques. D’autres étiquettes de données sensibles seront introduites à l’avenir pour identifier d’autres types d’informations sensibles. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL Accès aux RGPD]** | Les étiquettes de gouvernance des données permettent aux utilisateurs de classer les données en fonction des considérations liées à la confidentialité et des conditions contractuelles afin qu’elles soient conformes aux réglementations et aux politiques d’entreprise. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL Suppression des RGPD]** | Une étiquette de suppression n’est nécessaire que pour les champs contenant une valeur qui permettrait de faire l’association entre un accès et le titulaire de données (autrement dit, qui permettrait d’identifier le titulaire de données). [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL Espace de noms]** | Lorsque vous étiquetez une variable comme ID-DEVICE ou ID-PERSON, vous êtes invité à fournir un espace de noms. Vous pouvez utiliser un espace de noms défini précédemment ou en définir un nouveau. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#provide-namespace) |
| **[!UICONTROL Catégorie]** | Fait référence au type de composant, tel que le composant standard, la variable de conversion, etc. |

{style="table-layout:auto"}

## Copier des étiquettes de confidentialité dans une suite de rapports  {#copy-to-rs}

Si vous souhaitez appliquer les mêmes paramètres de confidentialité des données à plusieurs suites de rapports, procédez comme suit :

1. Sélectionnez la variable que vous souhaitez copier. Notez que vous ne pouvez copier les étiquettes que d’une seule variable à la fois.
1. Cliquez sur **[!UICONTROL Copier dans une ou plusieurs suites de rapports]** au bas de la boîte de dialogue Gouvernance des données.

   ![Copier dans une suite de rapports](assets/copy_to_reportsuite.png)

1. L’écran qui en résulte affiche le nom de la variable, la ou les étiquettes actuellement appliquées que vous essayez de copier, les suites de rapports et leurs identifiants, ainsi que la correspondance entre les paramètres des suites de rapports cibles.

   ![Copie de l’étiquette dans une suite de rapports](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >N’oubliez pas que toutes les suites de rapports que vous sélectionnez doivent être mappées à votre organisation Experience Cloud.

   Lorsque vous copiez les étiquettes pour une variable ou un groupe de variables dans une autre suite de rapports, la copie a lieu sur la variable se trouvant à la même position dans la suite de rapports de destination. Pour les composants standard, les variables de liste et les événements de succès, les étiquettes sont copiées dans la variable portant le **même nom** dans la suite de rapports de destination.

   Cependant, pour les variables de conversion (eVars) et les dimensions de trafic (props), la copie a lieu sur la variable portant le **même numéro** dans la suite de rapports de destination. Par exemple, eVar12 sera copiée dans eVar12 dans toutes les suites de rapports de destination. Les noms de ces variables seront ignorés lors de la détermination de la cible de la copie. Si la variable correspondante n’est pas activée dans la suite de rapports de destination, la copie échoue pour cette variable.

   Lors de la copie des étiquettes pour des classifications définies pour une variable, les étiquettes sont copiées dans une classification de la variable correspondante dans la suite de rapports de destination (par exemple, eVar7 dans eVar7) qui porte le même nom que la classification définie pour la copie. Sinon, la copie pour les étiquettes de cette classification échoue.

1. Cochez la case en regard d’une ou de plusieurs suites de rapports pour lesquelles les paramètres correspondent.
1. Cliquez sur **[!UICONTROL Appliquer]**.

   Un message de statut s’affiche après l’application des étiquettes. Celui-ci indique le nom des variables de destination ou classifications et des suites de rapports pour lesquelles la copie a échoué.

   >[!IMPORTANT]
   >
   >Vous devez toujours vérifier les suites de rapports de destination pour vérifiez que les étiquettes sont copiées correctement. Ceci est particulièrement important pour les variables possédant des étiquettes ID ou DEL.

## Exporter vers un fichier .csv {#export-csv}

Vous pouvez télécharger un fichier CSV contenant toutes les définitions d’étiquettes actuelles pour toutes les variables de la ou des suites de rapports sélectionnées. Nous recommandons à votre équipe juridique de passer en revue vos choix d’étiquetage. Cette option facilite la vérification. En effet, au lieu d’effectuer la vérification lorsque vous êtes connecté à l’interface utilisateur Gouvernance des données, vous pouvez partager le fichier .CSV avec celle-ci.

1. Cliquez sur **[!UICONTROL Exporter au format CSV]** en haut à droite et cette boîte de dialogue s’affiche :

   ![](assets/export_csv.png)

1. Sélectionnez une ou plusieurs suites de rapports pour lesquelles vous souhaitez exporter tous les paramètres de gouvernance des données.

## Modifier les étiquettes de confidentialité {#edit}

Consultez [Attribuer ou modifier des étiquettes de confidentialité de suites de rapports](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md).
