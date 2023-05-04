---
title: Algorithmes de chiffrement HTTPS pris en charge
description: Paramètres de sécurité du chiffrement TLS et types de certificat.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 299de03c05f6a8af4f6c5d98c76bae54eec4c088
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 30%

---

# Algorithmes de chiffrement HTTPS pris en charge

## Niveaux de sécurité des filtres

Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité lors de la collecte de données propriétaires. Ces niveaux déterminent quels algorithmes de chiffrement sont pris en charge pour les connexions HTTPS avec nos serveurs. Adobe passe régulièrement en revue et met à jour l’ensemble des algorithmes pris en charge en fonction des pratiques de sécurité actuelles. Si vous souhaitez modifier les paramètres de sécurité du chiffrement, contactez l’assistance clientèle.

&quot;Standard&quot; nécessite TLS 1.2 ou une version plus récente et un chiffrement au moins 128 bits. Il est conçu pour offrir la compatibilité d’appareil la plus large tout en conservant un chiffrement sécurisé.

Le niveau de sécurité de chiffrement &quot;élevé&quot; nécessite TLS 1.2 ou une version ultérieure et supprime la prise en charge des chiffrements plus faibles. Il est conçu pour les clients qui souhaitent un chiffrement le plus fort et ne se soucient pas de la prise en charge des appareils plus anciens.

Les clients suivants sont connus pour ne pas pouvoir se connecter avec le paramètre de sécurité de chiffrement défini sur &quot;Élevé&quot;.

* Windows 8.1 et versions antérieures (dernière mise à jour en 2018)
* Windows Phone 8.1 et versions antérieures (dernière mise à jour en 2016)
* OS X 10.10 et versions antérieures (dernière mise à jour en 2017)
* iOS 8.4 et versions antérieures (dernière mise à jour en 2015)

## Types de certificat HTTPS pris en charge

Adobe prend en charge les types de certificats RSA et ECC pour répondre à différents besoins des clients. Les certificats RSA sont plus largement pris en charge pour les clients, mais les certificats ECC utilisent moins de traitement côté serveur et côté client. Pour les certificats gérés par Adobe, RSA et ECC sont fournis. Pour les certificats gérés par le client, RSA et ECC sont recommandés. Les clients modernes prennent en charge RSA et ECC. Les clients suivants ne prennent en charge que les certificats RSA :

* Windows Vista et versions antérieures (dernière mise à jour en 2012)
* Windows Phone 8.0 et versions antérieures (dernière mise à jour en 2014)
* OS X 10.8 et versions antérieures (dernière mise à jour en 2013)
* iOS 5.1 et versions antérieures (dernière mise à jour en 2012)
* Android 4.3 et versions antérieures (dernière mise à jour en 2013)
