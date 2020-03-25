---
description: valeur nulle
keywords: DFA
title: Questions fréquentes
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Questions fréquentes {#frequently-asked-questions}

## Pourquoi l’assistant de Data Connectors n’accepte-t-il pas mes informations d’identification de connexion ? {#section-f019b3de18774df3954af7881aa564fa}

Si vous avez vérifié que les informations d’identification de connexion sont correctes, vérifiez ensuite que le nom d’utilisateur spécifié pour l’intégration est activé pour l’accès aux API. L’assistant Data Connectors valide les données d’identification de connexion à l’aide de l’API DFA, puis désactive et active les paramètres spécifiques à Adobe dans l’API DFA. Le paramètre Accès API doit être activé par un administrateur dans l’interface DFA. Ensuite, vérifiez que vous êtes autorisé à accéder à l’identifiant publicitaire ou à l’identifiant de configuration Floodlight sélectionné dans l’assistant.

## Pourquoi ne vois-je aucune donnée issue des mesures transférées de nuit (impressions DFA, clics DFA, etc.) ? {#section-465fd22ae6b447ffb6baf20b57daa433}

Si vous utilisez la version 1.5 de l’intégration, il se peut que votre intégration n’ait pas encore été affectée à un identifiant de site client. Un identifiant de site client (CSID) est requis pour que l’échange de nuit puisse avoir lieu et pour demander des données au serveur de publicités DFA. Il peut s’écouler jusqu’à trois jours à compter de la date d’intégration pour que les CSID soient échangés avec Google. Une fois le CSID reçu de Google, vous recevrez à l’adresse électronique de l’intégration le nouvel CSID, ainsi que le code JavaScript le plus récent.

Si, passé ce délai de trois jours, vous n’avez pas reçu le message de configuration et que les mesures ne sont pas distribuées, il est probable que le CSID a déjà été affecté à une autre intégration. Google maintient un mappage 1:1 entre le CSID et la suite de rapports, ce qui signifie que si une intégration dans une suite de rapports utilise le même identifiant publicitaire qu’une autre intégration dans une autre suite de rapports, un CSID sera affecté à la première suite de rapports seulement. Pour affecter le mappage d’un CSID à une autre suite de rapports ou à un autre identifiant publicitaire, vous devez en faire la demande à l’assistance de Google.

Par exemple, supposons qu’il existe une intégration dans la suite de rapports A avec l’identifiant publicitaire Z auquel est affecté un CSID. Si une autre intégration est configurée ultérieurement dans la suite de rapports B avec l’identifiant publicitaire Z, le CSID ne sera PAS réaffecté à cette nouvelle intégration. L’assistance Google doit en être informée. D’un autre côté, prenons l’exemple d’une intégration dans la suite de rapports A, avec l’identifiant publicitaire Z, puis une intégration ultérieure dans la suite de rapports A, le publicitaire Z est configuré. Seule la première intégration recevra les données de l’intégration ; toutefois, dans ce cas, il est possible de désactiver la première intégration pour que les données soient distribuées à la seconde intégration.

> [!NOTE] Les CSID ne sont pas utilisés dans la version 2.0 de l’intégration ; ainsi, le processus de négociation des CSID ne s’applique pas.

## J’utilise la version 2.0 de l’intégration et les mesures de coûts ne s’affichent pas pour mes publicités DFA. Pourquoi ? {#section-805748111bbe4bbf918d6dbbb2641fff}

Les mesures de coûts doivent être activées côté DFA Google et spécifiées dans l’interface DFA, et être activées également dans l’assistant Data Connectors. Commencez par vérifier que vous avez mappé un événement Analytics pour le coût des médias DFA et que vous avez spécifié un code de devise. Si vous avez mappé l’événement Coût des médias, achevez et enregistrez l’assistant ; l’indicateur DFA omnitureCostData sera activé dans l’API DFA. Google saura ainsi que les mesures doivent être envoyées dans le fichier de nuit. Vous pouvez vérifier dans l’interface DFA qu’omnitureCostData est bien activé en observant les propriétés sur le serveur Floodlight intégré. Enfin, après avoir vérifié ces deux emplacements, vérifiez que les publicités qui font partie du serveur Floodlight intégré spécifient les données et les structures de coûts. Si les données de coûts ne sont pas spécifiées dans l’interface DFA, elles ne s’affichent pas dans Analytics.

## Pourquoi certaines publicités ne présentent-elles aucune impression DFA ou affichage publicitaire, mais présentent des clics et des clics publicitaires ? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Certaines publicités enregistrent uniquement les données de clics, appelées outils de suivi des clics. Ces types de publicités ne renvoient pas les dernières données d’impression issues de l’interrogation du serveur Floodlight. Pour vérifier si une certaine publicité est un outil de suivi des clics ou une publicité d’un clic seulement, contactez votre agence DFA ou votre représentant technique Google.

## Pourquoi n’y a-t-il aucun clic publicitaire pour les publicités qui présentent des clics DFA ? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Il peut y avoir plusieurs explications.

Commencez par vérifier que l’URL de la page d’entrée de la publicité en question (a) est balisée avec le code Adobe pour la même suite de rapports que celle pour laquelle vous constatez une incohérence et (b) contient le paramètre de chaîne de requête *`clickThroughParam`*.

Ensuite, vérifiez que vous disposez d’une intégration fonctionnelle en suivant les étapes décrites dans [Confirmation d’une intégration DFA réussie](../dfa-data-connector-analytics/dfa-integration.md). Si un code de suivi DFA apparaît avec l’accès Adobe sur la page d’entrée, le clic publicitaire doit apparaître dans le rapport des campagnes DFA. Si vous ne le voyez pas passer, vérifiez que les suites de rapports correspondent entre la variable *`s.account`* de la page d’entrée et la suite de rapports affichée dans Reports &amp; Analytics. Si elles correspondent, vérifiez les codes de suivi dans le rapport des eVar d’affichage publicitaire du type DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

Ces codes indiquent que la règle VISTA DFA n’a pas réussi à digérer les données brutes de DFA. Ce problème peut être résolu en ouvrant un ticket d’assistance auprès de votre représentant de compte Adobe.

Si aucune des solutions ci-dessus n’explique le problème, voir [Rapprochement des écarts de mesures](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) pour explorer d’autres possibilités.
