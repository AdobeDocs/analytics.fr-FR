---
title: 'Commencer avec le marketing '
description: Découvrez le flux de travail des  marketing, la configuration automatique et comment appliquer les paramètres des suites de rapports de modèle à plusieurs suites de rapports.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Commencer avec le marketing 

Les  marketing sont généralement utilisées pour fournir des informations sur la manière dont les arrivent sur votre site. Vous pouvez personnaliser vos règles de traitement des marketing en fonction des que vous souhaitez suivre et de la manière dont vous souhaitez les suivre.

Les canaux marketing sont axés sur les mesures Première touche et Dernière touche qui sont des composants des mesures de conversion standard.

## Flux de  du marketing

![](assets/step1_icon.png) Définir chaque canal en fonction de vos besoins.

La définition des canaux que vous utilisez constitue l’une des tâches les plus importantes. La définition du  peut nécessiter la collaboration de plusieurs personnes de votre entreprise. Voici quelques questions à prendre en compte :

* Utilisez-vous une recherche payante ?
* Utilisez-vous des campagnes par courrier électronique ? Utilisez-vous plusieurs campagnes par courrier électronique dont vous souhaitez effectuer le suivi séparément ?
* Des affiliés redirigent-ils le trafic vers votre site ? Existe-t-il des affiliés dont vous souhaitez effectuer le suivi individuellement ?
* Existe-t-il des campagnes externes qui présentent un intérêt pour le suivi séparé ?
* Souhaitez-vous  tous les sites de réseaux sociaux, ou y en a-t-il un dont vous souhaitez effectuer le suivi individuellement ?
* Y a-t-il d&#39;autres  qui pourraient affecter la conversion dont vous souhaitez effectuer le suivi ?

Vous trouverez une liste des canaux recommandés dans la section  [Questions fréquentes et exemples](/help/components/c-marketing-channels/c-faq.md). Établissez une liste des canaux que vous souhaitez utiliser pour simplifier leur définition lors de leur création.

![](assets/step2_icon.png) Ajouter marketing  sur la [!UICONTROL Marketing Channel Manager] page.

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Voir [Canaux et règles](/help/components/c-marketing-channels/c-channels.md) pour consulter des informations importantes sur les concepts et les conditions préalables requises.

Voir [Ajout de canaux marketing](/help/components/c-marketing-channels/c-channels.md) pour la procédure.

>[!NOTE]
>
>Si les canaux marketing n’ont pas été configurés précédemment, la [configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md) s’affiche. Elle propose plusieurs canaux préconfigurés que vous pouvez personnaliser. Adobe recommande d’utiliser ces règles en tant que modèle. Toutefois, si vous disposez déjà de définitions de solides, vous pouvez ignorer la configuration automatique.

![](assets/step3_icon.png) Configurez ou affinez chaque règle  sur la [!UICONTROL Marketing Channel Processing Rules] page.

After you create channels on the [!UICONTROL Marketing Channel Manager] page, you configure the rules so that channels can retrieve and report data.

Voir [Règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md).

Si les canaux ont été créés lors de la configuration automatique, les règles de ceux-ci sont définies. Vous pouvez les modifier en fonction de vos besoins.

## Configuration automatique pour les  de marketing {#run-auto-setup}

Le rapport Canal marketing comporte une page de configuration unique pour vous aider à démarrer. Il fournit plusieurs  marketing que vous pouvez utiliser pour le suivi. Vous pouvez ignorer cette configuration si vous vous sentez à l’aise avec la création des canaux et des règles. Adobe vous recommande toutefois d’autoriser l’assistant à créer le  pour vous. La configuration automatique vous permet de voir comment les règles sont construites ou de les modifier pour vos propres besoins. Vous pouvez à tout moment désactiver ou supprimer le  prédéfini.

Comment exécuter la configuration automatique des canaux marketing.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sur la [!UICONTROL Report Suite Manager]page, sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Résultat de l’étape](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. (Voir [Gestionnaire de canaux marketing](/help/components/c-marketing-channels/c-channels.md).) Cette page ne s’affiche pas si votre suite de rapports contient un ou plusieurs  marketing. Vous ne pouvez plus accéder à cette page, sauf si vous sélectionnez une autre suite de rapports qui ne contient pas d’ marketing.

1. Vérifiez que les canaux à créer sont sélectionnés.

   Lorsque cette option est sélectionnée, **[!UICONTROL Email]**, **[!UICONTROL Display]** et **[!UICONTROL Affiliate]** sont des champs obligatoires.

1. Cliquez sur **[!UICONTROL Save]**.

## Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports

Comment utiliser une suite de rapports maître comme modèle pour tester votre configuration de marketing. Pour gagner du temps, vous pouvez appliquer ce modèle à une ou plusieurs suites de rapports de production dans une mise à jour en masse. Vous effectuez ce  pour les jeux de et de règles séparément.

>[!NOTE] Appliquez les canaux à partir d’un modèle avant d’appliquer des ensembles de règles. Les canaux doivent être identiques pour toutes les suites de rapports lors de cette procédure.

1. Assurez-vous que l’option Rapport Canal marketing est activée pour les suites de rapports sélectionnées. Cette étape est effectuée par votre gestionnaire de compte.
1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Sur la **[!UICONTROL Select Master Report Suites]** page, sélectionnez une suite de rapports de modèle.
1. Cliquez sur **[!UICONTROL Save All]**.
1. Appliquez les règles d’un modèle à plusieurs suites de rapports :
   1. Revenez à la [!UICONTROL Report Suite Manager] page.
   1. Sélectionnez la suite de rapports modèle, ainsi qu’une ou plusieurs suites de rapports cibles.
   1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Cliquez sur **[!UICONTROL Save]**. Si le bouton Enregistrer est désactivé au cours de cette étape, activez-le en développant l’une des règles.

