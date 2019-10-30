---
description: Dans le langage HTML, plusieurs caractères créent un espace.
keywords: Mise en œuvre d’Analytics
seo-description: Dans le langage HTML, plusieurs caractères créent un espace.
seo-title: Utilisation des espaces dans les valeurs de variable
solution: Analytics
subtopic: Résolution des problèmes
title: Utilisation des espaces dans les valeurs de variable
topic: Développeur et mise en œuvre
uuid: 1edd7934-9b3e-43e2-9f24-65f42cb306e2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Utilisation des espaces dans les valeurs de variable

Dans le langage HTML, plusieurs caractères créent un espace.

Il s’agit notamment d’un espace, d’une tabulation et d’un retour chariot (ou nouvelle ligne). Examinez l’exemple suivant :

```js
<head> 
 <title> 
   Home Page 
 </title> 
</head> 
<body> 
<script language="javascript"> 
 s.pageName=document.title 
</script> 
```

Dans ce cas, document.title renseigne [!UICONTROL s.pageName], qui doit recevoir la valeur « Home Page ». Vous pouvez remarquer l’espace situé avant « Home Page ». Tous les navigateurs n’interprètent pas cet espace de la même manière. Le résultat obtenu est illustré par les deux exemples suivants :

```js
s.pageName="Home Page"
```

```js
s.pageName="        Home Page"
```

La première valeur s’affiche correctement, mais la seconde comporte un espace avant le texte. [!DNL Analytics] traite ces valeurs comme des valeurs distinctes pour la variable [!UICONTROL s.pageName]. L’interface d’[!DNL Analytics] supprime l’espace de début de la seconde valeur. Le résultat obtenu est un rapport qui affiche les valeurs ci-dessous.

![](assets/white_space.jpg)

Cette erreur d’implémentation entraîne la fragmentation sur plusieurs lignes des valeurs de la variable. [!DNL SAINT] n’autorise pas d’espace de début dans une valeur clé. Cela signifie que cet outil ne peut pas être utilisé pour regrouper plusieurs lignes afin de contourner ce problème. Le seul moyen de résoudre ce problème consiste à prétraiter la valeur de variable souhaitée (dans le cas présent, la propriété document.title) pour supprimer les espaces de début (ou de fin).

L’exemple ci-dessus utilise la variable [!UICONTROL s.pageName] avec la propriété document.title. Adobe ne conseille pas d’utiliser la propriété document.title en tant que nom de page. Ce problème n’affecte pas que la variable [!UICONTROL s.pageName]. Toute variable dont la valeur comprend un espace de début ou de fin peut être affectée.
