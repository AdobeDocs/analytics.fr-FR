---
description: Découvrez comment attribuer des montants de coût et de budget aux canaux.
subtopic: Marketing channels
title: Coûts et budgets
topic: Reports and analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Coûts et budgets

Découvrez comment attribuer des montants de coût et de budget aux canaux.

Les coûts représentent ce que vous dépensez pour le canal. Le budget représente le montant disponible à dépenser.

Un moyen utile d’afficher le RSI consiste à créer une mesure calculée montrant les recettes moins les coûts. Vous pouvez également créer une mesure affichant le coût total avec une ventilation des coûts par nouvel engagement. Vous pouvez, par exemple, générer un rapport [!UICONTROL Canal Première touche] qui montre les nouveaux engagements, puis ajouter une mesure de coût Première touche qui vous montre le coût par nouvel engagement en créant une mesure calculée.

Reportez-vous à la section [Mesures calculées utilisées dans les rapports sur les canaux marketing](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

Vous ne pouvez attribuer des coûts et des budgets qu’aux canaux. Tous les coûts correspondent à une période pendant laquelle ils sont appliqués dans le cadre de la création de rapports. Lorsque les coûts sont directement associés à un canal, une mesure d’attribution est choisie pour indiquer le mode de ventilation des coûts entre les campagnes d’un même canal.

Après l’ajout des éléments de coût et de budget, vous pouvez exporter les données du tableau dans un fichier CSV. Vous pouvez également importer un fichier CSV vers la page Coûts du canal marketing.

## Ajout d’éléments de coûts et de budget {#add-cost-and-budget}

Ajoutez des éléments de coûts et de budget aux canaux marketing.

1. Cliquez sur **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Suites de rapports]**.
1. Sur la page [!UICONTROL Gestionnaire de Report Suites], sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Canaux marketing]** &gt; **[!UICONTROL Coûts du canal marketing]**.
1. Sur la page [!UICONTROL Coûts du canal marketing]**, cliquez sur[!UICONTROL Ajouter l’élément Cost]** ou **[!UICONTROL Ajouter l’élément Budget]**.
1. Cliquez sur **[!UICONTROL Enregistrer.]**

   Pour continuer à ajouter des éléments de coûts, cliquez sur **[!UICONTROL Enregistrer et ajouter un autre élément]**.

1. (Facultatif) Pour exporter ou importer des fichiers CSV, accédez à la page [!UICONTROL Coûts du canal marketing], cliquez sur **[!UICONTROL Exporter un fichier]** ou **[!UICONTROL Importer un fichier]**, puis suivez les invites.

## Coûts du canal marketing - Définitions {#mktg-channel-costs}

Définition des champs relatifs aux coûts ou budgets de canal marketing.

| Champ | Définition |
|--- |--- |
| Nom | Le nom de l’élément de coût ou de budget. (Il s’agit de la valeur clé si vous utilisez SAINT.) |
| Canal | Le canal auquel vous souhaitez associer ce montant. Indiquez si le coût ou le budget s’applique à un canal Première touche ou Dernière touche. Considérez le montant de coût Première touche comme un nouvel engagement unique. Un montant de coût Dernière touche concerne les clics publicitaires. |
| Période | La période à utiliser pour ce montant. |
| Type | Le type de coût ou de budget, qu’il s’agisse d’un Taux ou d’un Coût unique. Le Taux indique un coût permanent ; par exemple un certain montant par clic. Le Coût unique permet de spécifier un montant « Réparti par ». Par exemple, si vous répartissez le coût par clics, l’affilié avec 60 % des clics totaux reçoit 60 % du coût total. La valeur Réparti par est la mesure utilisée lorsque vous ventilez des classifications numériques. |
| Exporter un fichier | Permet d’exporter les données du tableau au format CSV. |
| Importer un fichier | Permet d’importer un fichier CSV dans la page Coûts du canal marketing. |
