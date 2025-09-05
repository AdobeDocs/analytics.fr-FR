---
title: Signatures de robots courantes
description: Reconnaissez les identifiants communs des robots.
feature: Bot Removal
role: Admin
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

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

Ceci sʼapplique particulièrement au rapport de lʼagent utilisateur. Comme vous pouvez le voir dans la copie dʼécran ci-dessous, la « version inconnue » de ces navigateurs a presque le même nombre de visiteurs que de visiteurs uniques (et presque le même nombre de pages vues). Cela peut être isolé dans la segmentation en créant un conteneur [!UICONTROL Inclure] pour `Single Page Visits equals Enabled` ou `Hit Depth is less than 2`.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-browsers-unknown.png)

## Nombre de visites égal à 1

Les robots obtiennent généralement un nouvel identifiant visiteur à chaque fois quʼils sʼexécutent, nʼentraînant ainsi quʼune seule visite et tout leur trafic sera constitué dʼun nombre de visites égal à 1.

## Résolutions dʼécran inférieures

Les utilisateurs modernes disposent dʼécrans à résolution beaucoup plus élevée que par le passé. Les accès avec les résolutions suivantes semblent être très populaires pour les robots :

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

En règle générale, les robots nʼajoutent pas de produits à un panier ou n’effectuent pas le passage en caisse. La plupart du temps, ils nʼenvoient pas de formulaire de prospect ou dʼautres événements de succès, mais certains robots envoient des formulaires HTML simples.

## Chaîne de requête spécifique présente

Parfois, les robots tentent de détruire le cache ou dʼendommager les sites en utilisant des URL malformées ou inexistantes (comme les pages dʼadministration LAMP ou Wordpress) ou en ajoutant des chaînes de requête spécifiques.

## Adresses IP provenant de plateformes de calcul distribuées

Les services dʼhébergement Web comme Amazon Web Services ou Google Cloud peuvent être utilisés à mauvais escient comme des fermes de robots. Ces adresses IP risquent fort dʼêtre des robots :
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/) : lʼadresse IP commence par `&#x200B;35.199` ou `35.194&#x200B;`
