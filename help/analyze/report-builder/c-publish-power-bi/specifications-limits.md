---
description: valeur nulle
title: Limitations et spécifications
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Limitations et spécifications

## Restrictions de publication de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE] Ces restrictions ne s’appliquent qu’à l’option « Publier les requêtes du Report Builder en tant que tableaux de jeu de données Power BI ».

* 100 requêtes du Report Builder peuvent être exportées au maximum vers Power BI par classeur.
* Le processus de planification interrompt l’exportation des requêtes lorsque la 101e requête est atteinte.
* Seules les 10 000 premières lignes de données d’analyse seront envoyées à Power BI par requête du Report Builder. Les lignes restantes seront ignorées.

## Modifier une requête du Report Builder après sa publication sur Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE] Cette spécification s’applique aux options « Publier toutes les requêtes du Report Builder en tant que tableaux de jeu de données Power BI » et « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI ».

La modification d’une requête du Report Builder après sa publication sur Power BI peut entraîner des problèmes.

* **Cas 1**: Vous publiez un classeur dans Power BI et créez une visualisation basée sur ses données. Ensuite, vous apportez des modifications au classeur, provoquant la disparition de l’une des colonnes du jeu de données auquel il fait référence. Vous republiez ensuite. Cela va briser la visualisation dans Power BI.

   **Voici un exemple de rupture de la visualisation :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) sur Power BI.
   1. Dans Power BI, créez une visualisation pour les  de page et de page.
   1. Modifiez maintenant le classeur en supprimant les  de page de la requête.
   1. Modifiez la planification avec le classeur mis à jour et publiez à nouveau la requête dans Power BI.
   1. Une fois le nouveau classeur envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page et Visites.
      1. Vérifiez que votre visualisation est rompue, puisqu’elle fait référence à la colonne  de page qui n’est plus présente dans le tableau page_1.
   **Voici un exemple de la façon dont la visualisation ne se rompt PAS :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   1. [Planifiez la publication de cette requête](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) sur Power BI.
   1. Dans Power BI, créez une visualisation pour les  de page et de page.
   1. Maintenant, modifiez le classeur dans Report Builder, en ajoutant la mesure Visites tout en conservant Page et Pages vues.
   1. Modifiez la planification avec le classeur mis à jour et publiez à nouveau la requête dans Power BI.
   1. Une fois le nouveau classeur envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant créé lors de la première publication.
      1. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page, de page et Visites.
      1. Vérifiez que votre visualisation continue de fonctionner correctement, puisqu’elle fait référence à deux colonnes qui sont toujours présentes dans le tableau page_1.


* **Cas 2**: Vous épinglez une section de votre classeur vers un dans Power BI et vous supprimez ensuite cette section épinglée (un graphique ou un tableau, par exemple) du classeur. Cela rompra la visualisation.

## Modifier le nom d’un rapport Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Par défaut, le nom est renseigné à partir du nom de fichier du classeur (sans l’extension .xlsx), sauf que les espaces sont remplacés par des caractères de soulignement.

N’oubliez pas que

* Le libellé ne peut pas être une combinaison de lettres et de chiffres qui peut être confondue avec une adresse de ligne et de colonne. Par exemple, A100 ne peut pas être une étiquette, car il s’agit de l’adresse d’une cellule d’une feuille de calcul.
* Les caractères suivants ne sont pas des caractères d’étiquette valides : &#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39;~&#39;, &#39; . Ils seront remplacés par un trait de soulignement.
* Lorsque vous saisissez un nom non valide, un message d’avertissement s’affiche, indiquant un nom généré automatiquement. Si vous cliquez sur **[!UICONTROL Yes]**, ce nom sera utilisé. Si vous cliquez sur **[!UICONTROL No]**, l&#39;interface utilisateur de l&#39;Assistant avancé vous permet de saisir le nouveau nom.

