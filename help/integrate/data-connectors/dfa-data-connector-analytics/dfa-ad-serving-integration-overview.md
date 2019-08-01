---
description: 'Cette intégration peut capturer les données au sujet du visiteur orienté par une publicité de plusieurs façons. La première consiste à cliquer sur une publicité et à accéder à une page d''entrée balisée, appelée clic publicitaire '
keywords: DFA
seo-description: 'Cette intégration peut capturer les données au sujet du visiteur orienté par une publicité de plusieurs façons. La première consiste à cliquer sur une publicité et à accéder à une page d''entrée balisée, appelée clic publicitaire '
seo-title: Présentation de l’intégration AdServing
solution: Analytics
title: Présentation de l’intégration AdServing
topic: Connecteurs de données
uuid: e 286 f 61 e -4 b 09-48 b 5-b 1 e 9-3 c 07 b 6 face 24
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Présentation de l’intégration AdServing{#ad-serving-integration-overview}

Cette intégration peut capturer les données au sujet du visiteur orienté par une publicité de plusieurs façons. La première consiste à cliquer sur une publicité qui dirige vers une page d’entrée balisée, ce qu’on appelle un clic publicitaire.

![](assets/Diagram1.png)

Le visiteur parvient sur un site de l’éditeur, qui héberge la publicité. Cette publicité porte un identifiant unique, appelé un ID de publicité. Les publicités se composent d’un référencement et d’un attribut créatif, qui décrivent où se trouve la publicité sur le site de l’éditeur et quel contenu était présenté au visiteur. Quand le visiteur récupère cette publicité, le référencement ou le créatif sur les serveurs de contenu DFA, un suivi est effectué de l’impression jusqu’aux serveurs Floodlight DFA pour ce visiteur (1).

Si le visiteur clique sur la publicité (2), le serveur Floodlight est interrogé, ce qui compte comme un clic, puis l’instruction 302 redirige (3) le visiteur vers la page d’entrée. Quand le visiteur parvient à la page d’entrée, il s’agit d’un clic publicitaire. Cette page comprend le code de suivi Adobe, qui interroge les données du serveur Floodlight DFA.

Si le visiteur ne parvient pas sur la page d’entrée alors que le serveur Floodlight a effectué un suivi sur un clic, il ne s’agit pas d’un clic publicitaire. Certaines publicités et mises en œuvre n’obligent pas systématiquement le navigateur du visiteur à obéir à la redirection 302. Pour en savoir plus sur ce sujet, voir [Rapprochement des écarts de mesures](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f).

La prochaine mesure capturée par cette intégration survient quand le visiteur reçoit l’impression de publicité, ne clique pas, mais parvient tout de même dans un futur proche sur la page d’entrée par un autre moyen.

![](assets/Viewthrough.png)

Ce scénario est alors nommé un affichage publicitaire. Il diffère du scénario du clic publicitaire du fait que le visiteur ne clique pas sur la publicité, mais poursuit d’autres activités avant de parvenir à la page d’entrée (2). Dans le plus simple des cas, le visiteur saisit l’URL de la page d’entrée dans le navigateur. Il arrive aussi que le visiteur poursuive sa navigation mais parvienne ensuite à la page d’entrée en utilisant un moteur de recherche. Dans tous les cas, l’utilisateur parvient à la page d’entrée.
