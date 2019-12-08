---
description: Les services ou réseaux de diffusion de contenu (CDN), tels que Speedera et Akamai, poussent le contenu Web plus près du bord du réseau. Par conséquent, les documents qui font l’objet de demandes fréquentes restent à proximité de l’emplacement d’accès.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Services et réseaux de diffusion de contenu
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Services et réseaux de diffusion de contenu

Les services ou réseaux de diffusion de contenu (CDN), tels que Speedera et Akamai, poussent le contenu Web plus près du bord du réseau. Par conséquent, les documents qui font l’objet de demandes fréquentes restent à proximité de l’emplacement d’accès.

En règle générale, cela a pour effet de réduire la latence d’accès, l’utilisation de la bande passante et les coûts d’infrastructure.

Le fichier de bibliothèque AppMeasurement pour JavaScript peut être distribué par le biais d’un réseau CDN afin d’optimiser les performances et la remise du fichier au visiteur du site. Les clients Adobe doivent veiller à la configuration correcte de leurs services CDN. Les réseaux CDN expliquent souvent les fluctuations constatées au niveau des temps de téléchargement. Aussi, doivent-ils être considérés comme la cause la plus probable de variations à ce niveau.

Le gestionnaire de balises stocke tout le code JavaScript sur un réseau CDN.
