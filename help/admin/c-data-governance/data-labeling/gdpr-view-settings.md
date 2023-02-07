---
description: La boîte de dialogue Étiquette de confidentialité pour la gouvernance des données offre un aperçu des étiquettes de confidentialité et des espaces de noms d’une suite de rapports. Vous pouvez également exporter les paramètres vers un fichier .csv à partir de cet emplacement.
title: Affichage/gestion de l’étiquetage des données personnelles pour la gouvernance des données
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: f135138de15f3fc788e637128daeb064d0d453af
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 41%

---

# Affichage/gestion de l’étiquetage des données personnelles pour la gouvernance des données

Le **[!UICONTROL Étiquetage de la confidentialité pour la gouvernance des données]** La boîte de dialogue offre un aperçu des étiquettes de confidentialité et des espaces de noms d’une suite de rapports. Vous pouvez également exporter les paramètres vers un fichier .csv à partir de cet emplacement.

## Affichage des étiquettes de confidentialité {#view-privacy}

1. Connectez-vous à Adobe Experience Cloud.
1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Gouvernance des données]**.

   >[!NOTE]
   >
   >Si cet élément de menu ne s’affiche pas, vous devez être ajouté à un [profil de produit dans Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=fr) avec les autorisations requises pour cette fonctionnalité.

1. Dans la partie supérieure droite, sélectionnez les suites de rapports dont vous souhaitez afficher ou gérer les étiquettes de confidentialité.

   ![](assets/privacy_labeling.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Nom du composant]** | Cette colonne répertorie tous les composants (dimensions, mesures) qui font partie de cette suite de rapports. |
| **[!UICONTROL Identité]** | Les étiquettes « I » pour les données d’identification sont utilisées pour catégoriser les données qui peuvent identifier ou servir à contacter une personne spécifique. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#identity-data-labels) |
| **[!UICONTROL Sensibilité]** | Les étiquettes « S » pour les données sensibles sont utilisées pour catégoriser les données sensibles telles que les données géographiques. D’autres étiquettes de données sensibles seront introduites à l’avenir pour identifier d’autres types d’informations sensibles. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL Accès RGPD]** | Les étiquettes de gouvernance des données permettent aux utilisateurs de classer les données en fonction des considérations liées à la confidentialité et des conditions contractuelles afin qu’elles soient conformes aux réglementations et aux politiques d’entreprise. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL Suppression RGPD]** | Une étiquette de suppression n’est requise que pour les champs qui contiennent une valeur permettant d’associer un accès au titulaire de données (c.-à-d. qui permettrait d’identifier le titulaire de données). [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL Espace de noms]** | Lorsque vous étiquetez une variable comme ID-DEVICE ou ID-PERSON, vous êtes invité à fournir un espace de noms. Vous pouvez utiliser un espace de noms défini précédemment ou en définir un nouveau. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#section_F0A47AF8DA384A26BD56032D0ABFD2D7) |
| **[!UICONTROL Catégorie]** | Fait référence au type de composant, tel que le composant standard, la variable de conversion, etc. |

{style=&quot;table-layout:auto&quot;}

## Copier des étiquettes de confidentialité dans une suite de rapports  {#copy-to-rs}

Si vous souhaitez appliquer les mêmes paramètres de Confidentialité des données à plusieurs suites de rapports, procédez comme suit :

1. Sélectionnez la variable que vous souhaitez copier. Notez que vous ne pouvez copier les étiquettes que pour une variable à la fois.
1. Cliquez sur **[!UICONTROL Copier dans une ou plusieurs suites de rapports]** au bas de la boîte de dialogue Gouvernance des données.

   ![Copier dans une suite de rapports](assets/copy_to_reportsuite.png)

1. L’écran qui en résulte affiche le nom de la variable, le ou les libellés actuellement appliqués que vous essayez de copier, les suites de rapports et leurs identifiants, ainsi que la correspondance entre les paramètres des suites de rapports cibles.

   ![Copie du libellé vers la suite de rapports](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >Gardez à l’esprit que toutes les suites de rapports que vous sélectionnez doivent être mappées à votre organisation Experience Cloud.

   Lorsque vous copiez les étiquettes pour une variable ou un groupe de variables dans une autre suite de rapports, la copie a lieu sur la variable se trouvant à la même position dans la suite de rapports de destination. Pour les composants standard, les variables de liste et les événements de succès, les étiquettes seront copiées dans la variable avec la variable **même nom** dans la suite de rapports de destination.

   Toutefois, pour les variables de conversion (eVars) et les Dimensions de trafic (props), la copie est envoyée à la variable avec la variable **même nombre** dans la suite de rapports de destination. Par exemple, eVar12 sera copiée dans eVar12 dans toutes les suites de rapports de destination. Les noms de ces variables seront ignorés lors de la détermination de la cible de la copie. Si la variable correspondante n’est pas activée dans la suite de rapports de destination, la copie échoue pour cette variable.

   Lors de la copie des étiquettes pour des classifications définies pour une variable, les étiquettes sont copiées dans une classification de la variable correspondante dans la suite de rapports de destination (par exemple, eVar7 dans eVar7) qui porte le même nom que la classification définie pour la copie. Sinon, la copie pour les étiquettes de cette classification échoue.

1. Cochez la case en regard d’une ou de plusieurs suites de rapports pour lesquelles les paramètres correspondent.
1. Cliquez sur **[!UICONTROL Appliquer]**.

   Un message d’état s’affiche après l’application d’un libellé. Celui-ci indique le nom des variables de destination ou classifications et des suites de rapports pour lesquelles la copie a échoué.

   >[!IMPORTANT]
   >
   >Vérifiez toujours les suites de rapports de destination pour vous assurer que les étiquettes ont été copiées correctement. Ceci est particulièrement important pour les variables possédant des étiquettes ID ou DEL.

## Exportation dans un fichier .csv {#export-csv}

Vous pouvez télécharger un fichier CSV contenant toutes les définitions d’étiquettes actuelles pour toutes les variables des suites de rapports sélectionnées. Nous recommandons à votre équipe juridique de passer en revue vos choix d’étiquetage. Cette option facilite la vérification. En effet, au lieu d’effectuer la vérification lorsque vous êtes connecté à l’interface utilisateur Gouvernance des données, vous pouvez partager le fichier .CSV avec celle-ci.

1. Cliquez sur **[!UICONTROL Exportation CSV]** en haut à droite et cette boîte de dialogue s’affiche :

   ![](assets/export_csv.png)

1. Sélectionnez une ou plusieurs suites de rapports pour lesquelles vous souhaitez exporter tous les paramètres de gouvernance des données.

## Modification des étiquettes de confidentialité {#edit}

Voir [Attribuer ou modifier des étiquettes de confidentialité de suite de rapports](/help/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md).
