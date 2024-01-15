---
title: Prévoir un pic de trafic
description: Faites équipe avec Adobe pour vous assurer que les événements à trafic élevé ne subissent pas de latence.
feature: Traffic Management
role: Admin
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 97%

---

# Prévoir un pic de trafic

Adobe fait le nécessaire pour créer des partenariats avec les clients afin de s’assurer qu’un événement à trafic élevé est réussi. La planification des pics de trafic est le point de départ de ce processus de partenariat. La section Prévoir les pics vous permet de signaler des pics de trafic temporaires à Adobe, de telle sorte que des ressources suffisantes puissent être allouées pour leur traitement. Vous pouvez estimer les appels au serveur précédents afin de vous faire une idée précise de la taille du pic de trafic que vous devez planifier.

Nous utilisons un système avancé dʼéquilibrage des données côté serveur et des employés dédiés pour nous assurer que tous les clients disposent des rapports les plus à jour possible. Lorsque votre organisation informe Adobe quʼelle connaît des pics de trafic, Adobe peut faire en sorte que cette augmentation soudaine du trafic soit une expérience positive. Si Adobe nʼest pas informé de lʼaugmentation du trafic, cela peut augmenter la latence pendant les périodes critiques.

{{$include /help/_includes/traffic-lead-time.md}}

## Prévoir un pic de trafic

Pour planifier un pic de trafic :

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion du trafic]** > **[!UICONTROL Prévoir les pics]**.
1. (Facultatif) Vous pouvez estimer les appels au serveur précédents afin de vous faire une idée précise de la taille du pic de trafic que vous devez planifier.

   Par exemple, vous pouvez obtenir une moyenne des appels quotidiens au serveur de l’année passée durant une période précise, ainsi que l’augmentation prévue du volume d’appels au serveur de cette année. Vous pouvez ainsi prévoir un pic de trafic d’après ce facteur de multiplication.

   1. Dans la zone **[!UICONTROL Appels au serveur précédents]**, sélectionnez des dates de début et de fin des suites de rapports sélectionnées.

      Les valeurs pour [!UICONTROL **Jour de pic**], [!UICONTROL **Appels au serveur par jour de pic**] et [!UICONTROL **Moyenne quotidienne d’appels au serveur**] sont générées.

   1. Saisissez une valeur pour le facteur de multiplication, puis sélectionnez **[!UICONTROL Cliquer pour multiplier et définir]**.

      La valeur de chaque colonne est multipliée pour chaque suite de rapports.
1. Dans la zone [!UICONTROL **Définir les paramètres du pic**], dans le champ **[!UICONTROL Date de début du pic]**, indiquez la date à laquelle vous pensez que le pic de trafic va commencer.
1. Dans le champ **[!UICONTROL Date de fin du pic]**, indiquez la date de fin prévue du pic de trafic.
1. Dans le champ **[!UICONTROL Appels au serveur par jour de pic]**, indiquez le pic total attendu de pages vues par jour pendant la période du pic de trafic.
1. Dans le champ **[!UICONTROL Appels au serveur par heure de pic]**, indiquez le pic total attendu de pages vues par heure pendant la période du pic de trafic.
1. Sélectionnez **[!UICONTROL Envoyer]**.

   Veillez à indiquer le nombre total de pages vues attendu et pas simplement le nombre de pages vues supplémentaires.

   >[!NOTE]
   >
   >Pour planifier un pic de trafic, indiquez un numéro de téléphone dans vos coordonnées de contact, de telle sorte qu’Adobe puisse vous contacter si la moindre question se pose.

## Importance des prévisions des pics de trafic

Lorsque les clients signalent à Adobe des pics de trafic pour chaque suite de rapports, Adobe met tout en œuvre pour que lʼimpact sur les rapports soit minimal.

* Les organisations qui ont prévu des pics de trafic sont prioritaires si les données commencent à devenir latentes. Ce concept revêt toute son importance durant la période des fêtes, car de nombreuses organisations prévoient des pics de trafic.
* Si Adobe constate que vous avez considérablement surestimé/sous-estimé le trafic prévu par rapport aux années précédentes, nous pouvons vous contacter pour vérifier lʼexactitude des données.
* Il est important de prévoir un pic de trafic chaque année, même si votre organisation connaît le même pic chaque année. De nombreuses organisations publient de nouvelles applications, combinent des suites de rapports et migrent/abandonnent des suites de rapports tout au long de lʼannée. Adobe ne peut déterminer avec certitude les suites de rapports qui connaissent un trafic supplémentaire, sauf si votre organisation prévoit un pic de trafic à chaque fois. Grâce aux données historiques, Adobe obtient une estimation, mais il est important que toutes les ressources supplémentaires soient placées sur la bonne suite de rapports.

## Mesures à prendre par votre organisation

Adobe veut sʼassurer que votre expérience en matière de création de rapports à jour est cohérente. Pour gérer au mieux les pics de trafic, Adobe recommande vivement de procéder comme suit :

* Planifiez le délai d’avance de tous les pics de trafic. **Il est particulièrement important que les pics de trafic prévus pour les mois de novembre et décembre soient signalés avant le 15 septembre**. Au-delà de cette date, prévoyez votre pic dès que possible. Un délai réduit est préférable à un délai nul, et Adobe travaille avec les ressources actuelles pour répondre au mieux à vos suites de rapports.
* Si Adobe vous contacte au sujet d’un pic de trafic prévu, veillez à indiquer le type de création de rapports qui vous importe le plus : en temps réel ou à traitement complet. Certaines organisations comptent plus que dʼautres sur les rapports en temps réel. Adobe peut établir des priorités si vous lui indiquez le type de création de rapports utilisé.
* Communiquer avec votre équipe de compte d’Adobe les rapports les plus importants et, lorsque vous les extrayez, peut les aider à vous défendre.
