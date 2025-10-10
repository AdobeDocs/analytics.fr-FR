---
description: Découvrez comment utiliser le mode hors ligne pour renvoyer des données d’espace réservé.
title: Activation du mode hors ligne
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 33%

---

# Mode hors ligne pour la création et la modification de requêtes

{{legacy-arb}}

Le mode hors ligne renvoie des données d’espace réservé afin d’accélérer le processus de création et de modification des requêtes.

Lorsque vous créez ou modifiez une requête, des appels d’API de rapport sont effectués pour récupérer la réponse. Parfois, ces appels ralentissent le processus de création de requête, car vous devez attendre que les données reviennent avant de passer à l’étape suivante. Le mode hors ligne renvoie uniquement les données d’espace réservé et les API ne sont pas créées.

Pour activer le mode hors ligne

1. Cliquez sur **[!UICONTROL Options]** dans le menu du Report Builder.

   ![Copie d’écran de l’écran Options avec le mode hors ligne sélectionné.](assets/offline_mode.png)

1. Cochez la case en regard de l’option **[!UICONTROL Passez hors ligne pour créer/modifier des demandes]**.
1. Dans le champ **[!UICONTROL Afficher les données de mesure au format]**, saisissez les données d’espace réservé que vous voulez renvoyer dans votre requête. Par exemple, saisissez « 1 ».
1. Cliquez sur **[!UICONTROL OK]**.
1. Créez et exécutez votre requête en mode hors ligne à l’aide de l’Assistant Requête. La capture d’écran suivante présente un exemple de requête avec « 1 » comme données d’espace réservé.

   ![Capture d’écran montrant l’exemple de mode hors ligne utilisant 1 comme espace réservé.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Assurez-vous d’avoir désactivé le mode hors ligne avant d’exécuter vos requêtes avec des données réelles.
