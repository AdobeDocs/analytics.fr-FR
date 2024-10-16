---
description: Découvrez comment utiliser le mode hors ligne pour renvoyer des données d’espace réservé.
title: Comment activer le mode hors ligne
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 33%

---

# Mode hors ligne pour la création et la modification de requêtes

Le mode hors ligne renvoie des données d’espace réservé afin d’accélérer le processus de création et de modification des requêtes.

Lorsque vous créez ou modifiez une requête, des appels d’API de rapport sont effectués pour récupérer la réponse. Parfois, ces appels ralentissent le processus de création de requête, car vous devez attendre que les données reviennent avant de passer à l’étape suivante. Le mode hors ligne renvoie uniquement les données d’espace réservé et les API ne sont pas créées.

Pour activer le mode hors ligne

1. Cliquez sur **[!UICONTROL Options]** dans le menu du Report Builder.

   ![Capture d&#39;écran de l&#39;écran Options avec codage hors ligne sélectionné.](assets/offline_mode.png)

1. Cochez la case en regard de l’option **[!UICONTROL Passez hors ligne pour créer/modifier des demandes]**.
1. Dans le champ **[!UICONTROL Afficher les données de mesure au format]**, saisissez les données d’espace réservé que vous voulez renvoyer dans votre requête. Par exemple, saisissez « 1 ».
1. Cliquez sur **[!UICONTROL OK]**.
1. Créez et exécutez votre requête en mode hors ligne à l’aide de l’Assistant Requête. La capture d’écran suivante illustre un exemple de requête avec &quot;1&quot; comme données d’espace réservé.

   ![Capture d&#39;écran montrant l&#39;exemple de mode hors ligne utilisant 1 comme espace réservé.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Veillez à désactiver le mode hors ligne avant d’exécuter vos requêtes avec des données réelles.
