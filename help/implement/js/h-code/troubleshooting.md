---
title: Résolution des problèmes de mise en œuvre du code H
description: Découvrez quelques problèmes courants liés aux mises en œuvre JavaScript héritées.
translation-type: ht
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Résolution des problèmes de mise en œuvre du code H

Vous trouverez ci-dessous les étapes de dépannage spécifiques aux mises en œuvre du code H.

## Placement du code Analytics dans la balise d’en-tête

> [!NOTE] Bien que les mises en œuvre du code H exigent que le code soit référencé dans la balise `<body>`, d’autres mises en œuvre (telles que l’utilisation d’Adobe Experience Platform Launch) nécessitent que le code soit référencé dans la balise `<head>`.

Le code Analytics crée une image invisible de 1x1 pixel. Auparavant, il était courant de placer la référence `s_code.js` dans la balise `<head>`. Le placement du code à cet endroit a empêché l’image d’affecter la mise en page de quelque manière que ce soit. Il s’exécute également plus tôt, ce qui permet de comptabiliser les pages vues pour les chargements de page partiels de façon plus efficace.

Certains éléments du code requièrent la présence de l’objet `<body>`. Si le code JavaScript Analytics figure dans la balise `<head>`, il s’exécute avant que l’objet `<body>` n’existe. Votre mise à jour ne collecte donc pas les données [!UICONTROL ClickMap], ni le suivi automatique des téléchargements de fichiers ou des liens de sortie ou les données de type de connexion. L’insertion de la référence de script `s_code.js` dans la balise `<head>` fonctionne, mais le résultat est une version très limitée d’Analytics.

Le code Analytics peut être placé n’importe où à l’intérieur des balises `<body>` d’une page HTML correctement formatée. Adobe recommande de placer le code Analytics aussi près que possible du haut de la balise `<body>`. Assurez-vous que toutes les variables de page sont définies une fois le fichier `s_code.js` chargé.

> [!TIP] Si vous souhaitez intégrer Adobe Analytics à Adobe Target, le fichier d’inclusion JavaScript doit être placé en bas de la page.
