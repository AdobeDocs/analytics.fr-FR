---
description: En plaçant l’appel vers le fichier de bibliothèque JavaScript en haut de la page, vous avez la garantie que l’image fait partie des premiers éléments à être téléchargés.
keywords: Mise en œuvre d’Analytics
seo-description: En plaçant l’appel vers le fichier de bibliothèque JavaScript en haut de la page, vous avez la garantie que l’image fait partie des premiers éléments à être téléchargés.
seo-title: Emplacement et approbation du fichier JavaScript
solution: Analytics
subtopic: Résolution des problèmes
title: Emplacement et approbation du fichier JavaScript
topic: Développeur et mise en œuvre
uuid: ed 5118 a 8-b 142-4 fab -8 aa 1-92 d 931 cc 1439
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Emplacement et approbation du fichier JavaScript

En plaçant l’appel vers le fichier de bibliothèque JavaScript en haut de la page, vous avez la garantie que l’image fait partie des premiers éléments à être téléchargés.

La plupart des navigateurs Web téléchargent les images (généralement trois ou quatre) de manière simultanée.

En raison de cette simultanéité des téléchargements, la barre d’état de nombreux navigateurs utilisés couramment (dont Internet Explorer) n’indique pas avec précision l’élément qui fait l’objet d’une tentative de téléchargement. Ainsi, elle peut indiquer que votre navigateur attend le téléchargement de l’image 1. Or, les tests de paquets réseau font apparaître que votre navigateur a déjà reçu l’image 1 et attend actuellement l’image 2.

>[!NOTE]
>
>Comme les fournisseurs tiers d'audit de performances Internet (tels que Keynote Systems) téléchargent des éléments d'image de page de manière séquentielle, et non simultanément, ils ne reproduisent pas l'expérience utilisateur habituelle.

