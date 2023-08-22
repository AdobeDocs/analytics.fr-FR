---
description: Consultez et gérez les rapports planifiés de l’ensemble de l’organisation.
title: Gestionnaire de projets planifiés
feature: Admin Tools
source-git-commit: 8d0cf795b0366b2797fa0574ae9faaffb76b005e
workflow-type: ht
source-wordcount: '414'
ht-degree: 100%

---

# Projets planifiés

Les projets Analysis Workspace planifiés peuvent être gérés sous **Analytics > Composants > Projets planifiés**.

Dans le cadre de la gestion de projets planifiés, vous pouvez modifier et supprimer les plannings de projets récurrents. Utilisez la barre de recherche ou les options de filtre dans le rail de gauche pour rechercher un planning. Vous pouvez filtrer par [!UICONTROL Balises], [!UICONTROL Propriétaires], [!UICONTROL Favoris], etc.

![](assets/scheduled-project-manager2.png)

## Colonnes disponibles

| Champ | Description |
| --- | --- |
| [!UICONTROL Favoris] | Sélectionnez l’icône en forme d’étoile pour marquer ce planning comme favori. |
| [!UICONTROL Identifiant de planning] | Cet identifiant est principalement utilisé à des fins de débogage. |
| [!UICONTROL Titre et description] | Titre et description de ce projet. |
| [!UICONTROL Propriétaire] | Personne qui a créé le projet et qui en est propriétaire. |
| [!UICONTROL Balises] | (facultatif) Le balisage est un moyen efficace d’organiser les projets. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un projet. Néanmoins, vous ne pouvez afficher les balises que pour les projets que vous possédez ou qui ont été partagés avec vous. |
| [!UICONTROL Distribué à] | Le ou les personnes destinataires de ce projet planifié. |
| [!UICONTROL Date d’expiration] | Pour toute fréquence de projet planifié, vous pouvez définir la date d’expiration jusqu’à un an au maximum. |
| [!UICONTROL Fréquence] | Fréquence à laquelle vous souhaitez envoyer ce projet planifié aux personnes destinataires. |
| [!UICONTROL Heure d’exécution] | Heure à laquelle ce projet planifié est envoyé. |
| [!UICONTROL Nombre de requêtes] | Nombre de requêtes concernant ce projet. |

## Actions courantes

Actions courantes du Gestionnaire de projets planifiés :

| Action | Description |
|---|---|
| **[!UICONTROL Modifier]** | Cliquez sur le titre du planning pour mettre à jour les paramètres de diffusion. |
| **[!UICONTROL Supprimer]** | Sélectionnez le projet planifié dans la liste, puis cliquez sur Supprimer dans le menu. Cela supprime le planning sélectionné pour le projet ; le projet lui-même n’est pas supprimé. |
| **[!UICONTROL Balise]** | Sélectionnez le projet planifié dans la liste, puis « Balise » ou « Approuver » pour organiser vos plannings et faciliter les recherches. |
| **[!UICONTROL Afficher les plannings échoués]** | Accédez au rail de gauche > Autres filtres > Échec pour afficher les plannings qui ont échoué. |
| **[!UICONTROL Afficher les plannings expirés]** | Accédez au rail de gauche > Autres filtres > Expiré pour afficher les plannings qui ont expiré. Cliquez sur le titre du planning pour configurer une nouvelle diffusion. |
| **[!UICONTROL Afficher l’ID de planning]** | Accédez aux options relatives aux colonnes dans le coin supérieur droit et ajoutez la colonne ID de planning dans le tableau. L’ID planifié est souvent utile pour le débogage. |

Le Gestionnaire de projets planifiés affiche les éléments créés par un utilisateur ou une utilisatrice spécifique. Si le compte d’utilisateur ou d’utilisatrice est désactivé dans l’application, toutes les livraisons planifiées sont interrompues. La propriété du projet planifié peut être transférée à un nouvel utilisateur ou à une nouvelle utilisatrice sous **Admin** > **Utilisateurs et ressources Analytics** > **Transférer les ressources**.