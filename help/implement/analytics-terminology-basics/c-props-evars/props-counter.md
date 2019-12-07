---
description: Un compteur stocke (et, dans certains cas, affiche) le nombre d’occurrences d’un événement ou processus spécifique.
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
title: Utilisation de propriétés comme compteurs
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Utilisation de propriétés comme compteurs

Un compteur stocke (et, dans certains cas, affiche) le nombre d’occurrences d’un événement ou processus spécifique.

Vous pouvez utiliser une prop pour compter le nombre de fois qu’un événement s’est produit. Vous pouvez, par exemple, comparer l’utilisation de Real Player par rapport au Lecteur Windows Media sur votre site. Chaque page contient le [!UICONTROL code à coller], dans lequel figurent des variables [!UICONTROL s.prop]. Utilisez [!UICONTROL s.prop] 1 pour effectuer le suivi des lecteurs. Pour la page A, saisissez une valeur dans [!UICONTROL s.prop]1 pour représenter Real Player.

```js
s.prop1="RealPlayer"
```

Pour la page B, saisissez une valeur semblable dans [!UICONTROL s.prop] 1 pour le Lecteur Windows Media, comme illustré ci-dessous.

```js
s.prop1="WindowsMP"
```

> [!NOTE] Adobe met à votre disposition 75 variables [!UICONTROL s.prop].

A mesure que les utilisateurs accèdent à votre site et visitent des pages contenant Real Player ou le Lecteur Windows Media, [!DNL Analytics] est en mesure d’effectuer une segmentation en fonction des pages consultées. Le rapport [!UICONTROL Trafic personnalisé] affiche alors le nombre de visites enregistrées sur chaque page.

> [!NOTE] Le nom du rapport [!UICONTROL Trafic personnalisé] peut être personnalisé. Vous pouvez, par exemple, renommer le rapport [!UICONTROL Trafic personnalisé] en « Rapports sur les types de lecteur ».

