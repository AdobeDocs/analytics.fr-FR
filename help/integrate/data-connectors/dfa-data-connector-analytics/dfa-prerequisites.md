---
description: valeur nulle
keywords: DFA
seo-description: valeur nulle
seo-title: Conditions préalables
solution: Analytics
title: Conditions préalables
topic: Connecteurs de données
uuid: b 5 f 5 e 30 c-e 269-41 a 4-9236-5 ddc 404 bfd 94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Conditions préalables{#prerequisites}

Avant de commencer l’intégration des Connecteurs de données Adobe pour DFA, procédez comme suit :

* Décidez de procéder à l’intégration de la version 1.5 ou d’attendre la version 2.0. Cette décision dépend des fonctions utilisées dans votre compte DFA et du délai imparti pour réaliser l’intégration. Voir la section [Version 2.0](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664) pour en savoir plus.
* Décidez de la façon dont DFA Advertisers va mapper les suites de rapports Adobe Analytics. Par exemple, en présence de plusieurs instances de DFA Advertisers et de plusieurs suites de rapports, vous devez choisir les paires Advertisers/suites de rapports.
* Mettez en œuvre le code de collecte de données Adobe sur toutes les pages à suivre, à l’aide du code de collecte version H.22 ou ultérieure.
* Vous devez connaître l’identifiant publicitaire d’un compte DFA qui fait partie de la configuration Floodlight à intégrer. L’intégration importe automatiquement toutes les instances Advertisers incluses dans la configuration de Floodlight.
* Vous devez connaître le nom d’utilisateur et le mot de passe de votre compte DFA.
* Associez chaque instance DFA Advertisers à une seule suite de rapports Adobe Analytics. Le balisage vers plusieurs suites de rapports n’est pas pris en charge dans l’intégration Genesis par défaut pour DFA.
* Ajoutez un paramètre de chaîne de requête de clic publicitaire à la page d’entrée pour chaque référencement DFA qui fait partie de l’intégration. Ce paramètre de chaîne de requête est nécessaire pour comptabiliser correctement les clics publicitaires.
* Configurez vos référencements DFA de sorte qu’ils ne redirigent pas les visiteurs par plusieurs domaines. Par exemple, un référencement ne doit pas diriger les sondés vers un microsite hébergé sous www.xyz.com si le microsite les redirige ensuite vers un autre site, www.fgh.com. Si la réponse de campagne s’étend sur plusieurs domaines, les données sur les clics et affichages publicitaires risquent d’être gonflées et trompeuses.
* Identifiez une variable personnalisée dans les rapports et analyses afin de conserver les informations sur votre campagne.
* Identifiez une eVar de rapports et analyses afin de stocker les données sur les affichages publicitaires DFA. Utilisez cette eVar seulement pour cette intégration DFA.
* Identifiez les événements Rapports et analyses où stocker les données sur les impressions et les clics. Vous pouvez renommer ces événements de manière appropriée.
* (Facultatif) Identifiez les événements Rapports et analyses qui stockeront les données de coûts DFA. Vous pouvez renommer ces événements de manière appropriée.
* (Facultatif) Identifiez une variable personnalisée Rapports et analyses et l’événement de succès qui stockeront les erreurs et dépassements de délai DFA. Ces variables permettent de diagnostiquer les problèmes susceptibles de se produire avec l’intégration.
* (Facultatif) Créez un compte de messagerie spécial où recevoir des informations et des notifications liées à l’intégration des Connecteurs de données pour DFA.

