---
source-git-commit: df0d2c4687117fd00714ced56db6259e44698a20
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 15%

---
# Extraits

## Annonce de fin de vie de Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>En savoir plus sur l’[annonce de fin de vie](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics.

## Critères de filtre du dictionnaire de données {#dd-filter-criteria}

1. (Facultatif) Sélectionnez le **Filtrer** icon ![Icône Filtre du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png), puis sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme Approuvés par un administrateur. |
   | [!UICONTROL **Favoris**] | Afficher uniquement les composants qui se trouvent dans votre liste de Favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, voir [Présentation des composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des Dimensions. (Cette option est également disponible dans la variable [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois.) |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible dans la variable [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois.) |
   | [!UICONTROL **Segments**] | Afficher uniquement les composants qui sont des segments. (Cette option est également disponible dans la variable [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible dans la variable [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois.) |
   | [!UICONTROL **Tout afficher**] | Afficher tous les composants. Cette option est disponible uniquement pour les administrateurs. |
   | [!UICONTROL **Non approuvé**] | Afficher uniquement les composants qui ne sont pas encore marqués comme Approuvés par un administrateur. En tant qu’administrateur, cela s’avère utile pour identifier les composants qui nécessitent votre révision et votre approbation. Cette option est disponible uniquement pour les administrateurs. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ Description . Cette option est disponible uniquement pour les administrateurs. |
   | [!UICONTROL **Afficher les doublons**] | Afficher uniquement les composants qui ont le même libellé ou la même description qu’un autre composant de la suite de rapports sélectionnée. Les libellés ou descriptions doivent correspondre exactement pour s’afficher en tant que doublons. Cette option est disponible uniquement pour les administrateurs. |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est disponible uniquement pour les administrateurs. |
   | [!UICONTROL **Créé par Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants qui ont été créés par Adobe. Les composants créés par un administrateur ou un autre utilisateur de votre entreprise ne s’affichent pas. |

   {style=&quot;table-layout:auto&quot;}

## Informations sur le composant du dictionnaire de données {#dd-component-information}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administrateur.</p><p>Les administrateurs voient une option pour [!UICONTROL **Ne pas approuver**]. La sélection de cette option marque le composant comme &quot;Non approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Non approuvé**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administrateur.</p><p>Les administrateurs voient une option pour [!UICONTROL **Approuver**]. La sélection de cette option marque le composant comme &quot;Approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administrateur Analytics, comme décrit dans la section [Ajout de descriptions de composant](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous affichez.</p><p>Jusqu’à 5 composants sont affichés sur les 5 types de composants Principaux : Mesure, mesure calculée, Dimension, segment et période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous avez accès à la vue s’affichent. <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Similaire à**] | <p>Affiche les composants avec des libellés similaires au composant que vous affichez.</p><p>Jusqu’à 5 composants sont affichés sur les 5 types de composants Principaux : Mesure, mesure calculée, Dimension, segment et période.</p><p>Seuls les composants que vous avez accès à la vue s’affichent.</p><p>Tous les composants en double de votre suite de rapports s’affichent ici. Les administrateurs d’Analytics doivent identifier et supprimer tous les composants en double, comme décrit dans la section [Surveillance de l’intégrité du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md). <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Balises**] | Affiche toutes les balises appliquées au composant. Les utilisateurs disposant d’un accès administrateur peuvent ajouter des balises lors de la modification du composant. |
| [!UICONTROL **Type de composant**] | Répertorie le type de composant qu’il est, qu’il s’agisse d’une Dimension, d’une mesure, d’un segment ou d’une période. |
| [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur qui a créé le composant. |
| [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
| [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lorsque vous affichez des segments, des mesures calculées et des plages de dates. <!--for CJA, it is displayed for all components--> |

{style=&quot;table-layout:auto&quot;}

## Tests limités de la phase de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>Les fonctionnalités décrites dans cet article se trouvent dans la phase de test limité de la version et peuvent ne pas être encore disponibles dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

## Section Tests limités de la phase de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Les fonctionnalités décrites dans cette section se trouvent dans la phase Tests limités de la version et peuvent ne pas être encore disponibles dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

