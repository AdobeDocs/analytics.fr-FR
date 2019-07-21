---
description: Étapes décrivant comment placer des données de classification dans une séquence d’échappement dans le fichier de classification.
seo-description: Étapes décrivant comment placer des données de classification dans une séquence d’échappement dans le fichier de classification.
seo-title: Placer des données de classification dans une séquence d’échappement
solution: Analytics
subtopic: Gestionnaire
title: Placer des données de classification dans une séquence d’échappement
topic: Outils d’administration
uuid: 724 edcc 5-4990-4 f 24-afbb -9 aef 301791 a 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Placer des données de classification dans une séquence d’échappement

Étapes décrivant comment placer des données de classification dans une séquence d’échappement dans le fichier de classification.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assurez-vous que le format du fichier de classification est v2.1.

   Si le format v2.1 est activé, une ligne similaire à celle ci-dessous s’affiche :

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

Le caractère double guillemet peut apparaître dans une cellule placée dans une séquence d’échappement en le remplaçant par deux caractères guillemets doubles (`" "`). Par exemple :

```
My String "of data"
```

Le placement en séquence d’échappement serait :

```
"My String ""of data"""
```
