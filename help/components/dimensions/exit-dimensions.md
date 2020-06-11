---
title: Dimensions de sortie
description: Listes quittent les dimensions et leur utilisation.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Dimensions de sortie

*Cette page d’aide décrit le fonctionnement des sorties en tant que dimension. Pour plus d’informations sur le fonctionnement des sorties en tant que mesure, voir la mesure[Sorties](../metrics/exits.md).*

Les dimensions de sortie enregistrent la dernière valeur de dimension et l’appliquent rétroactivement à tous les accès de la visite. Les dimensions de sortie sont disponibles pour toutes les variables pour lesquelles le cheminement est activé sous Variables [de](/help/admin/admin/c-traffic-variables/traffic-var.md) trafic dans les paramètres de la suite de rapports.

## Renseigner les dimensions de sortie avec des données

Une dimension de sortie donnée est basée sur sa variable de trafic associée. Si la variable non quittée comporte des données, sa dimension de sortie associée contient également des données. Aucune modification d’implémentation n’est requise pour les dimensions de sortie si vos variables de trafic contiennent des données.

## Valeurs de dimension

Les variables de sortie étant généralement basées sur des chaînes personnalisées dans votre implémentation, votre organisation détermine les valeurs de dimension. Les valeurs d’une dimension de sortie donnée correspondent aux valeurs de dimension dans sa dimension de non-sortie associée. Par exemple, les valeurs de dimension de la dimension &quot;Page de sortie&quot; contiennent des valeurs de dimension similaires dans la dimension &quot;Page&quot;.
