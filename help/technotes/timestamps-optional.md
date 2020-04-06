---
description: Découvrez-en plus sur les avantages et les contraintes liés à l’utilisation du paramètre Horodatages (facultatif).
keywords: Analytics Implementation
title: Utilisation du paramètre Horodatages (facultatif)
topic: Developer and implementation
uuid: 956aaa16-6ffa-4b63-b022-a659f5143e00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Utilisation du paramètre Horodatages (facultatif)

Découvrez-en plus sur les avantages et les contraintes liés à l’utilisation du paramètre Horodatages (facultatif).

Le paramètre Horodatages (facultatif) est défini par défaut pour toutes les nouvelles suites de rapports.

* Combinez des données horodatées et non horodatées dans la même suite de rapports globale.
* Envoyez des données horodatées d’une application mobile vers une suite de rapports globale.
* Mettez à niveau les applications pour utiliser des horodatages sans avoir à créer de suite de rapports.

>[!NOTE] Le paramètre Horodatages (facultatif) est le paramètre par défaut pour toutes les nouvelles suites de rapports générées à partir d’un modèle. Les nouvelles suites de rapports copiées à partir d’une suite de rapports existante héritent des paramètres de la suite de rapports d’origine.

Voir [Horodatages facultatifs](https://marketing.adobe.com/resources/help/fr_FR/reference/timestamp-optional.html) pour plus d’informations sur la configuration.

## Horodatages (facultatif) : intégration de données horodatées et non horodatées {#section_BF17CB593044462B993FD0D28EA56518}

Avec l’option Horodatages (facultatif), vous pouvez combiner des données horodatées et non horodatées sans aucune perte de données. Les données hors ligne horodatées générées par un appareil mobile peuvent être combinées à des données en direct non horodatées d’une page web, ou intégrées aux données d’une plateforme quelconque à l’aide d’un appel d’horodatage côté client.

* **Données horodatées**. Les données d’horodatage côté client sont capturées et envoyées directement avec les données du périphérique à l’aide des variables d’horodatage côté client : Javascript sur une page web ou à l’aide d’un appel de SDK mobile ([!DNL offlineEnabled=true]) dans une application mobile.
* **Données non horodatées**. Adobe définit un horodatage sur les données non horodatées dans une suite de rapports lorsque les données atteignent les serveurs de collecte.


Une suite de rapports peut avoir l’un des paramètres d’horodatage suivants :

* Horodatages non autorisés (paramètre ID de visiteur pris en charge)
* Horodatage requis (paramètre ID de visiteur non pris en charge)
* Horodatages facultatifs (paramètre ID de visiteur pris en charge mais pas sur les accès horodatés)

## Paramètre Horodatages (facultatif) {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Le paramètre Horodatages (facultatif) permet d’intégrer plusieurs suites de rapports et d’en produire des rapports, avec ou sans horodatage côté client. Avec le paramètre Horodatages (facultatif), vous pouvez mettre à jour votre application afin d’utiliser des horodatages tout en utilisant des données non horodatées de l’application précédente.

| Dans les versions précédentes... | En outre... |
|--- |--- |
| Il n’était pas possible d’envoyer les données horodatées vers une suite de rapports globale non horodatée. Par conséquent, les données d’accès envoyées par les appareils hors ligne étaient ignorées lors de l’ajout à une suite de rapports non horodatée. <br/><br/>Par conséquent, les données d’accès envoyées à partir des données hors ligne étaient ignorées lors de l’ajout à une suite de rapports non horodatée. | La mise à jour d’une application pour collecter et utiliser les horodatages vous obligeait à utiliser une nouvelle suite de rapports. <br/>Vous ne pouviez pas les enregistrer dans la suite de rapports existante ni intégrer les données existantes lors de la mise à jour d’une application pour utiliser des horodatages. |

Avec le paramètre **Horodatages (facultatif)**, vous pouvez intégrer des données non horodatées d’un site web en ligne aux données hors ligne d’appareils mobiles ou mettre à jour votre application non horodatée en application horodatée.

## Combinaison de données dans une suite de rapports globale {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

Vous pouvez combiner les données dans une suite de rapports globale de plusieurs façons, notamment en utilisant le balisage multisuite, les règles Vista et les fichiers de lots importés à partir de sources hors ligne.

>[!IMPORTANT] Concevez avec soin chaque jeu de données de composant afin que la combinaison soit logique dans une suite de rapports globale.

## Bonnes pratiques lors du recours aux horodatages {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Voici quelques bonnes pratiques et quelques exigences et restrictions à prendre en compte lors de l’intégration de données horodatées avec des données non horodatées.

* En général, les horodatages d’un ou d’une visite donné doivent parvenir à Adobe dans l’ordre chronologique approprié.

   Les données qui ne sont pas dans l’ordre peuvent inclure des données arrivées tardivement issues de collections de données hors ligne et d’accès tardifs, ou encore d’horloges désynchronisées sur les appareils mobiles hors ligne. Les données hors commande peuvent avoir un impact négatif sur les calculs de temps (valeurs de durée de la visite, par exemple), l’attribution (persistance d’eVar), le nombre de visites/nombre de visites et les rapports de cheminement.

* L’utilisation d’horodatages lors de la définition d’un [s.visitorID](https://marketing.adobe.com/resources/help/fr_FR/sc/implement/visid_custom.html) n’est pas recommandée. Cela peut conduire à des données hors service.

* Il est préférable de ne pas avoir recours aux horodatages dans les applications hybrides composées d’une application (données hors ligne horodatées) ouvrant un navigateur web (données en direct non horodatées). Cela se traduit par des  inexactes de la session.

   En outre, les applications hybrides ne doivent pas définir l’attribut visitor ID.
