---
description: La validation de la précision des données est un processus qui consiste à comparer les données d’un rapport à des points de données connus et vérifiables.
keywords: Mise en œuvre d’Analytics
seo-description: La validation de la précision des données est un processus qui consiste à comparer les données d’un rapport à des points de données connus et vérifiables.
seo-title: Validation de la précision des données
solution: Analytics
title: Validation de la précision des données
topic: Développeur et mise en œuvre
uuid: 267 f 6 c 61-705 a -41 cf -9 e 09-4 e 2 ce 2331 f 32
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Validation de la précision des données

La validation de la précision des données est un processus qui consiste à comparer les données d’un rapport à des points de données connus et vérifiables.

Cette opération doit être effectuée par un membre du personnel Adobe, de préférence par le consultant Adobe (la personne la plus au fait des méthodes d’implémentation technique).

Les points de données à utiliser sont, par ordre de préférence :

* (Sites eConversion) Comparaison des commandes eConversion pour un seul jour.
* Comparaison des événements de succès connus, en particulier les données enregistrées lorsqu’une adresse IP et d’autres informations sur le navigateur généralement stockées dans des journaux de serveur Web peuvent être comparées aux données collectées.
* Comparaison des pages vues.

>[!NOTE]
>
>Default pages, such as [!DNL index.html], often receive automated or monitoring traffic. Elles présentent une plus grande différence, sur le plan de la collecte des données par le navigateur, que les autres pages consultées.

Les trois types de validation nécessitent un journal de débogage ou un flux de données pour la période concernée. Celle-ci équivaut généralement à un jour, voire moins.

Il est prévu que les commandes ou événements de succès puissent être mesurés dans une marge de 2 à 3 % des valeurs réelles (avec parfois des niveaux de précision supérieurs) à l’aide d’implémentations JavaScript standard. Cela suppose une page SSL, étant donné que les pages de ce type sont mises en cache beaucoup moins souvent (par définition, elles ne doivent pas l’être). Une implémentation comprenant des demandes d’image côté serveur sur une page SSL doit se trouver dans une marge de 0 à 1 % par rapport aux valeurs réelles. Les différences peuvent être plus importantes dans le cas des pages non sécurisées, mais toujours dans une marge de 5 % par rapport aux valeurs réelles.

Lors de la comparaison de pages vues pour une seule période, il est prévu que celles-ci soient prises en compte dans une marge de 5 % par rapport aux valeurs réelles, hormis le trafic de surveillance (tel que Keynote ou WhatsUpGold) ou automatisé (robot d’exploration, robots et scripts).

Les comparaisons de précision des données doivent prendre en compte les éléments suivants :

* Contrôle qualité ou autres types de tests internes pouvant être filtrés par adresses IP ou règles VISTA.
* Balises actives générant uniquement des balises pour certains types de commande ou de trafic.
* Les requêtes de comparaison doivent tenir compte de ce qui est mesuré par le site Web (hormis les retours, les commandes passées par le personnel du service d’assistance clientèle ou d’autres conditions particulières).
* Correspondance entre les décalages horaires entre la requête et la suite de rapports.
* Trafic Keynote personnalisé ou de même type (Keynote Transaction, etc.) qui mesure le processus de commande et peut être répercuté dans des balises, mais qui est supprimé des systèmes de commandes.
* Prise en compte des processus d’élimination des doublons du client.
* Rechargements de la page de commande (élimination des commandes en double selon le *`purchaseID`*).

