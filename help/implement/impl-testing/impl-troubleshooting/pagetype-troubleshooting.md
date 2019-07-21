---
description: La variable pageType n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».
keywords: Mise en œuvre d’Analytics
seo-description: La variable pageType n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».
seo-title: Définition incorrecte de la variable pagetype
solution: Analytics
subtopic: Résolution des problèmes
title: Définition incorrecte de la variable pagetype
topic: Développeur et mise en œuvre
uuid: eafaf 58 e-ba 07-416 f -89 b 9-694687 cc 4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Définition incorrecte de la variable pagetype

La variable pageType n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».

Une seule valeur est possible pour cette variable, à savoir : « errorPage ».

```js
pageType="errorPage"
```

Sur une page d’erreur 404, la variable *`pageName`* ne doit pas être renseignée sur une page « Erreur 404 ». The *`pageType`* variable should be set only on a designated 404 error page. Any page containing content should never have a value in the *`pageType`* variable. Pour les pages comportant du contenu, vous pouvez définir la variable, comme illustré ci-dessous.

```js
pageType=""
```

Il est recommandé de supprimer entièrement la variable des pages comportant du contenu. Cette pratique est conseillée pour éviter toute confusion en ce qui concerne l’objet de la variable.
