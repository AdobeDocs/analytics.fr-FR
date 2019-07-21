---
description: Les services ou réseaux de diffusion de contenu (CDN), tels que Speedera et Akamai, poussent le contenu Web plus près du bord du réseau. Par conséquent, les documents qui font l’objet de demandes fréquentes restent à proximité de l’emplacement d’accès.
keywords: Mise en œuvre d’Analytics
seo-description: Les services ou réseaux de diffusion de contenu (CDN), tels que Speedera et Akamai, poussent le contenu Web plus près du bord du réseau. Par conséquent, les documents qui font l’objet de demandes fréquentes restent à proximité de l’emplacement d’accès.
seo-title: Services/Réseaux de diffusion de contenu
solution: Analytics
subtopic: Résolution des problèmes
title: Services/Réseaux de diffusion de contenu
topic: Développeur et mise en œuvre
uuid: 6 cb 57 c 59-d 0 f 9-4 ca 5-9 f 15-0 e 74 e 585 a 4 a 1
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Services/Réseaux de diffusion de contenu

Les services ou réseaux de diffusion de contenu (CDN), tels que Speedera et Akamai, poussent le contenu Web plus près du bord du réseau. Par conséquent, les documents qui font l’objet de demandes fréquentes restent à proximité de l’emplacement d’accès.

En règle générale, cela a pour effet de réduire la latence d’accès, l’utilisation de la bande passante et les coûts d’infrastructure.

Le fichier de bibliothèque AppMeasurement pour JavaScript peut être distribué par le biais d’un réseau CDN afin d’optimiser les performances et la remise du fichier au visiteur du site. Les clients Adobe doivent veiller à la configuration correcte de leurs services CDN. Les réseaux CDN expliquent souvent les fluctuations constatées au niveau des temps de téléchargement. Aussi, doivent-ils être considérés comme la cause la plus probable de variations à ce niveau.

Le gestionnaire de balises stocke tout le code JavaScript sur un réseau CDN.
