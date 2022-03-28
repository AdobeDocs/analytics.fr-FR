---
title: Algorithmes de chiffrement HTTPS pris en charge
description: Le 23 juin 2022, nous supprimerons la prise en charge des chiffrements TLS 1.2 qui utilisent SHA1 ou CBC pour les clients dont le niveau de sécurité du chiffrement est défini sur "Élevé".
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Algorithmes de chiffrement HTTPS pris en charge

Adobe offre deux niveaux de sécurité de chiffrement pour répondre aux besoins divers des clients en matière de sécurité dans la collecte de données propriétaires. Ces niveaux déterminent quels algorithmes de chiffrement sont pris en charge pour les connexions HTTPS avec nos serveurs. Les clients prennent par défaut la valeur &quot;Standard&quot;, qui ne prend en charge que les algorithmes de chiffrement modernes. &quot;Élevé&quot; prend en charge une liste plus réduite d’algorithmes de chiffrement pour les clients qui sont plus préoccupés par ces connexions. Pour les deux niveaux de sécurité, Adobe met régulièrement à jour l’ensemble des algorithmes pris en charge en fonction des pratiques de sécurité actuelles. Si vous souhaitez modifier les paramètres de sécurité du chiffrement, contactez l’assistance clientèle.

Le 23 juin 2022, nous supprimerons la prise en charge des chiffrements TLS 1.2 qui utilisent SHA1 ou CBC pour les clients dont le niveau de sécurité du chiffrement est défini sur &quot;Élevé&quot;.  Cette modification aura un impact sur la collecte sécurisée des données pour les utilisateurs finaux sur les systèmes d’exploitation plus anciens.

Les chiffrements TLS 1.2 suivants ne seront plus pris en charge :

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

Les clients suivants sont connus pour être affectés par cette modification car ils ne prennent pas en charge les normes de chiffrement actuelles :

* Windows 8.1 et versions antérieures (dernière mise à jour en 2018)
* Windows Phone 8.1 et versions antérieures (dernière mise à jour en 2016)
* OS X 10.10 et versions antérieures (dernière mise à jour en 2017)
* iOS 8.4 et versions antérieures (dernière mise à jour en 2015)

Les appareils Android ne sont pas affectés par cette modification.

Les clients dont le niveau de sécurité du chiffrement est défini sur &quot;Standard&quot; ne sont pas affectés par cette modification.

