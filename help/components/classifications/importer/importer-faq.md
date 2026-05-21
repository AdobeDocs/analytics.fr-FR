---
title: FAQ sur les classifications
description: Forum aux questions sur l’utilisation des classifications.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
TQID: https://experienceleague.adobe.com/pIwAdewnHA4AB9hyRDRkH6xXvyxx-BceWvDXMydX-ew
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 87%

---

# FAQ sur l’importateur de classifications

{{classification-importer-deprecation}}

Questions fréquentes sur l’utilisation de l’importateur de classifications.

## Comment classer l’élément de dimension « 0 » ?

Les fichiers de classification chargés avec une valeur de clé ou une valeur de classification de zéro (`0`) génèrent une erreur. Cela comprend toutes les valeurs qui ne contiennent que des zéros (`00`, `000`, etc.). Plusieurs méthodes permettent de résoudre ce problème :

* **Mise en œuvre de valeurs alternatives** : l’utilisation d’une valeur de texte autre que `"0"` constitue la méthode la plus simple et la plus efficace pour résoudre ce problème. Par exemple, remplacez `s.campaign = "0";` dans votre mise en œuvre par `s.campaign = "Zero";`.

* **Utilisation des règles de traitement** : vous pouvez modifier des éléments de dimension entre la collecte de données et leur enregistrement dans une suite de rapports. Création de la règle de traitement suivante :

  *Si la [dimension] est égale à `0`, remplacez la valeur de la [dimension] par la valeur personnalisée `Zero`.*

* **Demande d’une règle VISTA** : un conseiller des services d’ingénierie configure une règle côté serveur pour vous, moyennant un coût supplémentaire. Contactez votre équipe Adobe en charge des comptes pour demander une règle VISTA.

## Puis-je utiliser l’importateur de classifications pour classer les éléments de dimension qui n’existent pas encore ?

Oui, *toutefois, cela comptabilise chaque élément de dimension comme un appel au serveur facturable.*

* Les éléments de dimension qui existent déjà n’entraînent aucun coût supplémentaire.
* L’utilisation du créateur de règles de classification ne classe pas les éléments inexistants et n’entraîne donc aucun coût supplémentaire.

## Comment classer les valeurs contenant des caractères spéciaux ?

L’utilisation d’espaces vides au début et à la fin dans les données de classification et les données d’accès n’est pas prise en charge, car Adobe Analytics tronque automatiquement les caractères vides.

Il n’est généralement pas recommandé d’utiliser des caractères spéciaux tels que des virgules ou des guillemets dans les rapports. Cependant, dans certains cas, leur utilisation est nécessaire. Si vos valeurs de rapports contiennent des caractères que vous choisissez de classer, procédez comme suit :

1. Connectez-vous à Adobe Analytics, puis accédez à **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
2. Cliquez sur l’onglet **[!UICONTROL Exportation navigateur]**.
3. Configurez les paramètres d’exportation et assurez-vous que l’option « Sortie entre guillemets » n’est PAS sélectionnée.
4. Cliquez sur **[!UICONTROL Exporter un fichier]**, puis ouvrez le fichier téléchargé dans un éditeur de feuille de calcul.
5. Sur la ligne 1, localisez la cellule C1, qui contient la valeur `v:2.0`. Remplacez la valeur par `v:2.1` et appliquez les classifications de votre choix au classeur.
6. Chargez le fichier comme vous le feriez pour toute autre classification.

## Que sont les classifications numériques 2 ?

Les classifications numériques 2 vous permettent de classer les éléments de dimension en tant que mesures basées sur le temps. Elles ont été retirées de l’IU d’Adobe Analytics en juillet 2019.

## Comment placer des données dans une séquence d’échappement dans un fichier de classification ?

Entourez le champ contenant des caractères spéciaux entre guillemets doubles (`"`). Le caractère double guillemet peut apparaître dans une cellule placée dans une séquence d’échappement en le remplaçant par deux caractères guillemets doubles (`" "`). Par exemple :

```
My String "of data"
```

Le placement en séquence d’échappement serait :

```
"My String ""of data"""
```
