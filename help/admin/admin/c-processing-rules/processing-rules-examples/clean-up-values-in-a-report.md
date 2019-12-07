---
description: Vous pouvez rechercher les fautes d’orthographe courantes dans les valeurs et les mettre à jour afin qu’elles s’affichent correctement dans les rapports.
subtopic: Processing rules
title: Nettoyer les valeurs d’un rapport
topic: Admin tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Nettoyer les valeurs d’un rapport

Vous pouvez rechercher les fautes d’orthographe courantes dans les valeurs et les mettre à jour afin qu’elles s’affichent correctement dans les rapports.

Pour éviter toute correspondance accidentelle avec d’autres valeurs, utilisez l’option de correspondance la plus restrictive possible. Vous pouvez exécuter un rapport sur la variable (prop1 dans l’exemple ci-dessous) et rechercher les candidats au remplacement pour être sûr d’éviter toute correspondance avec des valeurs non voulues. Les comparaisons de chaînes ne sont pas sensibles à la casse.

| Jeu de règles | Valeur |
|---|---|
| Condition | Si prop1 commence par Shopping |
| Action | Remplacer la valeur de prop1 par la valeur personnalisée Shopping |

Par exemple :

![](assets/clean-up-values-in-report.png)

