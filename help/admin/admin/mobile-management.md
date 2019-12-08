---
description: L’application de la gestion mobile active les variables des solutions mobiles qui capturent le cycle de vie et d’autres mesures des applications mobiles.
title: Gestion mobile
topic: Admin tools
uuid: d09edf72-bb91-422d-b22c-7b6971f228de
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestion mobile

L’application de la gestion mobile active les variables des solutions mobiles qui capturent le cycle de vie et d’autres mesures des applications mobiles.

Cette intégration entre Adobe Analytics et Mobile Services

* permet de partager vos données IPC (Indicateur de performance clé) provenant de Mobile Services avec Adobe Analytics ;
* permet d’activer le suivi de l’emplacement ;
* ajoute de nouveaux rapports sous Analytics &gt; Rapports &gt; Applications mobiles ;
* ajoute 25 nouvelles classifications Adobe Mobile ;
* ajoute 5 nouvelles mesures Adobe Mobile ;
* ajoute de nouvelles dimensions Adobe Mobile ;
* synchronise les données avec Analytics toutes les 15 minutes

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Suites de rapports]** &gt; **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Gestion mobile]** &gt; **[!UICONTROL Rapports d’applications mobiles**].

## Étape 1. Activation d’App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Activez App Reports v3.0 pour évaluer les mesures suivantes :

* **Acquisition** : suivi des URL de référence pour les campagnes de téléchargement d’applications.
* **Cycle de vie** : niveau de base des rapports fourni par la mesure envoyée à chaque lancement de l’application.
* **Actions de l’application** : rapports et cheminement basés sur les actions in-app.
* **Valeur de durée de vie** : comprenez la manière dont les utilisateurs exploitent la valeur au fil du temps en utilisant des indicateurs de performance clés des applications tels que les achats, vues de publicités, vidéos terminées, partages sur les réseaux sociaux, chargements de photos.
* **Événements minutés** : mesurez la durée qui s’écoule (dans l’application et durée totale) entre les actions clés de l’application, telles que le temps avant le premier achat.

## Étape 2. Activation du suivi de l’emplacement {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

L’activation du suivi de l’emplacement permet :

* d’effectuer le suivi des données de latitude et de longitude et d’en faire un rapport dans Analysis Workspace et Mobile Services ;
* d’identifier, créer et visualiser des points ciblés spécifiques dans Mobile Services. Les points ciblés doivent être définis dans le fichier de configuration du SDK Mobile ;
* d’effectuer le suivi des balises bluetooth (UUID, majeur, mineur et proximité).

## Étape 3. (Facultatif) Activation/désactivation de la création de rapports et de l’attribution héritées pour les accès en arrière-plan {#section_1708BCAA87AA4884986F7532759C5DD4}

L’activation des accès en arrière-plan (accès générés lorsque l’application est en arrière-plan) signifie qu’ils ont été traités comme des accès de premier plan. Ils s’affichent maintenant dans les rapports normaux, ce qui impacte également l’affectation. Cette configuration est généralement souhaitable uniquement pour maintenir la cohérence avec les implémentations héritées.

Au lieu de cela, il est recommandé d’inclure les « accès en arrière-plan » dans une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md). Vous pouvez ainsi afficher les accès mais ils n’affecteront pas défavorablement le nombre de visites et de visiteurs.
Les classifications mobiles sont activées une fois que vous avez activé **[!UICONTROL Gestion mobile]** &gt; **[!UICONTROL Rapports d’applications mobiles]**.

Les classifications permettent de classer des valeurs dans des groupes et de générer des rapports au niveau du groupe. Par exemple, vous pouvez classifier toutes les campagnes de recherches payantes dans une catégorie « termes de pop music » et générer des rapports sur le succès de cette catégorie par rapport à des mesures de type Instances (ou Clics publicitaires), ainsi qu’à la conversion en événements de succès.

| En-tête | Définition |
|--- |--- |
| Date du premier lancement | Date du premier lancement après installation ou réinstallation.   MM/JJ/AAAA |
| ID application | Stocke le nom et la version de l’application au format suivant :   `[AppName] [BundleVersion]`  Par exemple : `myapp 1.1.` |
| Nombre de lancements | Nombre de fois où l’application a été lancée ou mise en premier plan. |
| Jours depuis la première utilisation | Nombre de jours depuis la première exécution. |
| Jours depuis la dernière utilisation | Nombre de jours depuis la dernière exécution. |
| Heure du jour | Mesure l’heure de lancement de l’application suivant le format numérique de 24 heures. Utilisée pour le découpage temporel afin de déterminer les heures hautes d’utilisation. |
| Jour de la semaine | Numéro du jour de la semaine où l’application a été lancée. |
| Nom du périphérique | Stocke le nom de l’appareil.  Chaîne de deux chiffres séparés par une virgule qui identifie l’appareil Le premier chiffre représente généralement la génération de l’appareil, et le second les différents membres de la famille d’appareils. |
| Version du système d’exploitation | Version du système d’exploitation |
| Résolution | Largeur x Hauteur en pixels. |
| Valeur de durée de vie (eVar) | Renseignée par les méthodes trackLifetimeValue. |
| Source de l’acquisition |  |
| Support d’acquisition |  |
| Terme de l’acquisition |  |
| Contenu de l’acquisition |  |
| Nom de l’acquisition |  |
| Lieu (jusqu’à 10 km) | Renseigné par les méthodes trackLocation. |
| Lieu (jusqu’à 100 km) | Renseigné par les méthodes trackLocation. |
| Lieu (jusqu’à 1 m) | Renseigné par les méthodes trackLocation. |
| Nom du point ciblé | Renseigné par les méthodes trackLocation lorsque l’appareil est dans un point ciblé défini. |
| Distance jusqu’au centre du point ciblé | Renseigné par les méthodes trackLocation lorsque l’appareil est dans un point ciblé défini. |
| Identifiant de message in-app |  |
| Message en ligne in-app |  |
| Abonnement push |  |
| ID de données utiles |  |

