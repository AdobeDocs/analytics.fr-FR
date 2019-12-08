---
description: La variable pageType n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Mauvaise définition de la variable PageType
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mauvaise définition de la variable PageType

La variable pageType n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».

Une seule valeur est possible pour cette variable, à savoir : « errorPage ».

```js
pageType="errorPage"
```

Sur une page d’erreur 404, la variable *`pageName`* ne doit pas être renseignée sur une page « Erreur 404 ». La variable *`pageType`* ne doit être définie que sur une page d’erreur 404 désignée. Les pages qui comportent du contenu ne doivent jamais avoir de valeur dans la variable *`pageType`*. Pour les pages comportant du contenu, vous pouvez définir la variable, comme illustré ci-dessous.

```js
pageType=""
```

Il est recommandé de supprimer entièrement la variable des pages comportant du contenu. Cette pratique est conseillée pour éviter toute confusion en ce qui concerne l’objet de la variable.
