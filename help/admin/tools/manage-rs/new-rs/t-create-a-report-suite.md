---
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
title: Créer une suite de rapports
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
TQID: 'https://experienceleague.adobe.com/ZmPcYHvXOhaXXnqsSVUh1bpvignxomS3d4S76iMCAa4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 87%
---
# Créer une suite de rapports

Une suite de rapports est un silo de données qu’Adobe Analytics utilise pour générer des rapports. Une entreprise peut avoir plusieurs suites de rapports, contenant chacune différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. Lʼintroduction des [suites de rapports virtuelles](/help/components/vrs/vrs-about.md#virtual-report-suites) et du traitement de la période de rapport permet aux administrateurs de créer leurs propres sous-ensembles de données, offrant ainsi la flexibilité dʼobtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs Adobe Analytics afin de les préparer à la collecte de données.

## Conditions préalables

[Guide de premier administrateur d’Adobe Analytics &#x200B;](/help/admin/admin-console/first-admin-guide.md) : assurez-vous qu’un administrateur au niveau du système vous a accordé l’accès à Adobe Analytics via CX Enterprise Admin Console.

## Créer une suite de rapports {#create-report-suite}

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Cliquez sur **[!UICONTROL Ajouter une suite de rapports]**.
1. Sélectionnez un modèle prédéfini ou une suite de rapports existante à utiliser comme [modèle](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Seuls les paramètres peuvent être copiés, pas les données. Si l’Assistance clientèle copie les paramètres, vous devez fournir une confirmation écrite de la clause de non-responsabilité fournie par l’Assistance clientèle concernant les risques encourus. Pour plus d’informations, consultez [Paramètres non copiés depuis une suite de rapports source](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md).

1. Renseignez les champs décrits à la section [Nouvelle suite de rapports](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
1. Cliquez sur **[!UICONTROL Créer une suite de rapports]**.

Lʼidentifiant de suite de rapports est limité à 40 octets. Le nom convivial dʼune suite de rapports est limité à 255 octets.

## Résolution des problèmes

**Après vous être connecté à CX Enterprise, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Collaborez avec un administrateur au niveau du système de votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

## Étapes suivantes

[Créer une propriété de balise Adobe Analytics](/help/implement/launch/create-analytics-property.md) : créez une zone pour gérer l’implémentation Analytics.
