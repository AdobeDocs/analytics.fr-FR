---
title: Signatures de robots courantes
description: Reconnaissez les identifiants communs des robots.
feature: Bot Removal
role: Admin
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
TQID: 'https://experienceleague.adobe.com/BRcyAaCSCmRppDClCroSL-vGpe7PuU-UEuRhGaKOCHY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: ec140990-1570-4311-94d4-2d6b38511bbe
    internal-label: Bot removal
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 94%
---
# Signatures de robots courantes

Bien que lʼidentification des robots dans un jeu de données soit différente selon lʼenvironnement, voici quelques façons courantes dʼidentifier les robots.

## Nombre élevé de pages vues par visite

Vous pouvez obtenir un rapport Data Warehouse avec lʼadresse IP, les pages vues et les visiteurs uniques. Créez ensuite un calcul dans Excel pour les pages vues par visite et triez-les du plus élevé au plus bas. Les robots ont généralement un nombre très élevé de pages vues par visite (plusieurs centaines ou milliers). Vous constaterez une forte baisse lorsque vous passerez au trafic réel.

## Aucun référent

Les robots nʼont généralement pas dʼURL de référence. Dans la segmentation, cela peut être filtré en tant que `Referring Domain equals Typed/Bookmarked`.

## Agents utilisateurs étranges

Les robots utilisent souvent des agents utilisateurs personnalisés qui ne sont pas classés dans la dimension Navigateurs ou qui sʼaffichent sous la forme dʼune version `unknown` dʼun navigateur standard. Des versions inconnues de Safari et dʼOpera ont une probabilité extrêmement élevée dʼêtre des robots.

## Systèmes dʼexploitation Linux ou « Non spécifié »

Nous ne voulons pas discréditer le formidable système dʼexploitation open-source Linux, mais apparemment les robots aiment le définir comme leur système dʼexploitation. Cependant, faites attention à ne pas exclure le trafic légitime des utilisateurs de Linux. Les robots aiment également ne pas définir de système dʼexploitation, ce qui peut être segmenté en tant que `Operating System &#x200B;equals Not Specified`.

## Pages vues = Visites = Visiteurs uniques

Ceci sʼapplique particulièrement au rapport de lʼagent utilisateur. Comme vous pouvez le voir dans la copie d’écran ci-dessous, la « version inconnue » de ces navigateurs compte presque le même nombre de visiteurs que de visiteurs uniques (et presque le même nombre de pages vues). Cela peut être isolé dans la segmentation en créant un conteneur [!UICONTROL Inclure] pour `Single Page Visits equals Enabled` ou `Hit Depth is less than 2`.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-browsers-unknown.png)

## Nombre de visites égal à 1

Les robots obtiennent généralement un nouvel identifiant visiteur à chaque fois quʼils sʼexécutent, nʼentraînant ainsi quʼune seule visite et tout leur trafic sera constitué dʼun nombre de visites égal à 1.

## Résolutions dʼécran inférieures

Les utilisateurs modernes disposent dʼécrans à résolution beaucoup plus élevée que par le passé. Les hits avec les résolutions suivantes semblent être très populaires pour les robots :

* 1024 x 768&#x200B;&#x200B;
* 1 366 x 768
* 1 600 x 864
* 800 x 600
* 1600 x 1200
* Non spécifié
* 1024 x 667

## Incohérence entre le pays et le fuseau horaire

Vous remarquerez une incohérence entre le pays dʼorigine et le fuseau horaire. Par exemple, lʼemplacement peut être les États-Unis mais le fuseau horaire peut être GMT.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-country-time-zone.png)

## Non connecté

Lʼutilisateur ne se connecte à aucun moment de sa visite et ses eVars dʼidentification utilisateur ne sont pas conservés des visites précédentes. Si certains robots peuvent être configurés pour sʼauthentifier, la majorité dʼentre eux ne sont pas aussi intelligents.

## Aucun KPI lors de la visite

En règle générale, les robots nʼajoutent pas de produits à un panier ou n’effectuent pas le passage en caisse. La plupart du temps, ils n’envoient pas de formulaires de prospect ou d’autres événements de succès, mais certains robots envoient des formulaires HTML simples. &#x200B;

## Chaîne de requête spécifique présente

Des robots tentent parfois de contourner le cache ou de perturber les sites en générant des hits sur des URL mal formées ou inexistantes (comme les pages d’administration LAMP ou WordPress classiques), ou en ajoutant des chaînes de requête spécifiques.

## Adresses IP provenant de plateformes de calcul distribuées

Les services dʼhébergement web comme Amazon Web Services ou Google Cloud peuvent être exploités de manière abusive comme fermes de robots. Ces adresses IP présentent un risque élevé d’être des robots :
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/) : lʼadresse IP commence par `&#x200B;35.199` ou `35.194&#x200B;`
