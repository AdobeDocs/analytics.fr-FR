---
description: Découvrez comment affecter des montants de coûts et de budget aux canaux.
seo-description: Découvrez comment affecter des montants de coûts et de budget aux canaux.
seo-title: Coûts et budgets
solution: Analytics
subtopic: Canaux marketing
title: Coûts et budgets
topic: Reports and Analytics
uuid: 7 ba 0 e 968-e 565-4 d 4 c -8 fc 0-39 bf 25 d 3 e 5 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Coûts et budgets

Découvrez comment affecter des montants de coûts et de budget aux canaux.

## Costs and budgets {#topic_7CCFD3B54440433FBA0E4EE127F58B0C}

Découvrez comment affecter des montants de coûts et de budget aux canaux.

Les coûts représentent ce que vous dépensez pour le canal. Le budget représente le montant disponible à dépenser.

Un moyen utile d’afficher le RSI consiste à créer une mesure calculée montrant les recettes moins les coûts. Vous pouvez également créer une mesure affichant le coût total avec une ventilation des coûts par nouvel engagement. Vous pouvez, par exemple, générer un rapport [!UICONTROL Canal Première touche] qui montre les nouveaux engagements, puis ajouter une mesure de coût Première touche qui vous montre le coût par nouvel engagement en créant une mesure calculée.

Reportez-vous à la section [Mesures calculées utilisées pour les rapports Canal marketing](../../components/c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74).

Vous ne pouvez attribuer des coûts et des budgets qu’aux canaux. Tous les coûts correspondent à une période pendant laquelle ils sont appliqués dans le cadre de la création de rapports. Lorsque les coûts sont directement associés à un canal, une mesure d’attribution est choisie pour indiquer le mode de ventilation des coûts entre les campagnes d’un même canal.

Après l’ajout des éléments de coût et de budget, vous pouvez exporter les données du tableau dans un fichier CSV. Vous pouvez également importer un fichier CSV vers la page Coûts du canal marketing.

## Ajout d’éléments de coûts et de budget {#task_9238A033994440748960DE21593E6388}

Ajoutez des éléments de coûts et de budget aux canaux marketing.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sur la page [!UICONTROL Gestionnaire de Report Suites], sélectionnez une suite de rapports.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. Sur la page [!UICONTROL Coûts du canal marketing]**, cliquez sur[!UICONTROL Ajouter l’élément Cost]** ou **[!UICONTROL Ajouter l’élément Budget]**.
1. Cliquez sur **[!UICONTROL Enregistrer.]**

   Pour continuer à ajouter des éléments de coûts, cliquez sur **[!UICONTROL Enregistrer et ajouter un autre élément]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#reference_0B193210E10A4B6B84A385A781FD9515}

Définition des champs relatifs aux coûts ou budgets de canal marketing.



| Champ | Définition |
|--- |--- |
| Nom | Le nom de l’élément de coût ou de budget. (Il s’agit de la valeur clé si vous utilisez SAINT.) |
| Canal | Le canal auquel vous souhaitez associer ce montant. Indiquez si le coût ou le budget s’applique à un canal Première touche ou Dernière touche. Considérez le montant de coût Première touche comme un nouvel engagement unique. Un montant de coût Dernière touche concerne les clics publicitaires. |
| Période | La période à utiliser pour ce montant. |
| Type | Le type de coût ou de budget, qu’il s’agisse d’un Taux ou d’un Coût unique. Le Taux indique un coût permanent ; par exemple un certain montant par clic. Le Coût unique permet de spécifier un montant « Réparti par ». Par exemple, si vous répartissez le coût par clics, l’affilié avec 60 % des clics totaux reçoit 60 % du coût total. La valeur Réparti par est la mesure utilisée lorsque vous ventilez des classifications numériques. |
| Exporter un fichier | Permet d’exporter les données du tableau au format CSV. |
| Importer un fichier | Permet d’importer un fichier CSV dans la page Coûts du canal marketing. |
