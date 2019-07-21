---
description: La variable s.products peut être la variable utilisée par la collecte de données la plus complexe du point de vue de la syntaxe.
keywords: Mise en œuvre d’Analytics
seo-description: La variable s.products peut être la variable utilisée par la collecte de données la plus complexe du point de vue de la syntaxe.
seo-title: Erreurs courantes dans la variable Produits
solution: Analytics
subtopic: Résolution des problèmes
title: Erreurs courantes dans la variable Produits
topic: Développeur et mise en œuvre
uuid: 94075 c 56-37 c 3-44 de-bf 37-1 dfd 228 c 6665
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Erreurs courantes dans la variable Produits

La variable s.products peut être la variable utilisée par la collecte de données la plus complexe du point de vue de la syntaxe.

La virgule, le point-virgule, la barre verticale et le signe égal jouent un rôle spécifique dans la variable. Chaque entrée de produit ne peut pas excéder 100 octets (caractères multi-octets, y compris). Bien que des erreurs soient compréhensibles, la variable [!UICONTROL s.products] est toutefois la variable la plus importante d’un site, car elle permet le suivi des recettes, des unités, des noms de produit, etc.

Vous trouverez ci-dessous quelques erreurs très courantes qui peuvent entraîner des problèmes dans n’importe quelle implémentation. 

Vérifiez que la [!UICONTROL catégorie], le [!UICONTROL nom de produit] et les totaux des [!UICONTROL recettes] ne contiennent pas de virgules ou de points-virgules. La virgule sert à séparer les entrées dans la chaîne [!UICONTROL s.products]. Cela se produit lorsqu’une même transaction est associée à deux produits. Le point-virgule sert à délimiter les champs dans une entrée. Si vous utilisez une virgule ou un point-virgule dans un autre cas, la collecte de données suppose que vous séparez des entrées de produit. Examinez l’exemple suivant :

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

Dans cette implémentation, le développeur souhaitait probablement transcrire ces informations :

Catégorie 1 : widgets

Produit 1 : large widget, 40′x40′

Unités 1 : 1

Recettes 1 : 19.99

Catégorie 2 : wugs

Produit 2 : tiny wug

Unités 2 : 2

Recettes 2 : 1,999.98

Notez les virgules dans les entrées Produit 1 et Recettes 2. Elles indiquent une nouvelle entrée de produit. La collecte de données interprète les informations ci-dessus de la manière suivante :

Catégorie 1 : widgets

Produit 1 : large widget

Catégorie 2 : 40'x40'

Produit 2 : 1

Unité 2 : 19.99

Catégorie 3 : wugs

Produit 3 : tiny wug

Unités 3 : 2

Recettes 3 : 1

Catégorie 4 : 999.98

Une erreur de ce type entraîne souvent des valeurs numériques inattendues dans le rapport [!UICONTROL Produits], car le champs des unités est enregistré comme nom du produit. Si vous détectez des noms de produits incorrect dans votre rapport [!UICONTROL Produits], examinez l’implémentation de la variable [!UICONTROL s.products] pour rechercher une utilisation incorrecte des caractères réservés comme la virgule.

Les noms de produit et de catégorie ne doivent pas contenir de caractères qui ne sont pas pris en charge. Cette règle peut être particulièrement difficile à appliquer dans la chaîne [!UICONTROL s.products], car les noms de produit peuvent souvent contenir les caractères ™, © et ®. Ces caractères doivent être supprimés des valeurs de produit et de catégorie avant de les placer dans [!UICONTROL s.products] Vous devez également vérifier que les symboles de devise ne sont pas inclus dans les valeurs de recettes. Les caractères pris en charge sont les nombre 1 à 127 de la table ASCII.

Si vous ne transmettez pas une catégorie de produit dans la chaîne du produit, veillez à inclure un point-virgule (;) à l’endroit où apparaît normalement le produit, comme illustré ci-dessous :

```js
s.products=";product name"
```

Dans ce cas, le point-virgule représente un espace réservé pour la catégorie de produit. Si un point-virgule n’est pas inclus, le nom de produit est comptabilisé en tant que catégorie, le nombre d’unités est comptabilisé en tant que nom du produit, etc.
