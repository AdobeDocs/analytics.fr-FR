---
description: valeur nulle
seo-description: valeur nulle
seo-title: Limites et spécifications
title: Limites et spécifications
uuid: 6717 b 6 ea -7 e 01-49 b 8-8 f 6 e-fb 733 a 03 b 687
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Limites et spécifications

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Ces restrictions s'appliquent uniquement à l'option « Publier les requêtes Créateur de rapports sous forme de tableaux de jeu de données BI Power ».

* 100 requêtes du Créateur de rapports peuvent être exportées au maximum vers Power BI par classeur.
* Le processus de planification arrêtera l’exportation des requêtes une fois que la 101e requête sera atteinte.
* Seules les 10 000 premières lignes de données d’analyse seront envoyées à Power BI par requête du Créateur de rapports. Les lignes restantes seront ignorées.

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Cette spécification s'applique aux options « Publier toutes les requêtes du créateur de rapports sous forme de tableaux de jeu de données BI Power » et « Publier tous les tableaux formatés dans le classeur sous forme de tableaux de jeu de données Power BI ».

La modification d’une requête du Créateur de rapports après sa publication sur Power BI peut entraîner des problèmes.

* **Cas 1** : Vous publiez un classeur sur Power BI et créez une visualisation à partir de ses données. Par la suite, vous apportez des modifications au classeur qui font disparaître l’une des colonnes du jeu de données à laquelle il fait référence. Puis vous republiez. Cela aura pour effet de corrompre la visualisation dans Power BI.

   **Voici un exemple de la façon dont la visualisation SERA corrompue :**

   1. Dans Créateur de rapports, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) sur Power BI.
   1. Dans Power BI, créez une visualisation pour Page et Pages vues.
   1. Maintenant, modifiez le classeur en supprimant Pages vues de la requête.
   1. Modifiez la planification avec le classeur mis à jour et republiez la requête sur Power BI.
   1. Une fois que le nouveau classeur est envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant qui avait été créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page et Visites.
      1. Vérifiez que votre visualisation est corrompue, étant donné qu’elle fait référence à la colonne Pages vues qui n’existe plus dans le tableau page_1.
   **Voici un exemple de la façon dont la visualisation NE sera PAS corrompue :**

   1. Dans Créateur de rapports, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) sur Power BI.
   1. Dans Power BI, créez une visualisation pour Page et Pages vues.
   1. Maintenant, modifiez le classeur dans Créateur de rapports, en ajoutant la mesure Visites tout en conservant Page et Pages vues.
   1. Modifiez la planification avec le classeur mis à jour et republiez la requête sur Power BI.
   1. Une fois que le nouveau classeur est envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant qui avait été créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page, Pages vues et Visites.
      1. Vérifiez que votre visualisation continue de fonctionner correctement, étant donné qu’elle fait référence à deux colonnes qui sont toujours présentes dans le tableau page_1.


* **Cas 2** : Vous épinglez une section de votre classeur dans un tableau de bord de Power BI ; par la suite, vous supprimez cette section épinglée (par exemple, un graphique ou un tableau) du classeur. Cela entraîne la corruption de la visualisation.

## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Par défaut, le nom sera renseigné à partir du nom de fichier du classeur (sans l’extension .xlsx), à cela près que les espaces seront remplacés par des caractères de soulignement.

Gardez à l’esprit que :

* L’intitulé ne peut pas être une combinaison de lettres et de nombres qui pourrait être confondue avec une adresse de ligne et de colonne. Par exemple, A100 ne peut pas être un intitulé car il s’agit de l’adresse d’une cellule de feuille de calcul.
* Les caractères suivants ne sont pas des caractères d’intitulé valides : ’#’, ’@’, ’!’, ’$’, ’^’, ’&amp;’, ’*’, ’`’, ’~’, ’ ’ . Ils seront remplacés par un caractère de soulignement.
* Lorsque vous entrez un nom incorrect, un message d’avertissement s’affiche pour vous suggérer un nom généré automatiquement. If you click **[!UICONTROL Yes]**, this name will be used. If you click **[!UICONTROL No]**, the Advanced Wizard UI will let you enter the new name.

