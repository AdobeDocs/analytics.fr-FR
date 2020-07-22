---
title: Dimensions mobiles
description: Dimensions basées sur la chaîne user-agent du périphérique.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 4%

---


# Dimensions mobiles

*Cette page fait référence aux propriétés des périphériques mobiles qui accèdent à votre site Web. Si vous souhaitez effectuer le suivi des périphériques sur une application mobile, reportez-vous à la section[Mise en oeuvre d’Analytics pour les périphériques](/help/implement/mobile-device-sdk.md)mobiles dans le guide d’utilisation Mise en oeuvre.*

Les dimensions mobiles fournissent des informations sur les propriétés des périphériques mobiles qui visitent votre site. Vous pouvez utiliser ces dimensions pour mieux comprendre les fonctionnalités prises en charge par un périphérique mobile.

## Renseigner ces dimensions avec des données

Ces dimensions font référence à des règles de recherche internes à Adobe. La valeur de recherche est basée sur l’en-tête `User-Agent` HTTP envoyé avec l’accès. Adobe travaille en partenariat avec [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et les dimensions mobiles. Si vous utilisez une bibliothèque AppMeasurement (par exemple, par le biais du lancement d’Adobe Experience Platform), toutes les dimensions mobiles sont prêtes à l’emploi.

## Descriptions des dimensions mobiles

>[!NOTE]
>
>Les éléments de dimension étiquetés `"None"` sont des périphériques non mobiles. Si vous souhaitez un rapport qui ne comprend que les périphériques mobiles, faites glisser la dimension &quot;Périphérique mobile&quot; dans la zone de segment du canevas de l’espace de travail.

* **Prise en charge** audio mobile : Détermine les formats de fichier que le périphérique peut lire. Example values include `"MP3"`, `"AAC"`, and `"MIDI Monophonic"`. Les valeurs de cette dimension ne s&#39;excluent pas mutuellement ; un accès unique peut être attribué à plusieurs éléments de dimension.
* **Opérateur** de téléphonie mobile : Si l&#39;agent utilisateur contient un périphérique spécifique à l&#39;opérateur, l&#39;opérateur est un élément de dimension. Example values include `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`, and `"Verizon"`.
* **Profondeur** de couleur mobile : Profondeur de couleur du périphérique mobile, en bits.
* **Prise en charge** des cookies mobiles : Détermine si le périphérique mobile prend en charge les cookies. Ce rapport n’indique pas si le navigateur accepte les cookies. Les éléments de dimension incluent `"Supported"`, `"Not supported"`et `"Unknown"`.
* **Périphérique** mobile : Périphérique mobile utilisé par le visiteur.
* **Numéro** du périphérique mobile : Détermine si le périphérique mobile transmet son numéro. Les éléments de dimension incluent `"Supported"`, `"Not supported"`et `"Unknown"`.
* **Type** de périphérique mobile : Type de périphérique mobile. Example values include `"Mobile phone"`, `"Tablet"`, `"Media player"`, and `"Gaming console"`.
* **DRM** mobile : Type de DRM pris en charge par le périphérique mobile. Example values include `"DRM OMA forward"`, `"DRM OMA combined delivery"`, and `"DRM OMA separate delivery"`.
* **Prise en charge** des images mobiles : Types d’images pris en charge par les périphériques mobiles. Example values include `"PNG"`, `"JPEG"`, and `"GIF 87"`. Les valeurs de cette dimension ne s&#39;excluent pas mutuellement ; un accès unique peut être attribué à plusieurs éléments de dimension.
* **services d&#39;information** mobiles : Types de services d’actualités pris en charge par le périphérique. Les périphériques récents ne signalent généralement pas ces informations.
* **Java VM** mobile : Les versions de Java prises en charge par le périphérique.
* **Décoration** du courrier mobile : Détermine si le périphérique prend en charge Decomail, une fonctionnalité autrefois populaire sur les périphériques japonais.
* **Fabricant** de dispositifs portables : Groupe les périphériques mobiles par fabricant. Example values include `"Apple"`, `"Samsung"`, `"Huawei"`, and `"Motorola"`.
* **Longueur** maximale du signet pour mobile : Nombre maximal d’octets pris en charge par le périphérique mobile dans les URL mises en signet. Les périphériques récents n’ont généralement pas de limite.
* **Longueur** maximale d&#39;URL du navigateur mobile : Nombre maximal d’octets pris en charge par le périphérique mobile dans les URL. Les périphériques récents n’ont généralement pas de limite.
* **Longueur** maximale de courrier électronique mobile : Nombre maximal d’octets pris en charge par le périphérique mobile dans un courrier électronique. Les périphériques récents n’ont généralement pas de limite.
* **Protocoles** réseau mobiles : Types de protocole pris en charge par le périphérique lors de l’accès à Internet. Example values include `"EDGE"`, `"GPRS"`, `"UMTS"`, and `"LTE"`.
* **Système d’exploitation mobile (obsolète)**: Utilisez plutôt la dimension Système [](operating-systems.md) d’exploitation.
* **La pression mobile pour parler**: Détermine si le périphérique prend en charge PTT (Push to talk), ce qui permet au périphérique mobile de se comporter comme une radio bidirectionnelle. Les périphériques récents ne signalent généralement pas cette fonctionnalité.
* **Hauteur** d&#39;écran mobile : Hauteur de l’écran, en pixels. Notez que les iPhone génèrent toujours des rapports `"480"` en raison de l’impossibilité de déterminer la version du périphérique iPhone. Reportez-vous à la section ci-dessous pour déterminer la version d’un périphérique iPhone.
* **Taille** d&#39;écran mobile : Dimensions complètes du périphérique mobile en pixels. La taille d’écran figurant dans le rapport n’indique pas l’orientation du dispositif. Quelle que soit l’orientation, chaque dispositif est associé à une résolution d’écran fixe dans le rapport. Cette taille est basée sur des recherches qui déterminent l’orientation la plus probable. You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **Largeur** d&#39;écran mobile : Largeur de l’écran, en pixels.
* **Prise en charge** des vidéos mobiles : Formats de fichiers vidéo et codecs pris en charge par le périphérique mobile. Il existe plusieurs éléments de dimension pour différents codecs de fichiers MP4 et 3GPP. Les valeurs de cette dimension ne s&#39;excluent pas mutuellement ; un accès unique peut être attribué à plusieurs éléments de dimension.

## Séparation de l’iPhone par modèle ou par version

Les périphériques mobiles signalent leur version de microprogramme dans la chaîne de l’agent utilisateur, et non la version du périphérique. Par exemple, un iPhone de nouvelle génération contient un agent utilisateur identique à son iPhone de dernière génération s’il se trouve sur la même version du microprogramme. Comme il n’existe aucun moyen de déterminer la version d’un périphérique iPhone à l’aide de JavaScript, tous les iPhones appartiennent au même compartiment. Les dimensions mobiles sont strictement basées sur les recherches qui référencent l’agent utilisateur. Vous constaterez donc que tous les iPhones signalent une taille d’écran mobile de `320 x 480`.

Si vous souhaitez collecter la version de l’appareil iPhone, vous pouvez contourner cette restriction de deux manières.

* **Utilisez le SDK** iOS : Le SDK mobile contient des dimensions qui exposent la version du périphérique en vue de son utilisation dans le rapports. Cette méthode est plus idéale pour les applications mobiles que pour les sites Web.
* **Utilisez d’autres variables disponibles via JavaScript**: Certaines variables, telles que `screen.height` et `screen.width`, peuvent être utilisées pour déduire la version du périphérique. Par exemple, vous pouvez utiliser le fragment de code suivant sur votre site :

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Ce bloc de code détecte tout d&#39;abord si l&#39;appareil est un iPhone. Si tel est le cas, le code utilise JavaScript pour extraire la résolution d’écran dans une eVar. Cette méthode permet de détecter approximativement la version du périphérique si les résolutions d’écran sont uniques.
