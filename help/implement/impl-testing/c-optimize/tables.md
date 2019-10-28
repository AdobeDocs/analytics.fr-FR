---
description: De nombreux navigateurs ne commencent à afficher le contenu d’un tableau qu’une fois la compilation de l’intégralité du tableau terminée.
keywords: Mise en œuvre d’Analytics
seo-description: De nombreux navigateurs ne commencent à afficher le contenu d’un tableau qu’une fois la compilation de l’intégralité du tableau terminée.
seo-title: Tableaux
solution: Analytics
subtopic: Résolution des problèmes
title: Tableaux
topic: Développeur et mise en œuvre
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: ht
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Tableaux

De nombreux navigateurs ne commencent à afficher le contenu d’un tableau qu’une fois la compilation de l’intégralité du tableau terminée.

Si tout le contenu de la page figure dans un tableau volumineux, le navigateur doit terminer la compilation afin d’afficher quoi que ce soit.

En plaçant l’appel au fichier de bibliothèque JavaScript en dehors des balises du tableau, vous avez la garantie que l’appel aux serveurs Analytics n’a aucune incidence sur le contenu de la page.

>[!NOTE]
>
>Le fichier doit être placé dans une position légale pour les images et doit apparaître entre la balise d’ouverture <body> et la balise </body> de fermeture.

