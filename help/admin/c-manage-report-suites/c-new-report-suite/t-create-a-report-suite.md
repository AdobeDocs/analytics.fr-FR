---
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
title: Créer une suite de rapports
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Créer une suite de rapports

Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour extraire des rapports. Une entreprise peut avoir plusieurs suites de rapports, contenant chacune différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. Lʼintroduction des [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr#virtual-report-suites) et du traitement de la période de rapport permet aux administrateurs de créer leurs propres sous-ensembles de données, offrant ainsi la flexibilité dʼobtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs Adobe Analytics afin de les préparer à la collecte de données.

## Conditions préalables

[Guide dʼAdobe Analytics pour le premier administrateur](/help/admin/admin-console/first-admin-guide.md) : assurez-vous qu’un administrateur au niveau du système vous a accordé l’accès à Adobe Analytics via lʼAdmin Console dʼExperience Cloud.

## Créer une suite de rapports {#create-report-suite}

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Cliquez sur **[!UICONTROL Nouveau]** > **[!UICONTROL Suite de rapports]**.
1. Sélectionnez un modèle prédéfini ou une suite de rapports existante à utiliser comme [modèle](../c-report-suite-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Seuls les paramètres peuvent être copiés, pas les données. Si le service à la clientèle copie les paramètres, vous devez fournir une confirmation écrite de la clause de non-responsabilité fournie par le service à la clientèle concernant les risques encourus. Voir [Paramètres non copiés depuis une suite de rapports source](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) pour plus d’informations.

1. Renseignez les champs décrits à la section [Nouvelle suite de rapports.](../c-new-report-suite/new-report-suite.md)
1. Cliquez sur **[!UICONTROL Créer une suite de rapports]**.

Lʼidentifiant de suite de rapports est limité à 40 octets. Le nom convivial dʼune suite de rapports est limité à 255 octets.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Collaborez avec un administrateur au niveau du système de votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

## Étapes suivantes

[Création d’une propriété de balise Adobe Analytics](/help/implement/launch/create-analytics-property.md): Créez une zone pour gérer votre mise en oeuvre Analytics.
