---
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics
title: Création d’une suite de rapports
feature: Outils d’administration
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: b7d71e89c427f1f8ffe68beb1e83646c54e92825
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 65%

---

# Création d’une suite de rapports

Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour extraire des rapports. Une entreprise peut avoir plusieurs suites de rapports, contenant chacune différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. L’introduction des [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) et du traitement de la période de rapport permet aux administrateurs de créer vos propres sous-ensembles de données, ce qui offre la possibilité d’obtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs Adobe Analytics afin de les préparer à la collecte de données.

## Conditions préalables

[Guide du premier administrateur d’Adobe Analytics](/help/admin/admin-console/first-admin-guide.md) : Assurez-vous qu’un administrateur au niveau du système vous a accordé l’accès à Adobe Analytics via le Admin Console Experience Cloud.

## Création d’une suite de rapports {#create-report-suite}

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Cliquez sur **[!UICONTROL Nouveau]** > **[!UICONTROL Suite de rapports]**.
1. Pour copier les paramètres d’une suite de rapports, sélectionnez dans la liste des modèles un modèle prédéfini ou une suite de rapports existante à utiliser comme [modèle.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >Seuls les paramètres peuvent être copiés, pas les données. Si le service à la clientèle copie les paramètres, vous devez fournir une confirmation écrite de la clause de non-responsabilité fournie par le service à la clientèle concernant les risques encourus. Voir [Paramètres non copiés depuis une suite de rapports source](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) pour plus d’informations.

1. Renseignez les champs décrits à la section [Nouvelle suite de rapports.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Cliquez sur **[!UICONTROL Créer une suite de rapports]**.

La longueur maximale d’un identifiant de suite de rapports est de 40 octets. Un nom convivial de suite de rapports a une longueur maximale de 255 octets.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Collaborez avec un administrateur au niveau du système de votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

**Une fois connecté à Adobe Analytics, la fenêtre contextuelle « Bienvenue dans Adobe Analytics » ne s’affiche pas.**

Assurez-vous que vous êtes connecté via [Experience Cloud](https://experience.adobe.com) et non via my.omniture.com. En effet, les utilisateurs qui se connectent via my.omniture.com ne disposent pas de l’assistant de configuration de suite de rapports.

## Étapes suivantes

[Créez et configurez une propriété pour Adobe Analytics dans Adobe Experience Platform Launch](/help/implement/launch/create-analytics-property.md) : Créer une zone pour gérer votre implémentation Analytics
