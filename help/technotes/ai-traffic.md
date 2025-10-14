---
description: Comprendre comment générer des rapports sur le trafic provenant des chatbots d’IA
title: Analyse du trafic provenant des chatbots de l’IA
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Analyse du trafic à partir des outils d’IA conversationnelle

Adobe Analytics fournit des outils permettant d’analyser le trafic d’IA sur votre site web.

Lors de l’analyse du trafic d’IA, vous devez d’abord comprendre les types de trafic d’IA qui peuvent se produire et quels types génèrent des accès. Vous pouvez ensuite analyser le trafic dans Analysis Workspace.

## Comprendre le trafic de l’IA

### Comprendre les types de trafic d’IA

Le trafic de l’IA sur votre site web peut se produire dans l’une des circonstances suivantes :

* **Pendant la préformation** : ce problème se produit rarement lorsque le contenu de votre site web est gratté et ingéré dans les données de formation de l’IA.

* **Lorsque vous répondez à des invites à la demande** : se produit au moment où l&#39;utilisateur invite l&#39;IA à poser une question et où le chatbot de l&#39;IA répond. Le chatbot d’IA effectue une recherche web et le contenu de votre site web est inclus dans la réponse. (Ce type d’interactions est parfois appelé Récupération-Génération Augmentée (RAG).)

  Certaines réponses du bot conversationnel de l’IA incluent des liens vers le matériel source de votre site et d’autres non.

* **Lors de l’exécution de workflows d’agent** : se produit chaque fois qu’un agent d’IA visite votre site web en cliquant sur une série de pages web dans un navigateur afin de répondre à une demande de l’utilisateur. Dans ce cas, l’IA agit en tant qu’agent pour l’utilisateur qui a effectué la requête.

### Savoir quand les accès sont générés pour le trafic de l’IA

Un accès est généré sur une page web lorsque JavaScript est exécuté sur la page. Selon le type de trafic d’IA qui se produit sur votre site, JavaScript peut être exécuté ou non.

| Type de trafic IA | Génère des accès | Considérations |
|---------|----------|---------|
| **Formation préalable** | Oui | Les accès sont générés lors du pré-entraînement lorsque le contenu de votre site web est ingéré dans l’IA. Cependant, le pré-apprentissage se produit rarement et le contenu inclus dans le pré-apprentissage d’une IA peut être réutilisé à maintes reprises dans les réponses futures sans générer d’autres accès sur votre site web. <p>En d’autres termes, un seul accès qui se produit pendant le pré-entraînement d’une IA peut être réutilisé plusieurs fois pour plusieurs réponses à la demande sans générer d’accès supplémentaires sur votre site web.</p><p>Pour plus d’informations sur l’analyse de ce type de trafic d’IA dans Analysis Workspace, voir [Analyser le trafic d’IA à l’aide de la détection de robots](#analyze-ai-traffic-using-bot-detection).</p> |
| **Invites à la demande** | Non | La réponse de l’IA ne génère aucun accès, car elle utilise une combinaison des éléments suivants :<ul><li>Données préentraînées <br/>les informations sont déjà incluses dans les connaissances préentraînées de l’IA, de sorte que l’IA n’exécute pas JavaScript sur les pages.</li><li>Recherche web à la demande <br/>récupère uniquement l’HTML brute de la page web pendant la recherche web ; l’IA n’exécute donc pas JavaScript sur les pages.</li></ul> |
| **Liens matériels Source dans les réponses de l’IA** | Oui | Les accès sont générés lorsqu’un utilisateur clique sur le lien vers le matériel source inclus dans la réponse de l’IA. Un accès n’est pas généré si un lien est inclus dans la réponse et que l’utilisateur ou l’utilisatrice ne clique pas sur le lien. <p>Certaines réponses du bot conversationnel de l’IA incluent des liens vers le matériel source, d’autres non. </p><p>Pour plus d’informations sur l’analyse de ce type de trafic d’IA dans Analysis Workspace, voir [Analyser le trafic d’IA par type de référent](#analyze-ai-traffic-by-referrer-type).</p> |
| **Workflows dynamiques** | Oui | Les accès sont générés sur chaque page lorsque l’agent d’IA clique sur le workflow au nom de l’utilisateur. <p>Pour plus d’informations sur l’analyse de ce type de trafic d’IA dans Analysis Workspace, voir [Analyser le trafic d’IA par type de référent](#analyze-ai-traffic-by-referrer-type).</p> |

## Analyse du trafic de l’IA dans Analysis Workspace

### Analyse du trafic de l’IA par type de référent

Vous pouvez utiliser la dimension de type Référent dans Analysis Workspace pour analyser les types de trafic IA suivants :

* Liens matériels Source dans les réponses de l’IA

* Workflows de l’agence

La dimension Type de référent comprend l’élément de dimension [&#x200B; Outils d’IA dédiée à la conversation &#x200B;](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Cet élément de dimension comprend une liste prédéfinie de chatbots d’IA.

Pour plus d’informations, voir [&#x200B; Type de référent &#x200B;](/help/components/dimensions/referrer-type.md).

### Analyse du trafic d’IA à l’aide de la détection des robots

Vous pouvez utiliser la détection de robots dans Analysis Workspace pour analyser le trafic d’IA provenant de la préformation.

