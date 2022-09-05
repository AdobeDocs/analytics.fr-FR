---
description: La boîte de dialogue Gouvernance des données dans les Outils d’administration offre un aperçu des suites de rapports configurées pour la gouvernance des données, indique si elles ont été mappées à une organisation Experience Cloud et si une politique de conservation des données est mise en place pour cette suite de rapports.
title: Afficher/Gérer les paramètres de gouvernance des données de la suite de rapports
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 538d5bcea449ecb868ff9ebcce4ca742f91b4a87
workflow-type: ht
source-wordcount: '517'
ht-degree: 100%

---

# Afficher/Gérer les paramètres de gouvernance des données de la suite de rapports

La boîte de dialogue Gouvernance des données dans les Outils d’administration offre un aperçu des suites de rapports configurées pour la gouvernance des données, indique si elles ont été mappées à une organisation Experience Cloud et si une politique de conservation des données est mise en place pour cette suite de rapports.

1. Connectez-vous à Adobe Experience Cloud.
1. Sélectionnez **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Gouvernance des données]**.

>[!NOTE]
>
>Si cet élément de menu ne s’affiche pas, vous devez être ajouté à un [profil de produit dans Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=fr) avec les autorisations requises pour cette fonctionnalité.

1. Vous verrez toutes les suites de rapports faisant partie de votre société de connexion :

   ![](assets/privacy_setup_an.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Suites de rapports]** | La première ligne contient le nom convivial de la suite de rapports. La deuxième ligne contient le nom interne de la suite de rapports. Si vous êtes autorisé à définir des étiquettes pour une suite de rapports, la première ligne est un lien cliquable qui vous dirige vers la page d’étiquetage. |
| **[!UICONTROL Mappage de l’organisation]** | <ul><li>Mappé : cette suite de rapports a déjà été mappée à la même organisation Experience Cloud que la société de connexion Analytics à laquelle vous êtes connecté. Seules les suites de rapports possédant ce paramètre peuvent être étiquetées.</li><li>Mappé à une autre organisation : une autre organisation Experience Cloud a déjà mappé cette suite de rapports à son organisation.</li></ul> |
| **[!UICONTROL Politique de conservation des données]** | La mise en œuvre de la Confidentialité des données pour Analytics nécessite la mise en place d’une politique de conservation des données. Ce paramètre indique si :<ul><li>une politique de conservation des données est en place pour cette suite de rapports ;</li><li>combien de temps les données sont conservées par Adobe avant d’être supprimées. Par défaut, la période de conservation des données est de 25 mois.</li></ul>**Remarque** : Adobe Analytics ne peut pas vous aider à traiter les demandes de l’API relative à la confidentialité des données, c’est-à-dire traiter les demandes d’accès ou de suppression que vous recevez de vos utilisateurs finaux, si la période de conservation des données n’a pas été définie. Veuillez contacter votre gestionnaire du succès client pour définir votre période de conservation des données. |
| **[!UICONTROL Groupes]** | La fonction de regroupement n’est pas prise en charge actuellement. |
| Barre latérale gauche | Cliquez sur l’icône de l’entonnoir pour ouvrir ou fermer la barre latérale. La section [!UICONTROL Mappage d’organisations] indique le nombre de suites de rapports qui entrent dans chacune des catégories décrites. La section [!UICONTROL Politique de conservation des données] affiche chaque politique de conservation des données actuellement en place au sein de votre organisation, ainsi que le nombre de suites de rapports auxquelles cette politique de conservation a été attribuée. |
| **[!UICONTROL Exporter dans un fichier CSV]** | Si vous cochez une ou plusieurs suites de rapports, l’option Exporter au format CSV s’affiche. Cette option vous permet de télécharger un fichier CSV contenant toutes les définitions d’étiquettes actuelles pour l’ensemble des variables des suites de rapports sélectionnées. Nous recommandons à votre équipe juridique de passer en revue vos choix d’étiquetage. Cette option facilite la vérification. En effet, au lieu d’effectuer la vérification lorsque vous êtes connecté à l’interface utilisateur Gouvernance des données, vous pouvez partager le fichier .CSV avec celle-ci. |
