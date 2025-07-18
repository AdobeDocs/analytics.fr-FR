---
description: Découvrez l’extension Activity Map et comment naviguer dans son interface.
title: Interface de l’extension Activity Map
uuid: f6734b60-0b77-4f50-a45a-6a6936d1524e
feature: Activity Map
role: User, Admin
exl-id: 461abda1-3238-4a32-b9d3-5a57b00cf0d3
source-git-commit: 19c2c1abd7f1799598597c0e696d0b001c1ef0ea
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 1%

---

# Interface de l’extension Activity Map

L’interface de l’extension Activity Map se compose de deux parties :

* Un panneau supérieur qui vous permet de configurer l’extension et les rapports
* Recouvrement qui affiche les liens les plus populaires
* Un panneau inférieur qui affiche les mesures des liens les plus populaires

## Panneau supérieur

Le panneau supérieur contient vos commandes de base pour le recouvrement Activity Map.

![Recouvrement](../assets/overlay.png)

Il propose les paramètres suivants :

* **Affichage standard/en direct** : permet de basculer entre les affichages standard et en direct.
   * Vue standard : affiche la superposition en fonction des données historiques.
   * Vue dynamique : affiche la superposition en fonction des données dynamiques. Le sélecteur de date se transforme en menu déroulant qui vous permet de modifier la granularité des données actives.
* **Sélecteur de mesure** : permet de modifier la mesure signalée par le recouvrement. Seuls les [!UICONTROL clics sur les liens] sont disponibles si la vue active est sélectionnée.
* **Sélecteur de segment** : vous permet de sélectionner un [segment](/help/components/segmentation/seg-overview.md), en affichant un sous-ensemble de données dans votre recouvrement. Les segments ne sont pas disponibles dans la vue active.
* **Type de visualisation de recouvrement** : permet de modifier la manière dont le recouvrement visualise le classement des liens.
   * **[!UICONTROL Bulle]** : les liens supérieurs reçoivent une bulle verte indiquant son rang numérique au cours de la période de rapport. Vous pouvez modifier la couleur de la bulle dans [Paramètres](settings.md).
   * **[!UICONTROL Dégradé]** : les liens supérieurs apparaissent ombrés en rouge transparent. Les liens les plus populaires sont le rouge le plus foncé. Vous pouvez modifier la couleur du dégradé dans [Paramètres](settings.md).
   * **[!UICONTROL Désactivé]** : désactive les recouvrements de liens.
* **Sélecteur de date** : permet de modifier la période de création des rapports.

L’en-tête de ce panneau contient les paramètres suivants :

* **Développer/réduire le panneau supérieur** : active/désactive le panneau supérieur pour afficher les paramètres horizontalement ou verticalement (icône de double flèche).
* **[!UICONTROL Activer/désactiver les détails de la page]** : affiche ou masque le panneau inférieur (icône représentant un œil).
* **[!UICONTROL Afficher les paramètres]** : ouvre un menu pour les paramètres que vous pouvez modifier (icône d’engrenage) :
   * **[!UICONTROL Settings]** : ouvre le [Settings](settings.md) de l’extension.
   * **[!UICONTROL Aide]** : ouvre la documentation sur Experience League (cette page).
   * **[!UICONTROL Communauté Adobe]** : ouvre la [communauté Experience League](https://experienceleaguecommunities.adobe.com/?profile.language=fr).
   * **[!UICONTROL À propos]** : affiche la version de l’extension.
   * **[!UICONTROL Déconnexion]** : vous déconnecte de l’extension, ce qui vous oblige à vous reconnecter.
* **[!UICONTROL Quitter Activity Map]** : ferme tous les recouvrements de l’extension (icône X).

## Recouvrement de page

Le recouvrement de page contient le contenu de votre site avec un recouvrement qui vous indique l’emplacement des liens les plus populaires sur lesquels l’utilisateur a cliqué au cours de la période de création de rapports. Vous pouvez configurer ces recouvrements de liens pour qu’ils apparaissent sous forme de bulles ou de dégradés dans le **[!UICONTROL type de visualisation de recouvrement]** du panneau supérieur.

Si vous cliquez sur une bulle ou un dégradé, vous pouvez afficher les détails de ce lien spécifique.

![Bulle de lien](../assets/link-bubble.png)

## Panneau inférieur

Le panneau inférieur affiche une vue agrégée des liens affichés sur le recouvrement.

* **Type de rapport** : basculez le panneau inférieur pour afficher le rapport **[!UICONTROL Liens sur la page]** ou le rapport **[!UICONTROL Détails sur la page]**.
* **[!UICONTROL Nom de la page]** : nom actuel de la dimension [Page](/help/components/dimensions/page.md).
* **[!UICONTROL Rechercher]** : filtrez le rapport afin d’afficher uniquement les noms de lien correspondant au texte saisi.
* **[!UICONTROL Télécharger]** : exporte le rapport au format CSV. Vous pouvez inclure le rapport [!UICONTROL Liens sur la page], le rapport [!UICONTROL Page] et le rapport [!UICONTROL Flux de page] dans le même fichier de téléchargement.
* **[!UICONTROL Modifier la position d’ancrage du rapport]** : permet d’activer ou de désactiver l’affichage de ce panneau dans la partie inférieure ou supérieure de la fenêtre du navigateur.
* **[!UICONTROL Fermer le rapport]** : ferme ce panneau. Vous pouvez ouvrir à nouveau le panneau à l’aide du bouton **[!UICONTROL Activer/désactiver les détails de la page]** dans le panneau supérieur (l’icône représentant un œil).

Le rapport **[!UICONTROL Liens sur la page]** affiche un rapport d’espace de travail de base avec les paramètres suivants :

* La dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md)
* La mesure [Occurrences](/help/components/metrics/occurrences.md) (libellée **[!UICONTROL Clics sur les liens]**)
* Valeur actuelle [Page](/help/components/dimensions/page.md) appliquée en tant que segment

![Liens dans le panneau Page](../assets/links-on-page.png)

Le rapport **[!UICONTROL Détails de la page]** affiche une visualisation [Flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) à l’aide de la dimension [Page](/help/components/dimensions/page.md), en se concentrant sur la page active. Les mesures suivantes pour la page active sont affichées à gauche :

* Total [pages vues](/help/components/metrics/page-views.md)
* [!UICONTROL &#x200B; % de toutes les pages vues]
* [Entrée](/help/components/metrics/entries.md) nombre
* Nombre de [Sorties](/help/components/metrics/exits.md)
* [Visites de page unique](/help/components/metrics/single-page-visits.md)
* [!UICONTROL Nombre moyen de clics sur la page]
* Moy. [temps passé sur la page](/help/components/metrics/time-spent.md)
* Nombre de [rechargements](/help/components/metrics/reloads.md)
* [Taux de rebond](/help/components/metrics/bounce-rate.md)
* [!UICONTROL Clics sur les liens]

![Détails de la page](../assets/page-details.png)
