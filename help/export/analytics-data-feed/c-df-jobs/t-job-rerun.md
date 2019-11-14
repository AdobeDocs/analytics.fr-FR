---
description: Vous pouvez réexécuter une ou plusieurs tâches de la liste.
keywords: Data Feed;job;rerun
solution: Analytics
title: Réexécution d’une tâche
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Réexécution d’une tâche

Vous pouvez réexécuter une ou plusieurs tâches de la liste.

1. Sélectionnez une ou plusieurs tâches que vous souhaitez réexécuter.
1. Click **[!UICONTROL Rerun Job]**.

   Le processus de réexécution dépend de l’état actuel de la tâche :

   | État | Nom du fichier en cache sur le serveur | Processus |
   |---|---|---|
   | Terminé | Oui | Le fichier a été renvoyé. |
   | Terminé | Non | La tâche sera retraitée, puis renvoyée. |
   | Échec | Non | La tâche sera retraitée, puis renvoyée. |
   | Autre état | s.o. | Non pris en charge. |

