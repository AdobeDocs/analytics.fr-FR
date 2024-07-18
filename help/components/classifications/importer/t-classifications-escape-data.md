---
description: Étapes décrivant comment placer des données de classification dans une séquence d’échappement dans le fichier de classification.
title: Données de classification placées dans une séquence d’échappement
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 100%

---

# Données de classification placées dans une séquence d’échappement

Pour placer des données de classification dans une séquence d’échappement dans le fichier de classification :

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assurez-vous que le format du fichier de classification est v2.1.

   Si le format v2.1 est activé, une ligne similaire à celle ci-dessous s’affiche :

   >[!NOTE]
   >
   >Pour indiquer le format v2.1, activez la **[!UICONTROL Sortie entre guillemets]** lors de l’exportation du fichier sur la page [!UICONTROL Importateur de classifications] ([!UICONTROL Exportation navigateur] ou [!UICONTROL Exportation FTP]).

1. Entourez le champ contenant les caractères spéciaux de guillemets doubles (`"`).

Le caractère double guillemet peut apparaître dans une cellule placée dans une séquence d’échappement en le remplaçant par deux caractères guillemets doubles (`" "`). Par exemple :

```
My String "of data"
```

Le placement en séquence d’échappement serait :

```
"My String ""of data"""
```
