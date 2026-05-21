---
description: Limitations lors de lʼutilisation de Report Builder et de Microsoft Power BI.
title: Limitations et spécifications
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
TQID: https://experienceleague.adobe.com/L3R3ufcclrTpw-fKoFLD8Y-v56rTm4tXlXqjaTdmdoQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 631
ht-degree: 34%

---

# Limitations et spécifications

{{legacy-arb}}

## Restrictions de publication de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Ces restrictions ne s’appliquent qu’à l’option « Publier les requêtes du Report Builder en tant que tableaux de jeu de données Power BI ».

* 100 requêtes du Report Builder peuvent être exportées au maximum vers Power BI par classeur.
* Le processus de planification cessera d’exporter des demandes lorsque la 101e demande sera atteinte.
* Seules les 10 000 premières lignes de données d’analyse seront envoyées à Power BI par requête du Report Builder. Les lignes restantes seront ignorées.

## Modifier une requête du Report Builder après sa publication sur Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Cette spécification s’applique aux options « Publier toutes les requêtes du Report Builder en tant que tableaux de jeu de données Power BI » et « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI ».

La modification d’une requête du Report Builder après sa publication sur Power BI peut entraîner des problèmes.

* **Cas 1** : vous publiez un classeur dans Power BI et créez une visualisation basée sur ses données. Ensuite, vous apportez des modifications au classeur, ce qui entraîne la disparition de l’une des colonnes du jeu de données auquel elle fait référence. Ensuite, vous republiez. La visualisation dans Power BI est alors interrompue.

  **Voici un exemple de la manière dont la visualisation sera rompue :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   2. Planifiez la publication de cette requête sur Power BI.
   3. Dans Power BI, créez une visualisation pour les pages vues et les pages vues.
   4. Modifiez maintenant le classeur en supprimant Pages vues de la requête.
   5. Modifiez le planning avec le classeur mis à jour et republiez la demande dans Power BI.
   6. Une fois le nouveau classeur envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant créé lors de la première publication.
      2. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page et Visites .
      3. Vérifiez que votre visualisation est endommagée, car elle fait référence à la colonne Pages vues qui n’est plus présente dans le tableau page_1.

  **Voici un exemple de la manière dont la visualisation ne sera PAS rompue :**

   1. Dans Report Builder, créez un classeur avec une requête, en utilisant la dimension Page et la mesure Pages vues.
   2. Planifiez la publication de cette requête sur Power BI.
   3. Dans Power BI, créez une visualisation pour les pages vues et les pages vues.
   4. Maintenant, modifiez le classeur dans Report Builder, en ajoutant la mesure Visites tout en conservant Page et Pages vues.
   5. Modifiez le planning avec le classeur mis à jour et republiez la demande dans Power BI.
   6. Une fois le nouveau classeur envoyé à Power BI

      1. Vérifiez qu’il a remplacé le jeu de données existant créé lors de la première publication.
      2. Vérifiez que le tableau page_1 est correctement mis à jour avec les colonnes Page, Pages vues et Visites.
      3. Vérifiez que votre visualisation continue à fonctionner correctement, car elle fait référence à deux colonnes toujours présentes dans le tableau page_1.

* **Cas 2** : vous épinglez une section de votre classeur sur un tableau de bord dans Power BI, puis vous supprimez cette section épinglée (un graphique ou un tableau, par exemple) du classeur. La visualisation est alors interrompue.

## Modifier le nom d’un rapport Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Par défaut, le nom est renseigné à partir du nom de fichier du classeur (sans l’extension .xlsx), sauf que les espaces sont remplacés par des caractères de soulignement.

Gardez à l’esprit que :

* L’étiquette ne peut pas être une combinaison de lettres et de chiffres qui pourrait être confondue avec une adresse de ligne et de colonne. Par exemple, A100 ne peut pas être un libellé parce qu&#39;il s&#39;agit de l&#39;adresse d&#39;une cellule dans une feuille de calcul.
* Les caractères suivants ne sont pas des caractères d’intitulé valides : `'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; et `'~', ' '`. Ils sont remplacés par un caractère de soulignement.
* Lorsque vous saisissez un nom non valide, un message d’avertissement s’affiche pour suggérer un nom généré automatiquement. Si vous cliquez sur **[!UICONTROL Oui]**, ce nom est utilisé. Si vous cliquez sur **[!UICONTROL Non]**, l’interface utilisateur de l’Assistant Avancé vous permet de saisir le nouveau nom.
