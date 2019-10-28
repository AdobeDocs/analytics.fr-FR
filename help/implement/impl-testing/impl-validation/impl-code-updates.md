---
description: Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.
keywords: Mise en œuvre d’Analytics
seo-description: Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.
seo-title: Modifications du code
solution: Analytics
title: Modifications du code
topic: Développeur et mise en œuvre
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modifications du code

Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.

Veillez à ce que les sauts de ligne/retours chariot ne soient pas modifiés ou supprimés du code HTML ou du fichier [!DNL .JS]. Assurez-vous que le code JavaScript s’exécute correctement sur l’ensemble des pages et des modèles de page (dans Internet Explorer, sélectionnez Options Internet, onglet Avancé, puis cliquez sur Afficher une notification de chaque erreur de script).

Lors de la recherche d’erreurs, collez le code dans une page HTML par défaut afin de déterminer si l’erreur est due à d’autres objets/éléments de page.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

