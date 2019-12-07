---
description: De nombreux navigateurs ne commencent à afficher le contenu d’un tableau qu’une fois la compilation de l’intégralité du tableau terminée.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Tableaux
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tableaux

De nombreux navigateurs ne commencent à afficher le contenu d’un tableau qu’une fois la compilation de l’intégralité du tableau terminée.

Si tout le contenu de la page figure dans un tableau volumineux, le navigateur doit terminer la compilation afin d’afficher quoi que ce soit.

En plaçant l’appel au fichier de bibliothèque JavaScript en dehors des balises du tableau, vous avez la garantie que l’appel aux serveurs Analytics n’a aucune incidence sur le contenu de la page.

> [!NOTE] Le fichier doit être placé dans une position légale pour les images et doit apparaître entre la balise d’ouverture <body> et la balise </body> de fermeture.

