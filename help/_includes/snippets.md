---
source-git-commit: 82bb289183f04ec6f795ebfa489436a7b0cc021f
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 64%

---
# Extraits

## Annonce de fin de vie de Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>En savoir plus sur l’[annonce de fin de vie](https://www.adobe.com/go/analytics_rnaeol_en) de Reports &amp; Analytics.

## Critères de filtre du dictionnaire de données {#dd-filter-criteria}

1. (Facultatif) Sélectionnez l’icône **Filtrer** ![icône du filtre du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png), puis sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Afficher uniquement les composants qui se trouvent dans votre liste de Favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, voir [Présentation des composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Segments**] | Afficher uniquement les composants qui sont des segments. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). <!--this is Filters in CJA--> |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Tout afficher**] | Afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Afficher uniquement les composants qui ne sont pas encore marqués comme Approuvés par un administrateur. En tant qu’administrateur, cela s’avère utile pour identifier les composants qui nécessitent votre révision et votre approbation. Cette option est réservée à l’administration. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ de description. Cette option est réservée à l’administration. |
   | [!UICONTROL **Afficher les doublons**] | <p>Afficher uniquement les composants portant le même nom ou la même définition qu’un autre composant de la suite de rapports sélectionnée. Les noms ou définitions doivent correspondre exactement pour s’afficher en tant que doublons.</p><p>Cette option est réservée à l’administration.</p><p>**REMARQUE :** Pour les définitions, cela inclut les composants que vous créez ainsi que ceux fournis par Adobe. Pour les noms, cela inclut actuellement uniquement les composants que vous créez et non ceux fournis par Adobe. L’affichage de noms en double pour les composants fournis par Adobe sera ajouté dans une prochaine version.</p> |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est réservée à l’administration. |
   | [!UICONTROL **Créé par Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants créés par Adobe. Les composants créés par l’administration ou une autre personne de votre organisation ne s’affichent pas. |

   {style="table-layout:auto"}

## Informations sur le composant Dictionnaire de données {#dd-component-information}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Une fois qu’un composant est approuvé, les administrateurs peuvent supprimer l’approbation en sélectionnant l’option **Approuvé** bouton .</p> |
| [!UICONTROL **Approbation requise**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administrateur.</p><p>Les administrateurs voient une option pour [!UICONTROL **Approuver**]. La sélection de cette option marque le composant comme &quot;Approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/analyze/analysis-workspace/components/add-component-descriptions.md)). |
| [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Les administrateurs peuvent traiter les composants que les utilisateurs voient dans cette section en sélectionnant les composants souhaités dans la section [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**] des champs de liste déroulante. Avant de traiter les composants que les utilisateurs voient, appliquez d’abord la variable **Tout afficher** filtre pour vous assurer que vous voyez des composants qui ne sont pas partagés avec vous.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similaire à**] | <p>Affiche les composants portant des noms similaires au composant que vous affichez.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Les composants en double de votre suite de rapports s’affichent également ici. L’administration Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Les administrateurs peuvent traiter les composants que les utilisateurs voient dans cette section en sélectionnant les composants souhaités dans la section [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**] des champs de liste déroulante. Avant de traiter les composants que les utilisateurs voient, appliquez d’abord la variable **Tout afficher** filtre pour vous assurer que vous voyez des composants qui ne sont pas partagés avec vous.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**REMARQUE :** Actuellement, la variable **Similaire à** comprend uniquement les composants que vous créez, et non ceux fournis par Adobe. Les composants fournis par Adobe seront ajoutés dans une prochaine version.</p> |
| [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
| [!UICONTROL **Type de composant**] | Indique le type du composant : dimension, mesure, segment ou période. |
| [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
| [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
| [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lorsque vous affichez des segments, des mesures calculées et des périodes. |

{style="table-layout:auto"}

## Tests limités de la phase de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

## Section Phase de tests limités de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).


## Clause de non-responsabilité du module externe {#plug-in}

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez l’équipe du compte d’Adobe de votre entreprise. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

