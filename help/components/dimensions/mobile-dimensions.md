---
title: Dimensions de recherche mobile
description: Dimensions basées sur lʼadresse IP et l’agent utilisateur de lʼappareil.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 100%

---

# Dimensions de recherche mobile

*Cette page fait référence aux propriétés des appareils mobiles qui accèdent à votre site web. Voir [Dimensions de cycle de vie mobile](lifecycle-dimensions.md) ou [Mesures de cycle de vie mobiles](../metrics/lifecycle-metrics.md) pour le suivi au sein d’une application mobile.*

Les [dimensions](overview.md) de recherche mobile fournissent des informations sur les propriétés des appareils mobiles qui visitent votre site. Ces propriétés sont basées sur l’agent utilisateur et l’adresse IP de l’accès. Vous pouvez utiliser ces dimensions pour déterminer les fonctionnalités prises en charge par un appareil mobile.

## Renseigner des données dans ces dimensions

Ces dimensions font référence à des règles de recherche qui sont internes à Adobe.

* Pour la dimension [!UICONTROL Opérateur de téléphonie mobile], Adobe s’associe à [Digital Element](https://www.digitalelement.com/) en utilisant NetAcuity pour maintenir les recherches entre l’adresse IP et l’opérateur de téléphonie mobile.
* Pour toutes les autres dimensions mobiles, Adobe s’associe à [DeviceAtlas](https://deviceatlas.com/) pour maintenir les références entre l’agent utilisateur et chaque dimension mobile respective.

La disponibilité de ces dimensions dépend du type d’implémentation :

* Pour les implémentations AppMeasurement, ces dimensions sont prêtes à l’emploi.
* Pour les implémentations du SDK Web, activez [!UICONTROL Recherche géographique] (pour l’opérateur de téléphonie mobile) ou [!UICONTROL Recherche d’appareils] (pour toutes les autres dimensions) lors de la [configuration d’un train de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Descriptions des dimensions mobiles

>[!NOTE]
>
>Les éléments de dimension intitulés `"None"` sont des appareils non mobiles. Si vous souhaitez un rapport qui ne comprend que les appareils mobiles, faites glisser la dimension « Appareil mobile » dans la zone de segment du canevas de Workspace.

* **[!UICONTROL Prise en charge de l’audio sur l’appareil mobile]** : détermine les formats de fichiers que l’appareil peut lire. Les exemples de valeurs comprennent `"MP3"`, `"AAC"` et `"MIDI Monophonic"`. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.
* **[!UICONTROL Opérateur de téléphonie mobile]** : opérateur de téléphonie ou fournisseur de données de l’appareil. Les exemples de valeurs comprennent `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` et `"Verizon"`.
* **[!UICONTROL Profondeur de couleur mobile]** : profondeur de couleur de l’appareil mobile, en bits.
* **[!UICONTROL Prise en charge des cookies sur l’appareil mobile]** : détermine si l’appareil mobile prend en charge les cookies. Cette dimension n’indique pas si le navigateur accepte les cookies. Les éléments de dimension comprennent `"Supported"`, `"Not supported"` et `"Unknown"`.
* **[!UICONTROL Appareil mobile]** : l’appareil mobile utilisé par le visiteur.
* **[!UICONTROL Numéro de l’appareil mobile]** : détermine si l’appareil mobile transmet son numéro. Cette dimension ne fournit pas le numéro de téléphone mobile. Les éléments de dimension comprennent `"Supported"`, `"Not supported"` et `"Unknown"`.
* **[!UICONTROL Type d’appareil mobile]** : le type d’appareil mobile. Les exemples de valeurs comprennent `"Mobile phone"`, `"Tablet"`, `"Media player"` et `"Gaming console"`.
* **[!UICONTROL DRM mobile]** : type de DRM pris en charge par l’appareil mobile. Les exemples de valeurs comprennent `"DRM OMA forward"`, `"DRM OMA combined delivery"` et `"DRM OMA separate delivery"`.
* **[!UICONTROL Prise en charge des images sur l’appareil mobile]** : types d’images pris en charge par les appareils mobiles. Les exemples de valeurs comprennent `"PNG"`, `"JPEG"` et `"GIF 87"`. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.
* **[!UICONTROL Services d’informations mobiles]** : les types de services d’actualités pris en charge par l’appareil. Les appareils modernes n’indiquent généralement pas ces informations.
* **[!UICONTROL Java VM mobile]** : versions de Java prises en charge par l’appareil.
* **[!UICONTROL Décoration d’e-mails sur appareil mobile]** : détermine si l’appareil prend en charge [Decome](https://en.wikipedia.org/wiki/Decome), une fonctionnalité autrefois populaire sur les appareils japonais.
* **[!UICONTROL Fabricant d’appareil mobile]** : regroupe les appareils mobiles par fabricant. Les exemples de valeurs comprennent `"Apple"`, `"Samsung"`, `"Huawei"` et `"Motorola"`.
* **[!UICONTROL Longueur maximale du signet sur l’appareil mobile]** : le nombre maximal d’octets pris en charge par l’appareil mobile dans les adresses URL marquées d’un signet. Les appareils modernes n’ont généralement pas de limite.
* **[!UICONTROL Longueur maximale d’URL de navigateur sur l’appareil mobile]** : nombre maximal d’octets pris en charge par l’appareil mobile dans les URL. Les appareils récents n’ont généralement pas de limite.
* **[!UICONTROL Longueur maximale d’adresse e-mail sur l’appareil mobile]** : nombre maximal d’octets pris en charge par l’appareil mobile dans une adresse e-mail. Les appareils modernes n’ont généralement pas de limite.
* **[!UICONTROL Protocoles réseau de l’appareil mobile]** : les types de protocoles pris en charge par l’appareil lors de l’accès à Internet. Les exemples de valeurs comprennent `"EDGE"`, `"GPRS"`, `"UMTS"` et `"LTE"`.
* **[!UICONTROL Système d’exploitation mobile (obsolète)]** : utilisez plutôt la dimension [Système d’exploitation](operating-systems.md).
* **[!UICONTROL Fonction mobile de pression pour parler]** : détermine si l’appareil prend en charge PTT (Push to talk), ce qui permet à l’appareil mobile de se comporter comme une radio bidirectionnelle. Les appareils récents n’indiquent généralement pas cette fonctionnalité.
* **[!UICONTROL Hauteur d’écran de l’appareil mobile]** : hauteur de l’écran, en pixels. Notez que les iPhone indiquent toujours `"480"`, car il est impossible de déterminer la version de l’appareil iPhone. Reportez-vous à la section ci-dessous pour déterminer la version d’un appareil iPhone.
* **[!UICONTROL Taille de l’écran de l’appareil mobile]** : les dimensions complètes de l’appareil mobile en pixels. La taille d’écran figurant dans le rapport n’indique pas l’orientation de l’appareil. Quelle que soit l’orientation, chaque appareil est associé à une résolution d’écran fixe dans le rapport. Cette taille est basée sur des recherches qui déterminent l’orientation la plus probable. Les tailles, notamment `"768x1024"` et `"1024x768"`, apparaissent dans le même rapport, chacune d’elles représentant un ou plusieurs appareils différents.
* **[!UICONTROL Largeur d’écran de l’appareil mobile]** : la largeur de l’écran, en pixels.
* **[!UICONTROL Prise en charge de la vidéo sur l’appareil mobile]** : les formats de fichiers vidéo et codecs pris en charge par l’appareil mobile. Il existe plusieurs éléments de dimension pour les différents codecs de fichiers MP4 et 3GPP. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.

## Classement des iPhone par modèle ou version

Les appareils mobiles indiquent la version du microprogramme dans leur chaîne d’agent utilisateur au lieu de la version de l’appareil. Par exemple, un iPhone de la génération actuelle contient un agent utilisateur identique à celui de l’iPhone de la génération précédente s’ils utilisent la même version du microprogramme. Comme il n’existe aucun moyen de déterminer la version d’un appareil iPhone à l’aide de JavaScript, tous les iPhone appartiennent au même compartiment. Les dimensions mobiles sont strictement basées sur les recherches qui référencent l’agent utilisateur. Vous constaterez donc que tous les iPhone indiquent une taille d’écran de l’appareil mobile de `320 x 480`.

Si vous souhaitez obtenir la version de l’appareil iPhone, il existe deux façons de contourner cette limite.

* **Utiliser le SDK mobile** : le SDK mobile contient des dimensions qui affichent la version de l’appareil en vue de son utilisation dans les rapports. Cette méthode est plus adaptée aux applications mobiles qu’aux sites Web.
* **Utiliser d’autres variables disponibles via JavaScript** : certaines variables, comme `screen.height` et `screen.width`, peuvent être utilisées pour déduire la version de l’appareil. Par exemple, vous pouvez utiliser le fragment de code suivant sur votre site :

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Ce bloc de code détecte tout d’abord si l’appareil est un iPhone. Si tel est le cas, le code utilise JavaScript pour extraire la résolution d’écran dans une eVar. Cette méthode permet de détecter la version de l’appareil de manière approximative si les résolutions d’écran sont uniques.
