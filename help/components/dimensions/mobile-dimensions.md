---
title: Dimensions mobiles
description: Dimensions basées sur lʼadresse IP de lʼappareil.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 97%

---

# Dimensions mobiles

*Cette page fait référence aux propriétés des appareils mobiles qui accèdent à votre site Web. Si vous souhaitez effectuer le suivi des appareils sur une application mobile, consultez [Mise en œuvre d’Analytics pour les appareils mobiles](/help/implement/mobile-device-sdk.md) dans le guide d’utilisation de la mise en œuvre.*

Mobile [dimensions](overview.md) fournir des informations sur les propriétés des appareils mobiles qui visitent votre site. Vous pouvez utiliser ces dimensions pour déterminer les fonctionnalités prises en charge par un appareil mobile.

## Renseignement des données dans ces dimensions

Ces dimensions font référence à des règles de recherche qui sont internes à Adobe. La recherche de lʼ[!UICONTROL opérateur de téléphonie mobile] est déterminée par lʼadresse IP, à lʼaide des données que nous obtenons de NetAcuity (un produit Digital Elements).
Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), toutes les dimensions mobiles sont prêtes à l’emploi.

## Descriptions des dimensions mobiles

>[!NOTE]
>
>Les éléments de dimension intitulés `"None"` sont des appareils non mobiles. Si vous souhaitez un rapport qui ne comprend que les appareils mobiles, faites glisser la dimension « Appareil mobile » dans la zone de segment du canevas de Workspace.

* **Prise en charge de l’audio sur l’appareil mobile** : détermine les formats de fichiers que l’appareil peut lire. Les exemples de valeurs comprennent `"MP3"`, `"AAC"` et `"MIDI Monophonic"`. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.
* **Opérateur de téléphonie mobile** : les valeurs de cette dimension sont renseignées en recherchant des données tierces (Digital Elements) sur la base des adresses IP capturées par Analytics. Les exemples de valeurs comprennent `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` et `"Verizon"`.
* **Profondeur de couleur mobile** : profondeur de couleur de l’appareil mobile, en bits.
* **Prise en charge des cookies sur l’appareil mobile** : détermine si l’appareil mobile prend en charge les cookies. Ce rapport n’indique pas si le navigateur accepte les cookies. Les éléments de dimension comprennent `"Supported"`, `"Not supported"` et `"Unknown"`.
* **Appareil mobile** : l’appareil mobile utilisé par le visiteur. **Remarque**: Digital Elements publie régulièrement des mises à jour pour reconnaître les appareils nouveaux ou mis à jour.
* **Numéro de l’appareil mobile** : détermine si l’appareil mobile transmet son numéro. Les éléments de dimension comprennent `"Supported"`, `"Not supported"` et `"Unknown"`.
* **Type d’appareil mobile** : le type d’appareil mobile. Les exemples de valeurs comprennent `"Mobile phone"`, `"Tablet"`, `"Media player"` et `"Gaming console"`.
* **DRM mobile** : le type de DRM pris en charge par l’appareil mobile. Les exemples de valeurs comprennent `"DRM OMA forward"`, `"DRM OMA combined delivery"` et `"DRM OMA separate delivery"`.
* **Prise en charge des images sur l’appareil mobile** : les types d’images pris en charge par les appareils mobiles. Les exemples de valeurs comprennent `"PNG"`, `"JPEG"` et `"GIF 87"`. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.
* **Services d’informations mobiles** : les types de services d’actualités pris en charge par l’appareil. Les appareils récents n’indiquent généralement pas ces informations.
* **Java VM mobile** : les versions de Java prises en charge par l’appareil.
* **Décoration du courrier sur l’appareil mobile** : détermine si l’appareil prend en charge Decomail, une fonctionnalité autrefois populaire sur les appareils japonais.
* **Fabricant de l’appareil mobile** : regroupe les appareils mobiles par fabricant. Les exemples de valeurs comprennent `"Apple"`, `"Samsung"`, `"Huawei"` et `"Motorola"`.
* **Longueur maximale du signet sur l’appareil mobile** : le nombre maximal d’octets pris en charge par l’appareil mobile dans les adresses URL marquées d’un signet. Les appareils récents n’ont généralement pas de limite.
* **Longueur maximale d’URL de navigateur sur l’appareil mobile** : le nombre maximal d’octets pris en charge par l’appareil mobile dans les adresses URL. Les appareils récents n’ont généralement pas de limite.
* **Longueur maximale d’adresse e-mail sur l’appareil mobile** : le nombre maximal d’octets pris en charge par l’appareil mobile dans une adresse e-mail. Les appareils récents n’ont généralement pas de limite.
* **Protocoles réseau de l’appareil mobile** : les types de protocoles pris en charge par l’appareil lors de l’accès à Internet. Les exemples de valeurs comprennent `"EDGE"`, `"GPRS"`, `"UMTS"` et `"LTE"`.
* **Système d’exploitation mobile (obsolète)** : utilisez plutôt la dimension [Système d’exploitation](operating-systems.md).
* **Fonction mobile de pression pour parler** : détermine si l’appareil prend en charge PTT (Push to talk), ce qui permet à l’appareil mobile de se comporter comme une radio bidirectionnelle. Les appareils récents ne signalent généralement pas cette fonctionnalité.
* **Hauteur d’écran de l’appareil mobile** : la hauteur de l’écran, en pixels. Notez que les iPhone indiquent toujours `"480"`, car il est impossible de déterminer la version de l’appareil iPhone. Reportez-vous à la section ci-dessous pour déterminer la version d’un appareil iPhone.
* **Taille de l’écran de l’appareil mobile** : les dimensions complètes de l’appareil mobile en pixels. La taille d’écran figurant dans le rapport n’indique pas l’orientation de l’appareil. Quelle que soit l’orientation, chaque appareil est associé à une résolution d’écran fixe dans le rapport. Cette taille est basée sur des recherches qui déterminent l’orientation la plus probable. Les tailles, notamment `"768x1024"` et `"1024x768"`, apparaissent dans le même rapport, chacune d’elles représentant un ou plusieurs appareils différents.
* **Largeur d’écran de l’appareil mobile** : la largeur de l’écran, en pixels.
* **Prise en charge de la vidéo sur l’appareil mobile** : les formats de fichiers vidéo et codecs pris en charge par l’appareil mobile. Il existe plusieurs éléments de dimension pour les différents codecs de fichiers MP4 et 3GPP. Les valeurs de cette dimension ne s’excluent pas mutuellement. Un accès unique peut être attribué à plusieurs éléments de dimension.

## Classement des iPhone par modèle ou version

Les appareils mobiles indiquent la version du microprogramme dans leur chaîne d’agent utilisateur au lieu de la version de l’appareil. Par exemple, un iPhone de la génération actuelle contient un agent utilisateur identique à celui de l’iPhone de la génération précédente s’ils utilisent la même version du microprogramme. Comme il n’existe aucun moyen de déterminer la version d’un appareil iPhone à l’aide de JavaScript, tous les iPhone appartiennent au même compartiment. Les dimensions mobiles sont strictement basées sur les recherches qui référencent l’agent utilisateur. Vous constaterez donc que tous les iPhone indiquent une taille d’écran de l’appareil mobile de `320 x 480`.

Si vous souhaitez obtenir la version de l’appareil iPhone, il existe deux façons de contourner cette limite.

* **Utiliser le SDK iOS** : le SDK mobile contient des dimensions qui affichent la version de l’appareil en vue de son utilisation dans les rapports. Cette méthode est plus adaptée aux applications mobiles qu’aux sites Web.
* **Utiliser d’autres variables disponibles via JavaScript** : certaines variables, comme `screen.height` et `screen.width`, peuvent être utilisées pour déduire la version de l’appareil. Par exemple, vous pouvez utiliser le fragment de code suivant sur votre site :

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Ce bloc de code détecte tout d’abord si l’appareil est un iPhone. Si tel est le cas, le code utilise JavaScript pour extraire la résolution d’écran dans une eVar. Cette méthode permet de détecter la version de l’appareil de manière approximative si les résolutions d’écran sont uniques.
