---
description: Découvrez comment utiliser le mode hors ligne pour renvoyer des données d’espace réservé.
title: Activation du mode hors ligne
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 15%

---

# Mode hors ligne pour la création et la modification de requêtes

{{legacy-arb}}

Le mode hors ligne renvoie des données d’espace réservé afin d’accélérer le processus de création et de modification des requêtes.

Lorsque vous créez ou modifiez une requête, des appels d’API de rapport sont effectués pour récupérer la réponse. Parfois, ces appels ralentissent le processus de création de requête, car vous devez attendre que les données reviennent avant de passer à l’étape suivante. Le mode hors ligne renvoie uniquement les données d’espace réservé et les API ne sont pas créées.

Pour activer le mode hors ligne

1. Cliquez sur **[!UICONTROL Options]** dans le menu du Report Builder.

   ![Copie d’écran de l’écran Options avec le mode hors ligne sélectionné.](assets/offline_mode.png)

1. Cochez la case en regard de **[!UICONTROL Activer le mode hors ligne pour créer et modifier des requêtes]**.
1. Dans le champ **[!UICONTROL Afficher les données de mesure sous]**, saisissez les données d’espace réservé à renvoyer dans votre requête. Par exemple, saisissez « 1 ».
1. Cliquez sur **[!UICONTROL OK]**.
1. Créez et exécutez votre requête en mode hors ligne à l’aide de l’Assistant Requête. La capture d’écran suivante présente un exemple de requête avec « 1 » comme données d’espace réservé.

   ![Capture d’écran montrant l’exemple de mode hors ligne utilisant 1 comme espace réservé.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Assurez-vous d’avoir désactivé le mode hors ligne avant d’exécuter vos requêtes avec des données réelles.
