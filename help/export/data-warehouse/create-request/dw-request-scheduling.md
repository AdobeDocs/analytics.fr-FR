---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Configuration d’une destination de rapport pour une requête de Data Warehouse
feature: Data Warehouse
source-git-commit: 393355cd971f264da3e3e1b8736f5752fc4bdc62
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 13%

---

# Configuration des options de planification pour une requête de Data Warehouse

{{release-limited-testing}}

Plusieurs options de configuration sont disponibles lors de la création d’une requête de Data Warehouse. Les informations suivantes décrivent comment configurer les options de planification pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les options de planification d’une requête de Data Warehouse :

1. Commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse , sélectionnez le [!UICONTROL **Options de planification**] .

   ![Onglet Destination du rapport](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | Envoyer le rapport maintenant | Envoie le rapport sous la forme d’un rapport unique. Lorsque cette option est sélectionnée, toutes les options de planification sont masquées. |
   | Planifier pour plus tard | Fournit des options pour planifier la remise des rapports. Toutes les options sont décrites ci-dessous. |
   | Fréquence du rapport | Fréquence de remise des rapports. <p>Les options disponibles sont les suivantes :</p><ul><li>Toutes les heures</li><p>[!UICONTROL **Horaire**] est disponible uniquement lorsque la variable [!UICONTROL **Plages de dates**] sur l’option [!UICONTROL **Paramètres généraux**] est défini sur [!UICONTROL **Dernière heure**].</p><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Annuel</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | Périodicité mensuelle | Intervalle entre les mois d’envoi du rapport. |
   | Jour du mois | Date d’envoi du rapport chaque mois.<p>Lorsque cette option est disponible, la variable [!UICONTROL **Semaine du mois**] et [!UICONTROL **Jour de la semaine**] ne le sont pas. Sélectionnez la variable [!UICONTROL **Format alternatif**] pour basculer entre les deux. </p> |
   | Semaine du mois | La semaine de chaque mois où le rapport doit être envoyé. <p>Les options disponibles sont les suivantes :</p><ul><li>Premier</li><li>Seconde</li><li>Troisième</li><li>Quatrième</li><p>Envoyez le rapport la 4e semaine, même les mois de 5 semaines. Choisir [!UICONTROL **Dernière**] si vous souhaitez que le rapport soit envoyé la dernière semaine de chaque mois.</p><li>Dernière position</li></ul><p>Lorsque cette option est disponible, la variable [!UICONTROL **Jour du mois**] ne l’est pas. Sélectionnez la variable [!UICONTROL **Format alternatif**] pour basculer entre les deux. </p> |
   | Jour de la semaine | Jour de la semaine où le rapport doit être envoyé. <p>Lorsque cette option est disponible, la variable [!UICONTROL **Jour du mois**] ne l’est pas. Sélectionnez la variable [!UICONTROL **Format alternatif**] pour basculer entre les deux. </p> |
   | Début le | Date à laquelle le nouveau planning doit commencer. |
   | Heure | Heure de la journée d’envoi du rapport. |
   | Options de diffusion | Choisissez quand terminer les diffusions planifiées. Vous pouvez choisir de ne jamais se terminer, de ne pas terminer après un nombre spécifique d’occurrences ou de terminer à une date spécifique. |

   {style="table-layout:auto"}

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Email de notification**] . Pour plus d’informations, voir [Configuration d’un courrier électronique de notification pour une demande de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

