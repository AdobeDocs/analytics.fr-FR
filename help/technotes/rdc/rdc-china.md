---
title: Collecte de données régionale pour la Chine
seo-title: Adobe Analytics Chine RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Collecte de données régionale pour la Chine

La collecte de données régionale d’Adobe (RDC) en Chine continentale permet aux clients d’envoyer des données directement à un centre de collecte de données (DCC) en Chine plutôt qu’ailleurs dans le monde. Cela améliore le temps de chargement des pages et la précision des données par rapport à l’envoi de données à des centres de collecte de données situés en dehors de Chine.

> [!IMPORTANT] L'utilisation du nœud Chine RDC engendre des coûts supplémentaires. Avant de mettre en œuvre la collecte de données en Chine à l'aide du nœud de collecte de données régionale décrit dans ce document, contactez le gestionnaire de compte de votre organisation pour vérifier que vous êtes bien autorisé à accéder à cette fonctionnalité.

## Définition du serveur de suivi pour la Chine

Le suivi peut être réalisé sur la RDC Chine à n’importe quel moment convenable pour votre service. Pour une propriété numérique (telle qu'une application mobile ou une page Web) que vous souhaitez acheminer vers la collecte de données régionale de Chine, changez le serveur de suivi en :

`<namespace>.sc.adobedc.cn`

Veillez à insérer l’espace de noms correct. Cela se trouve généralement au début de votre serveur de suivi existant. For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. Vous pouvez également désigner un enregistrement propriétaire [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) non SSL à ce nouvel emplacement.

Ne définissez pas la valeur trackingserver globalement, pour toutes les propriétés et régions, sur la CRD Chine si une partie importante de votre base de clients est en dehors de la Chine. Le trackingServer doit être défini sur la valeur de la RDC Chine uniquement pour les clients qui se trouvent en Chine. Sinon, cela affectera négativement la vitesse pour vos utilisateurs en dehors de Chine, car cela forcera la collecte de données à aller en Chine et à revenir pour une réponse.

## Identification des utilisateurs en Chine

Quel que soit l’endroit où votre propriété numérique est hébergée ou la langue qu’elle utilise, vos utilisateurs en Chine connaîtront des améliorations si vous utilisez le nœud RDC en Chine. Par conséquent, il est recommandé de déterminer les utilisateurs qui se trouvent en Chine, puis d’utiliser la RDC Chine pour ces utilisateurs. Les méthodes qui peuvent vous aider à identifier ces utilisateurs sont les suivantes :

* Utilisation d'une solution geoip fiable. Vous pouvez décider d'utiliser une solution côté serveur pour intégrer facilement à Adobe Experience Platform Launch (ou la gestion des balises de données). Dans ce cas, l'emplacement peut être déterminé en incluant un élément de données standard dans l'objet de lancement ou de gestion dynamique des balises d'Experience Platform. Vous pouvez également utiliser une solution GeoIP côté client. Dans ce cas, le lancement de Platform Platform peut être ancré dans le code client. Notez que de telles solutions peuvent impliquer d’inviter l’utilisateur à accéder au site localisé. Cela risque de représenter un risque que la première page soit comptabilisée par le serveur de suivi global et la deuxième par celle de Chine, ce qui peut entraîner une visite comptée deux fois. Suivez les meilleures pratiques pour les solutions GeoIP. Adobe n’est pas responsable de la précision de la solution GeoIP utilisée.

* Using site structure or the browser language (the `navigator.language / accept-language` header). L’avantage de cette méthode est un coût inférieur et éventuellement une meilleure performance. L’inconvénient de cette méthode est que les visiteurs de langue chinoise hors de Chine sont soumis à des vitesses affectées négativement.
* Utilisation d'une solution d'hébergement basée en Chine et définition de trackingserver en Chine en fonction de votre hôte. Cela augmentera également considérablement la vitesse.

## Restrictions actuelles

Les limites actuelles de la collecte de données régionale pour la Chine :

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
2. Bien que [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) et [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) soient pris en charge, les domaines Target et Demdex ne se trouvent pas actuellement en Chine continentale et n’auront pas les mêmes avantages en termes de rapidité ou de fiabilité que ceux de la RDC Chine.

## Engagement d’Adobe en Chine

Adobe prévoit de conserver définitivement la RDC Chine et d’y ajouter des fonctionnalités telles que le protocole propriétaire SSL et le système de transfert côté serveur. De plus, Adobe prévoit de fournir un domaine de demdex (ou équivalent) en Chine pour assurer la prise en charge complète de la collection ECID et Audience Manager depuis la Chine. Les clients qui utilisent la RDC Chine d’Adobe sont les bienvenus pour continuer à utiliser ce point de terminaison de collecte de données indéfiniment.
