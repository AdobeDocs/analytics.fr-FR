---
description: Vous pouvez copier la valeur d’une variable eVar sur une valeur Prop pour activer le cheminement.
seo-description: Vous pouvez copier la valeur d’une variable eVar sur une valeur Prop pour activer le cheminement.
seo-title: Détermination d'un chemin en copiant une valeur evar dans une prop
solution: Analytics
subtopic: Règles de traitement
title: Détermination d'un chemin en copiant une valeur evar dans une prop
topic: Outils d’administration
uuid: 8 d 7647 c 7-aa 91-466 b -8 d 31-fb 4 dce 83 f 04 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Détermination d'un chemin en copiant une valeur evar dans une prop

Vous pouvez copier la valeur d’une variable eVar sur une valeur Prop pour activer le cheminement.

Lors de la définition de valeurs, la variable de gauche reçoit la valeur (même si elle est vide) de la variable de droite.

| Jeu de règles | Valeur |
|---|---|
| Condition | Aucun (toujours exécuter) |
| Action | Remplacer la valeur de Prop1 par eVar1 |

Vous ne pouvez modifier cette règle pour définir la valeur de Prop1 que si elle ne contient pas encore de valeur, comme indiqué ci-dessous :

| Jeu de règles | Valeur |
|---|---|
| Condition | Si Prop1 n’est pas défini |
| Action | Remplacer la valeur de Prop1 par eVar1 |

Par exemple :

![](assets/overwrite-empty-prop.png)

