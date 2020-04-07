---
description: valeur nulle
title: Configuration d’une visualisation Abandons
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 2cd9872ed5052b9569d03a07d5171221b9e0af29

---


# Configuration d’une visualisation Abandons

Vous pouvez spécifier les points de contact d’après lesquels créer une séquence d’abandons multidimensionnelle. En général, un point de contact est une page sur votre site. Ils ne se limitent toutefois pas à cela. Vous pouvez par exemple ajouter des événements, tels que des unités, ainsi que des visiteurs uniques et des visites récurrentes. Vous pouvez également ajouter des dimensions, telles qu’un  de, un type de navigateur ou un terme de recherche interne.

Il est possible en outre d’ajouter des segments dans un point de contact, par exemple pour comparer les utilisateurs d’iOS à ceux d’Android. Faites glisser les segments à comparer en haut de l’abandon pour ajouter des informations sur ces segments au rapport sur les abandons. Si vous souhaitez afficher uniquement ces segments, pouvez-vous supprimer la ligne de base Toutes les visites.

Le nombre d’étapes que vous pouvez ajouter ou le nombre de dimensions utilisées ne sont pas limités.

Vous pouvez effectuer le cheminement sur les eVars, y compris les eVars de marchandisage et les [variables](https://marketing.adobe.com/resources/help/fr_FR/sc/implement/listN.html) de liste (variables pouvant avoir plusieurs valeurs par accès, telles que les produits, les variables de liste, les eVars de marchandisage et les props de ). Supposons par exemple qu’un visiteur consulte sur une page la séquence chaussures, chemise puis, sur la page suivante, la séquence chemise, chaussettes. Le prochain rapport de flux de produits des chaussures sera chemise et chaussettes, PAS chemise.

1. Faites glisser une [!UICONTROL Fallout] visualisation de la liste déroulante Visualisations vers une [!UICONTROL Freeform Table].

1. Drag the Page dimension into the Freeform Table and from there, drag a page (in this case, Home - JJEsquire) into the **[!UICONTROL Add TouchPoint]** field as the first touchpoint.

   ![](assets/fallout1.png)

   Pointez sur un point de contact afin d’afficher les abandons et autres informations sur ce niveau (nom du point de contact, nombre de visiteurs à ce point, etc.) puis consultez le taux de succès pour ce point de contact (et comparez-le à celui d’autres points de contact).

   Les nombres encadrés dans la partie grise de la barre correspondent aux abandons entre les points de contact (et non à l’ensemble des abandons à ce point). Le % du point de contact montre les abandons réussis de l’étape précédente à l’étape actuelle du rapport sur les abandons.

   Vous pouvez également ajouter une seule page au rapport des abandons, plutôt que la dimension entière. Cliquez sur la flèche droite &quot;>&quot; dans la dimension de la page pour sélectionner la page spécifique à ajouter au rapport sur les abandons.

1. Continuez à ajouter des points de contact jusqu’à ce que votre séquence soit terminée.

   Vous pouvez **combiner plusieurs points de contact** en faisant glisser un ou plusieurs autres points de contact sur un point de contact.

   >[!NOTE]
   >
   >Plusieurs segments sont reliés par l’opérateur AND, mais plusieurs éléments, tels que des éléments de dimension et des mesures, sont reliés par l’opérateur OR.

   ![](assets/multiple_obj_touchpoint.png)

1. Vous pouvez également **limiter les points de contact individuels pour la prochaine procédure** au sein du chemin (par opposition à un aspect définitif). Sous chaque point de contact, il existe un sélecteur avec les options &quot;Chemin de fin&quot; et &quot;Accès suivant&quot;, comme indiqué ici :

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chemin final </p> <p>(Par défaut) </p> </td> 
   <td colname="col2"> <p>Les sont comptabilisés qui "finiront" par atterrir sur la page suivante du chemin, mais pas nécessairement sur le prochain accès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Accès suivant </p> </td> 
   <td colname="col2"> <p>Les sont comptabilisés qui accèdent à la page suivante dans le chemin du prochain accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paramètres d’abandon {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Paramètre | Description |
|--- |--- |
| d’abandons <ul><li>Visite</li><li>Visitor.</li></ul> | Permet de basculer entre Visite et Visiteur afin d’analyser le cheminement du visiteur. La valeur par défaut est Visiteur.  Ces paramètres permettent de comprendre l’engagement des visiteurs au niveau des visiteurs (à l’échelle de toutes visites) ou de contraindre l’analyse à une seule visite. |
| Afficher « Tous les visiteurs » comme premier point de contact | Désactivez cette option si vous ne souhaitez pas que « Tous les visiteurs » soit le premier point de contact. |

Lorsque vous **cliquez avec le bouton droit de la souris sur un point de contact**, les options suivantes s’affichent :

| Option | Description |
|--- |--- |
| Point de contact de tendance | Voir les données de tendance d’un point de contact dans un graphique linéaire, avec certaines données de détection des anomalies prédéfinies. |
| Point de contact de tendance (%) | Tente le pourcentage total d’abandons. |
| Tendance de tous les points de contact (%) | Applique une tendance à tous les pourcentages des points de contact dans les abandons (à l’exception de &quot;Toutes les visites&quot;, le cas échéant), sur le même graphique. |
| Ventiler les abandons à ce point de contact |  ce que les ont fait entre deux points de contact (ce point de contact et le point de contact suivant) s&#39;ils continuaient jusqu&#39;au point de contact suivant. Un tableau à structure libre présentant les dimensions est ainsi créé. Vous pouvez remplacer des dimensions et d’autres éléments du tableau. |
| Ventiler les abandons à ce point de contact |  ce que les personnes qui n’ont pas réussi à traverser l’entonnoir ont fait immédiatement après l’étape sélectionnée. |
| Créer un segment à partir d’un point de contact | Créez un segment à partir du point de contact sélectionné. |
