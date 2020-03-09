---
description: valeur nulle
title: Limitations et spécifications
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Limitations et spécifications

## Restrictions de publication de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

> [!NOTE] Ces restrictions ne s’appliquent qu’à l’option « Publier les requêtes du Report Builder en tant que tableaux de jeu de données Power BI ».

* 100 requêtes du Report Builder peuvent être exportées au maximum vers Power BI par classeur.
* Le processus de planification arrêtera l’exportation des requêtes une fois que la 101e requête sera atteinte.
* Seules les 10 000 premières lignes de données d’analyse seront envoyées à Power BI par requête du Report Builder. Les lignes restantes seront ignorées.

## Modifier une requête du Report Builder après sa publication sur Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

> [!NOTE] Cette spécification s’applique aux options « Publier toutes les requêtes du Report Builder en tant que tableaux de jeu de données Power BI » et « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI ».

La modification d’une requête du Report Builder après sa publication sur Power BI peut entraîner des problèmes.

* **Cas 1** : Vous publiez un classeur sur Power BI et créez une visualisation à partir de ses données. Par la suite, vous apportez des modifications au classeur qui font disparaître l’une des colonnes du jeu de données à laquelle il fait référence. Puis vous republiez. Cela aura pour effet de corrompre la visualisation dans Power BI.

   **Voici un exemple de la façon dont la visualisation SERA corrompue :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) sur Power BI.
   1. Dans Power BI, créez une visualisation pour Page et Pages vues.
   1. Maintenant, modifiez le classeur en supprimant Pages vues de la requête.
   1. Modifiez la planification avec le classeur mis à jour et republiez la requête sur Power BI.
   1. Une fois que le nouveau classeur est envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant qui avait été créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page et Visites.
      1. Vérifiez que votre visualisation est corrompue, étant donné qu’elle fait référence à la colonne Pages vues qui n’existe plus dans le tableau page_1.
   **Voici un exemple de la façon dont la visualisation NE sera PAS corrompue :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) sur Power BI.
   1. Dans Power BI, créez une visualisation pour Page et Pages vues.
   1. Maintenant, modifiez le classeur dans Report Builder, en ajoutant la mesure Visites tout en conservant Page et Pages vues.
   1. Modifiez la planification avec le classeur mis à jour et republiez la requête sur Power BI.
   1. Une fois que le nouveau classeur est envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant qui avait été créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page, Pages vues et Visites.
      1. Vérifiez que votre visualisation continue de fonctionner correctement, étant donné qu’elle fait référence à deux colonnes qui sont toujours présentes dans le tableau page_1.


* **Cas 2** : Vous épinglez une section de votre classeur dans un tableau de bord de Power BI ; par la suite, vous supprimez cette section épinglée (par exemple, un graphique ou un tableau) du classeur. Cela entraîne la corruption de la visualisation.

## Modifier le nom d’un rapport Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Par défaut, le nom sera renseigné à partir du nom de fichier du classeur (sans l’extension .xlsx), à cela près que les espaces seront remplacés par des caractères de soulignement.

Gardez à l’esprit que :

* L’intitulé ne peut pas être une combinaison de lettres et de nombres qui pourrait être confondue avec une adresse de ligne et de colonne. Par exemple, A100 ne peut pas être un intitulé car il s’agit de l’adresse d’une cellule de feuille de calcul.
* Les caractères suivants ne sont pas des caractères d’intitulé valides : ’#’, ’@’, ’!’, ’$’, ’^’, ’&amp;’, ’*’, ’`’, ’~’, ’ ’ . Ils seront remplacés par un caractère de soulignement.
* Lorsque vous entrez un nom incorrect, un message d’avertissement s’affiche pour vous suggérer un nom généré automatiquement. Si vous cliquez sur **[!UICONTROL Oui]**, ce nom sera utilisé. Si vous cliquez sur **[!UICONTROL Non]**, l’interface utilisateur de l’Assistant Options avancées vous permet d’entrer le nouveau nom.

