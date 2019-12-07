---
description: Dans la mesure où le suivi des appareils s’effectue via une balise Web, tout comme les autres visiteurs, la plupart des rapports sont disponibles et corrects.
keywords: Analytics Implementation;reports;mobile protocols;search engines;search keywords;referring domains;referrers;geosegmentation;domains;connection type;time zone;cookies;java;javascript;monitor colors;monitor resolution;browser width;height;netscape plug-in
title: Rapports pour les appareils qui utilisent des protocoles mobiles
topic: Developer and implementation
uuid: 4aab125d-c131-4402-9bc8-1c7fd1bb2bee
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapports pour les appareils qui utilisent des protocoles mobiles

Dans la mesure où le suivi des appareils s’effectue via une balise Web, tout comme les autres visiteurs, la plupart des rapports sont disponibles et corrects.

[!DNL VISTA] peut être utilisé pour modifier les données collectées à partir des méthodes standard et pour périphériques mobiles. Tous les rapports [!UICONTROL d’aperçu] [!UICONTROL personnalisé] ([!UICONTROL prop] et [!UICONTROL eVar]), [!UICONTROL Evénement], [!UICONTROL Trafic du site] et sur le [!UICONTROL cheminement] sont pris en charge.

## Moteurs de recherche, mots-clés de recherche, domaines référents et référents {#section_184D2EF9D906443FBDED04A09CDC50E9}

Ces rapports ne contiennent des données que si le référent est renseigné dans la demande d’image envoyée à partir de la page mobile. Le référent est renseigné via le paramètre de chaîne de requête « r », comme décrit dans le livre blanc Implémentation sans JavaScript. Vous devez également transférer manuellement les informations sur le référent dans une demande d’image.

Le paramètre de chaîne de requête 'r' doit inclure le protocole du référent. Si le protocole est omis, le rapport du référent n’est pas rempli. Par exemple, utilisez `r=https://msn.com`, et non `r=msn.com`.

## Géosegmentation et domaines {#section_2B4E9443AAFE4ECA961F9E993592E628}

Les rapports sur la géosegmentation reposent sur l’adresse IP du périphérique qui envoie la demande. Dans la mesure où les périphériques mobiles dépendent d’une passerelle pour demander des images à partir des serveurs Adobe, l’adresse IP de la passerelle est utilisée pour déterminer l’emplacement géographique de l’utilisateur. Comme les passerelles et leur adresse IP sont enregistrées pour de vastes réseaux, les emplacements géographiques associés sont souvent moins précis.

Les domaines reposent également sur l’adresse IP de la passerelle, ce qui signifie que le rapport sur les domaines contient souvent le nom de l’opérateur qui possède la passerelle. En raison des opérateurs de réseaux mobiles virtuels (MVNO), cette information peut ne pas être précise.

## Types de connexion {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe entretient une plage connue d’adresses IP qui appartiennent à des opérateurs de téléphonie mobile. Lorsqu’un accès est reçu depuis une plage d’adresses IP qui appartient à un opérateur de téléphonie mobile connu, l’accès s’affiche en tant qu’« opérateur de téléphonie mobile » dans le rapport de type de connexion. Sinon, le trafic mobile est répertorié sous « Réseau local/Wi-Fi ».

## Fuseaux horaires, Cookies, Java, JavaScript, couleurs et résolutions des moniteurs, largeur et hauteur du navigateur et modules externes Netscape {#section_158C848273AE4691B4413767E849E846}

Ces rapports sont tous collectés à l’aide de JavaScript afin de détecter des paramètres spécifiques du navigateur. Comme JavaScript n’est pas utilisé pour créer la balise Web d’image sur les appareils mobiles, les données collectées à partir des utilisateurs mobiles ne sont pas incluses dans ces rapports.
