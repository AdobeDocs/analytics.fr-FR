---
title: FAQ sur les classifications
description: Questions fréquentes sur l’utilisation des classifications.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---


# FAQ sur les classifications

Questions fréquentes sur l’utilisation des classifications.

## Comment puis-je classer l’élément de dimension &quot;0&quot; ?

Les fichiers de classification chargés avec une valeur de clé ou une valeur de classification de zéro (`0`) génèrent une erreur. Elle comprend toutes les valeurs qui ne contiennent que des zéros (`00`, `000`etc.). Il existe plusieurs méthodes pour résoudre ce problème :

* **Mettez en oeuvre des valeurs** alternatives : L’utilisation d’une valeur de texte autre que `"0"` celle de la méthode la plus simple et la plus efficace pour résoudre ce problème. Par exemple, remplacez `s.campaign = "0";` votre mise en oeuvre par `s.campaign = "Zero";`.

* **Utiliser les règles** de traitement : Vous pouvez modifier des éléments de dimension entre la collecte de données et leur enregistrement dans une suite de rapports. Créez la règle de traitement suivante :

   *Si la[dimension]est égale`0`, remplacez la valeur de[dimension]par la valeur personnalisée`Zero`.*

* **Demander une règle** VISTA : Un consultant en services d&#39;ingénierie vous configurez une règle côté serveur à un coût supplémentaire. Contactez le gestionnaire de compte de votre organisation pour demander une règle VISTA.

## Puis-je utiliser l’importateur de classifications pour classer les éléments de dimension qui n’existent pas encore ?

Oui, *toutefois, cela comptabilise chaque élément de dimension comme un appel serveur facturable.*

* Les articles de Dimension existants n&#39;impliquent aucun coût supplémentaire.
* L’utilisation du créateur de règles de classification ne classe pas les éléments inexistants et n’entraîne donc aucun coût supplémentaire.

## Comment classifier les valeurs qui contiennent des caractères spéciaux ?

Il n’est généralement pas recommandé d’utiliser des caractères spéciaux tels que des virgules ou des guillemets de doublon dans le rapports. Cependant, dans certains cas, leur utilisation est nécessaire. Si vos valeurs de rapports contiennent des caractères que vous choisissez de classifier, procédez comme suit :

1. Connectez-vous à Adobe Analytics, puis accédez à **[!UICONTROL Admin]** > Importateur **[!UICONTROL de]** classifications.
2. Click the **[!UICONTROL Browser export]** tab.
3. Configurez les paramètres d&#39;exportation et assurez-vous que l&#39;option Sortie du devis n&#39;est PAS sélectionnée.
4. Cliquez sur **[!UICONTROL Exporter un fichier]**, puis ouvrez le fichier téléchargé dans un éditeur de feuille de calcul.
5. À la ligne 1, localisez la cellule C1, qui contient la valeur `v:2.0`. Modifiez la valeur `v:2.1` et appliquez les classifications de votre choix au classeur.
6. Téléchargez le fichier comme vous le feriez pour toute autre classification.

## Que sont les classifications numériques 2 ?

Les classifications numériques 2 vous permettent de classer les éléments de dimension en tant que mesures temporelles. Ils ont été retirés de l’interface utilisateur d’Analytics en juillet 2019.
