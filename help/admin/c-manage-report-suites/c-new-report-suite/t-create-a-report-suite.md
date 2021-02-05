---
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics
title: Création d’une suite de rapports
topic: Admin tools
translation-type: tm+mt
source-git-commit: 8ddd49ad894547d888efc513983e615d138ed13c
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 77%

---


# Création d’une suite de rapports

Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour extraire des rapports. Une entreprise peut avoir plusieurs suites de rapports, contenant chacune différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. L&#39;introduction de [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) et le traitement du temps des rapports permettent aux administrateurs de créer vos propres sous-ensembles de données, ce qui vous permet d&#39;obtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs Analytics afin de les préparer à la collecte de données.

## Conditions préalables

[Guide](/help/admin/admin-console/first-admin-guide.md) d’administration de l’Adobe Analytics First Admin : Assurez-vous qu’un administrateur de niveau système vous a accordé l’accès à Adobe Analytics par l’intermédiaire de l’Admin Console Experience Cloud.

## Création d’une suite de rapports {#create-report-suite}

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Cliquez sur **[!UICONTROL Nouveau]** > **[!UICONTROL Suite de rapports]**.
1. Pour copier les paramètres d’une suite de rapports, sélectionnez dans la liste des modèles un modèle prédéfini ou une suite de rapports existante à utiliser comme [modèle.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >Seuls les paramètres peuvent être copiés, pas les données. Si le service à la clientèle copie les paramètres, vous devez fournir une confirmation écrite de la clause de non-responsabilité fournie par le service à la clientèle concernant les risques encourus. Voir [Paramètres non copiés depuis une suite de rapports source](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) pour plus d’informations.

1. Renseignez les champs décrits à la section [Nouvelle suite de rapports.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Cliquez sur **[!UICONTROL Créer une suite de rapports]**.

La longueur maximale d’un identifiant de suite de rapports est de 40 octets. Le nom convivial d’une suite de rapports ne doit pas dépasser 255 octets.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Collaborez avec un administrateur au niveau du système de votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

**Une fois connecté à Adobe Analytics, la fenêtre contextuelle « Bienvenue dans Adobe Analytics » ne s’affiche pas.**

Vérifiez que vous vous êtes connecté via Experience Cloud et non via my.omniture.com. En effet, les utilisateurs qui se connectent via my.omniture.com ne disposent pas de l’assistant de configuration de suite de rapports.

## Étapes suivantes

[Créer et configurez une propriété pour Adobe Analytics dans Launch](/help/implement/launch/create-analytics-property.md) : Créer une zone pour gérer votre implémentation Analytics