---
description: L'intégration des connecteurs de données pour appfigures utilise les variables Analytics pour effectuer le suivi de diverses mesures appfigures.
seo-description: L'intégration des connecteurs de données pour appfigures utilise les variables Analytics pour effectuer le suivi de diverses mesures appfigures.
seo-title: Variables d'intégration Analytics
title: Variables d'intégration Analytics
uuid: 08 d 5 b 714-1 c 97-4 be 6-aae 8-1 f 8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

L'intégration des connecteurs de données pour appfigures utilise les variables Analytics pour effectuer le suivi de diverses mesures appfigures.

Le tableau suivant décrit les variables Analytics activées automatiquement pour l'intégration appfigures.

## Variables obligatoires {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Cette intégration utilise des variables dédiées pour les données de boutique d'applications ; vous n'avez donc pas besoin d'attribuer des variables et des événements de commerce personnalisés.

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| eVar | ID d’objet de la boutique d’applications | Importé à partir d'appfigures. | Configurez cette evar avec l'expiration de visite, l'attribution la plus récente et les sous-subrelations de base. |
| événement (numérique) | Téléchargements de la boutique d’applications | Importé à partir d'appfigures. | Nombre de téléchargements d’applications mobiles. |
| événement (numérique) | Achats de boutique d'applications (dans l'application) | Importé à partir d'appfigures. | Nombre d'options d'achat et d'abonnement intégrées à l'application. |
| événement (numérique) | Classement de la boutique d’applications | Importé à partir d'appfigures. | Utilisé pour définir la mesure calculée appfigures moyenne. Pas utilisé directement. |
| événement (numérique) | Diviseur de classement de la boutique d’applications | Importé à partir d'appfigures. | Utilisé pour définir la mesure calculée appfigures moyenne. Pas utilisé directement. |
| événement (numérique) | Evaluation de la boutique d’applications | Importé à partir d'appfigures. | Utilisé pour définir la mesure calculée appfigures moyenne. Pas utilisé directement. |
| événement (numérique) | Diviseur d’évaluations de la boutique d’applications | Importé à partir d'appfigures. | Utilisé pour définir la mesure calculée appfigures moyenne. Pas utilisé directement. |
| événement (currency) | Recettes de la boutique d'applications (dans l'application) | Importé à partir d'appfigures. | Montant des recettes in-app moins les frais de boutique. |
| événement (currency) | Recettes de la boutique d'applications (une désactivée) | Importé à partir d'appfigures. | Recettes totales provenant des achats d'applications moins les frais de boutique. |
| événement (currency) | Redevances de la boutique d'applications (dans l'application) | Importé à partir d'appfigures. | Inutilisée |
| événement (currency) | Redevances de la boutique d'applications (une désactivée) | Importé à partir d'appfigures. | Inutilisée |

