---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Configurer une destination de rapport pour une requête Data Warehouse
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 33%

---

# Configuration des options de planification pour une requête Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes décrivent comment configurer les options de planification pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les options de planification d’une requête Data Warehouse :

1. Si vous ne l’avez pas déjà fait, commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête Data Warehouse , sélectionnez l’onglet [!UICONTROL **Options de planification**].

   ![Onglet Destination du rapport](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Envoyer le rapport maintenant**] | Envoie le rapport en tant que rapport unique. Lorsque cette option est sélectionnée, toutes les options de planification sont masquées. |
   | [!UICONTROL **Planifier pour plus tard**] | Fournit des options pour planifier la diffusion de rapports. Toutes les options sont décrites ci-dessous. |
   | [!UICONTROL **Fréquence des rapports**] | Fréquence de diffusion des rapports. <p>Les options disponibles sont les suivantes :</p><ul><li>Toutes les heures</li><p>Le paramètre [!UICONTROL **Horaire**] n’est disponible que lorsque l’option [!UICONTROL **Périodes**] de l’onglet [!UICONTROL **Paramètres généraux**] est définie sur [!UICONTROL **Dernière heure**].</p><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Annuel</li></ul><p>D’autres options s’affichent selon la fréquence sélectionnée.</p> |
   | [!UICONTROL **À partir du**] | Date à laquelle la nouvelle planification doit commencer. |
   | [!UICONTROL **Heure de la journée**] | Heure à laquelle le rapport doit être envoyé. |
   | [!UICONTROL **Options de diffusion de fin**] | Choisissez quand terminer les diffusions planifiées. Vous pouvez choisir de ne jamais terminer, de se terminer après un nombre spécifique d’occurrences ou de se terminer à une date spécifique. |

   {style="table-layout:auto"}

1. Continuez à configurer votre requête Data Warehouse dans l’onglet [!UICONTROL **E-mail de notification**]. Pour plus d’informations, voir [Configuration d’un e-mail de notification pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).
