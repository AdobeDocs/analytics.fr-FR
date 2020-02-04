---
description: Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.
title: Horodatages facultatifs
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Horodatages facultatifs

Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.

Avec les horodatages facultatifs, vous pouvez faire ce qui suit :

* Ajoutez des données horodatées et non horodatées à la même suite de rapports globale.
* Envoyez des données horodatées d’une application mobile vers une suite de rapports globale.
* Mettez à niveau les applications afin d’utiliser le suivi hors ligne sans avoir à créer une suite de rapports.

> [!IMPORTANT] Si vous utilisez le paramètre Horodatages (facultatif), ne définissez pas [s.visitorID](/help/implement/vars/config-vars/visitorid.md) sur les données qui sont déjà horodatées. Ceci risquerait de générer des données dans le désordre et de nuire aux calculs de durée (valeurs de durée) et aux rapports d’attribution (persistance des eVars), du nombre de visites/de visiteurs et de rapports de cheminement.

> [!NOTE] Les données de la session avec horodatage sont conservées pendant 92 jours au maximum. Cela signifie qu’une visite/session sera « gardée ouverte » pendant 92 jours, tandis que tout accès supplémentaire, qui n’intervient pas 30 minutes après l’accès précédent (au cours de la période d’accès), peut toujours être inclus dans la même visite/session. Tout « ancien » accès qui est reçu sans ordre produira des résultats « inconnus », car plusieurs facteurs (segmentation, attribution, expiration, etc.) influencent l’inclusion ou non de ces accès dans les rapports.

## Nouvelles suites de rapports {#section_095A7CFBD280494593B9BEC1592B73A6}

* Si elles sont créées à partir d’un modèle, le paramètre Horodatages (facultatif) est activé par défaut pour les nouvelles suites de rapports.

   (Pour créer une suite de rapports à partir d’un modèle, sélectionnez **Admin > Report Suites > Nouveau > Report Suite**.)
* Si elle est copiée à partir d’une suite de rapports existante, la nouvelle suite de rapports hérite des paramètres d’horodatage de l’original, y compris :

   * **Horodatages non autorisés** (paramètre s.visitorID pris en charge)
   * **Horodatages requis** (paramètre s.visitorID non pris en charge)
   * **Horodatages facultatifs** (paramètre s.visitorID pris en charge sauf sur les accès horodatés)

## Pour activer le paramètre Horodatages (facultatif) pour des suites de rapports existantes, procédez comme suit : {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Sélectionnez **Admin > Report Suites > Modifier les paramètres > Général > Configuration de l’horodatage**.
1. Cochez la case **Convertir les suites de rapports sélectionnées en horodatages (facultatif)**

   Le paramètre Horodatages (facultatif) est activé pour la suite de rapports.

> [!NOTE] Si une suite de rapports a été définie sur **Horodatages facultatifs**, contactez le service à la clientèle Adobe si vous souhaitez modifier ce paramètre.

