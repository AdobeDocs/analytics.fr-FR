---
description: Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.
keywords: Mise en œuvre d’Analytics
seo-description: Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.
seo-title: Modifications du code
solution: Analytics
title: Modifications du code
topic: Développeur et mise en œuvre
uuid: efac 045 e -15 f 5-45 f 6-a 21 a-de 6 c 4 a 8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modifications du code

Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. Assurez-vous que le code JavaScript s’exécute correctement sur l’ensemble des pages et des modèles de page (dans Internet Explorer, sélectionnez Options Internet, onglet Avancé, puis cliquez sur Afficher une notification de chaque erreur de script).

Lors de la recherche d’erreurs, collez le code dans une page HTML par défaut afin de déterminer si l’erreur est due à d’autres objets/éléments de page.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

