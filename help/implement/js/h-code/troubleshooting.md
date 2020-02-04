---
title: Résolution des problèmes d'implémentation du code H
description: Découvrez quelques problèmes courants liés aux implémentations JavaScript héritées.
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Résolution des problèmes d&#39;implémentation du code H

Vous trouverez ci-dessous les étapes de dépannage spécifiques aux implémentations du code H.

## Placement du code Analytics dans la balise d’en-tête

> [!NOTE] Bien que les implémentations du code H exigent que le code soit référencé dans la `<body>` balise, d’autres implémentations (telles que l’utilisation d’Adobe Experience Platform Launch) nécessitent que le code soit référencé dans la `<head>` balise .

Le code Analytics crée une image invisible de 1x1 pixel. Auparavant, il était courant de placer la `s_code.js` référence dans la `<head>` balise . Le placement du code ici a empêché l’image d’affecter la mise en page de quelque manière que ce soit. Il s’exécute également plus tôt, ce qui vous permet de comptabiliser plus efficacement les pages vues pour les chargements partiels de pages.

However, certain elements of the code require the existence of the `<body>` object. Si le code JavaScript Analytics figure dans la `<head>` balise , il s’exécute avant que l’ `<body>` objet n’existe. As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. L’insertion de la référence de script `s_code.js` dans la `<head>` balise fonctionne, mais le résultat est une version très limitée d’Analytics.

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Adobe recommande de placer le code Analytics aussi près que possible du haut de la `<body>` balise . Assurez-vous que toutes les variables de page sont définies une fois le `s_code.js` fichier chargé.

> [!TIP] Si vous souhaitez intégrer Adobe Analytics à Adobe Target, le fichier d’inclusion JavaScript doit être placé en bas de la page.
