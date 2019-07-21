---
description: Vous pouvez réexécuter une ou plusieurs tâches de la liste.
keywords: Flux de données ; tâche ; réexécution
seo-description: Vous pouvez réexécuter une ou plusieurs tâches de la liste.
seo-title: Réexécution d'une tâche
solution: Analytics
title: Réexécution d'une tâche
uuid: 5 caf 95 da-dd 88-4 b 1 a-a 081-684 f 4 fd 1 f 714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Réexécution d'une tâche

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

