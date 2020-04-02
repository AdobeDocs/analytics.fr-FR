---
description: Nombre de fois où une valeur a été définie pour une variable.
keywords: instances
title: Instances
topic: Metrics
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instances

Nombre de fois où une valeur a été définie pour une variable.

Instances  Les sont comptabilisées pour tous les types d’accès mais ne sont pas comptabilisées lorsqu’une valeur est enregistrée pour une variable sur un accès suivant en raison de la persistance.

Par exemple, si un utilisateur arrive sur votre site via [!DNL example.com], la première requête d’image effectuée sur votre site contient le référent de [!DNL example.com]. Lors de la définition de cette valeur, une instance est attribuée à [!DNL example.com] même si ce référent est enregistré pour toutes les pages vues au cours de cette visite.

Les instances relatives aux variables de conversion de Data Warehouse ont été ajoutées à la mi-2011, permettant ainsi aux demandes de Data Warehouse de traiter une instance de variable de conversion spécifique comme une mesure. Ces mesures ne sont pas disponibles à des fins de création de rapports avant la date de leur introduction.
