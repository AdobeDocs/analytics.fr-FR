---
description: Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.
seo-description: Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.
seo-title: Horodatages facultatifs
solution: Analytics
title: Horodatages facultatifs
topic: Outils d’administration
uuid: 0 fa 63658-1 cc 2-4 adc -8 d 51-a 0662 d 0 aa 941
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Horodatages facultatifs

Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.

Avec les horodatages facultatifs, vous pouvez faire ce qui suit :

* Ajoutez des données horodatées et non horodatées à la même suite de rapports globale.
* Envoyez des données horodatées d’une application mobile vers une suite de rapports globale.
* Mettez à niveau les applications afin d’utiliser le suivi hors ligne sans avoir à créer une suite de rapports.

Voir [Utilisation du paramètre Horodatages (facultatif)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=timestamps-overview) pour connaître les bonnes pratiques en termes d’utilisation des horodatages dans une suite de rapports.

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) on data that is already timestamped. Ceci risquerait de générer des données dans le désordre et de nuire aux calculs de durée (valeurs de durée) et aux rapports d’attribution (persistance des eVars), du nombre de visites/de visiteurs et de cheminement.

>[!NOTE]
>
>Les données de la session avec horodatage sont conservées pendant 92 jours au maximum.

## Nouvelles suites de rapports {#section_095A7CFBD280494593B9BEC1592B73A6}

* Si elles sont créées à partir d’un modèle, le paramètre Horodatages (facultatif) est activé par défaut pour les nouvelles suites de rapports.

   (Pour créer une suite de rapports à partir d’un modèle, sélectionnez **Admin &gt; Report Suites &gt; Nouveau &gt; Report Suite**.)
* Si elle est copiée à partir d’une suite de rapports existante, la nouvelle suite de rapports hérite des paramètres d’horodatage de l’original, y compris :

   * **Horodatages non autorisés** (paramètre s.visitorID pris en charge)
   * **Horodatages requis** (paramètre s.visitorID non pris en charge)
   * **Horodatages facultatifs** (paramètre s.visitorID pris en charge sauf sur les accès horodatés)

## Pour activer le paramètre Horodatages (facultatif) pour des suites de rapports existantes, procédez comme suit : {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Sélectionnez **Admin &gt; Report Suites &gt; Modifier les paramètres &gt; Général &gt; Configuration de l’horodatage**.
1. Cochez la case **Convertir les suites de rapports sélectionnées en horodatages (facultatif)**

   Le paramètre Horodatages (facultatif) est activé pour la suite de rapports.

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

