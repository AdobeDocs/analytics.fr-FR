---
description: Un compteur stocke (et, dans certains cas, affiche) le nombre d’occurrences d’un événement ou processus spécifique.
keywords: Implémentation d'Analytics ; props ; s. prop ; trafic personnalisé ; compteurs
seo-description: Un compteur stocke (et, dans certains cas, affiche) le nombre d’occurrences d’un événement ou processus spécifique.
seo-title: Utilisation de props comme compteurs
solution: Analytics
title: Utilisation de props comme compteurs
topic: Développeur et mise en œuvre
uuid: ab 83 bd 7 e -10 d 9-49 f 9-b 9 e 7-c 50397 e 95 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilisation de props comme compteurs

Un compteur stocke (et, dans certains cas, affiche) le nombre d’occurrences d’un événement ou processus spécifique.

Vous pouvez utiliser une prop pour compter le nombre de fois qu’un événement s’est produit. Vous pouvez, par exemple, comparer l’utilisation de Real Player par rapport au Lecteur Windows Media sur votre site. Chaque page contient le [!UICONTROL code à coller], dans lequel figurent des variables [!UICONTROL s.prop]. Utilisez [!UICONTROL s.prop] 1 pour effectuer le suivi des lecteurs. Pour la page A, saisissez une valeur dans [!UICONTROL s.prop]1 pour représenter Real Player.

```js
s.prop1="RealPlayer"
```

Pour la page B, saisissez une valeur semblable dans [!UICONTROL s.prop] 1 pour le Lecteur Windows Media, comme illustré ci-dessous.

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

A mesure que les utilisateurs accèdent à votre site et visitent des pages contenant Real Player ou le Lecteur Windows Media, [!DNL Analytics] est en mesure d’effectuer une segmentation en fonction des pages consultées. Le rapport [!UICONTROL Trafic personnalisé] affiche alors le nombre de visites enregistrées sur chaque page.

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. Vous pouvez, par exemple, renommer le rapport [!UICONTROL Trafic personnalisé] en « Rapports sur les types de lecteur ».

