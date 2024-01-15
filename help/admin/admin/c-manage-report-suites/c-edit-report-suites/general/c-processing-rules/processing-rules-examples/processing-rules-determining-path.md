---
description: Vous pouvez copier la valeur d’une variable eVar sur une valeur Prop pour activer le cheminement.
subtopic: Processing rules
title: Déterminer un chemin en copiant une valeur eVar sur une valeur prop
feature: Admin Tools
role: Admin
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 100%

---

# Déterminer un chemin en copiant une valeur eVar sur une valeur prop

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
