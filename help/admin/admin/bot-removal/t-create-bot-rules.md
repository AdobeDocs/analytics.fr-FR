---
description: Les règles de robots personnalisées vous permettent de filtrer le trafic sur la base des conditions que vous avez définies.
seo-description: Les règles de robots personnalisées vous permettent de filtrer le trafic sur la base des conditions que vous avez définies.
seo-title: Créer une règle de robot personnalisée
solution: Analytics
subtopic: Règles de robots
title: Créer une règle de robot personnalisée
topic: Outils d’administration
uuid: abbc 5 c 7 e -912 f -4660-a 02 b -0431 a 740 ec 70
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Créer une règle de robot personnalisée

Les règles de robots personnalisées vous permettent de filtrer le trafic sur la base des conditions que vous avez définies.

Les règles de robots personnalisées sont définies à l’aide des types de conditions suivants :

* Agent utilisateur
* Adresse IP
* Plage IP

Plusieurs conditions peuvent être définies pour une seule règle. Dans le cas de conditions multiples, une correspondance est établie à l’aide de l’opérateur « OU ». Si vous indiquez, par exemple, une valeur pour Agent utilisateur et Adresse IP, le trafic est considéré comme du trafic de robots si l’une des conditions est remplie.

## Agent utilisateur

Une condition Agent utilisateur vérifie la valeur correspondante afin de déterminer si elle **[!UICONTROL contient]** ou **commence par]la chaîne spécifiée.[!UICONTROL ** En cas de sélection de l’option **[!UICONTROL contient], une correspondance est établie avec la sous-chaîne si elle est présente dans l’agent utilisateur.**

Des valeurs facultatives peuvent être incluses dans la liste **[!UICONTROL ne contient pas]afin de définir les valeurs qui ne peuvent pas se trouver dans l’agent utilisateur pour qu’une correspondance soit établie.** Vous pouvez inclure plusieurs valeurs, à raison d’une valeur par ligne. Si l’agent utilisateur répond aux critères spécifiés dans la chaîne de correspondance, mais contient également une chaîne reprise dans la liste « ne contient pas », il n’est pas considéré comme une correspondance.

Le champ **[!UICONTROL contient]est limité à 100 caractères.** La liste « ne contient pas » est limitée à 255 caractères, moins un caractère de séparation pour chaque nouvelle ligne. (Cela équivaut au nombre de chaînes - 1. Si vous indiquez 4 chaînes *ne contient pas*, 3 caractères de séparation sont obligatoires.) Les correspondances de chaînes ne sont pas sensibles à la casse.

## Adresse IP (avec correspondances de caractères génériques)

Établit une correspondance avec une ou plusieurs adresses IP dans le même bloc à l’aide de caractères génériques (*). Indiquez les valeurs numériques de l’adresse IP avec laquelle vous souhaitez établir une correspondance. Remplacez par * toute valeur que vous souhaitez faire correspondre à l’aide d’un caractère générique. La liste suivante contient des exemples de chaînes de correspondance d’adresses IP :

```
10.10.10.1
10.10.10.*
```

## Plage d’adresses IP

Indiquez les plages de début et de fin des adresses IP avec lesquelles vous souhaitez établir une correspondance. Remplacez par * toute valeur que vous souhaitez faire correspondre à l’aide d’un caractère générique.

## Définir une règle de robot personnalisée

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Cliquez sur **[!UICONTROL Enregistrer]**. La modification doit normalement être prise en compte dans les 30 minutes.

>[!Note]
>Il est possible de définir manuellement 500 règles dans l’interface utilisateur. Au-delà de cette limite, les règles doivent être gérées en bloc au moyen des options Importer un fichier et Exporter des règles de bots.
