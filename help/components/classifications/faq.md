---
title: FAQ sur les classifications
description: Questions fréquentes sur l’utilisation des classifications.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '202'
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

## Puis-je utiliser le chargeur pour classer les éléments de dimension qui n’existent pas encore ?

Oui, *toutefois, cela comptabilise chaque élément de dimension comme un appel serveur facturable.*

* Les articles de Dimension existants n&#39;impliquent aucun coût supplémentaire.
* L’utilisation du créateur de règles de classification ne classe pas les éléments inexistants et n’entraîne donc aucun coût supplémentaire.
