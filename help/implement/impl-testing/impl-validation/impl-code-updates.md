---
description: Il appartient au client de tester toute modification apportée au fichier .JS ou au code HTML. Ces tests doivent être terminés avant la publication des modifications sur les sites Web de production.
keywords: Analytics Implementation
solution: Analytics
title: Modifications du code
topic: Developer and implementation
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

