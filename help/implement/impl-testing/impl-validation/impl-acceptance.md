---
description: Etapes du processus d’implémentation.
keywords: Mise en œuvre d’Analytics
seo-description: Etapes du processus d’implémentation.
seo-title: Acceptation de l’implémentation
solution: Analytics
title: Acceptation de l’implémentation
topic: Développeur et mise en œuvre
uuid: 6f7ec56e-9e4f-4dc8-b534-92b1580b5b47
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Acceptation de l’implémentation

Etapes du processus d’implémentation.

Les étapes suivantes décrivent le processus d’implémentation.

1. Le consultant Adobe rassemble les exigences en termes de génération de rapports et s’en sert pour créer un plan de collecte de données.

   Ce plan comprend des définitions de variable, une corrélation de données, des règles VISTA requises et du code JavaScript personnalisé, ainsi que tous les paramètres relatifs à chaque suite de rapports. Il appartient au client de compléter le questionnaire d’implémentation.
1. Les ressources techniques côté client implémentent le code, le code JavaScript spécifique au site et les variables côté serveur.
1. Le consultant Adobe se charge de résoudre les problèmes techniques au cours de l’implémentation et apporte son aide dans le cadre de la conception de solutions en fonction des besoins.
1. Les ressources techniques côté client testent l’implémentation.

   Les testeurs se connectent à [!DNL Analytics] et vérifient l’intégralité des variables ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, variables Econversion, variables de trafic personnalisé *`products`* et toutes les autres).
1. Le client informe Adobe de la fin de l’implémentation.

   Le client fournit un échantillon de validation (échantillon de données) au consultant Adobe afin de valider l’exactitude des données. (Les suites de rapports générées par VISTA sont validées en comparant les mesures appropriées. Un accord portant sur les mesures à valider doit être établi, au préalable, entre le client et Adobe pour les suites de rapports de ce type et ce, au moment de la création des règles VISTA.)
1. Le client envoie par télécopie (ou signe en ligne) le Formulaire d’accord et d’acceptation d’implémentation pour le ou les sites appropriés.
1. Une fois l’acceptation reçue, le consultant Adobe active la certification « Bonnes pratiques Adobe - Vérification de l’implémentation » dans l’interface.
1. Le client peut éventuellement conclure avec Adobe un contrat portant sur la fourniture de services de surveillance pour des pages clés du site implémenté (il s’agit généralement de « modèles principaux », de la page d’accueil et de pages d’entrée critiques).

   Ce logiciel de surveillance, qui est décrit dans un document distinct, effectue le suivi des pages en les chargeant et en les exécutant, puis en comparant la demande d’image à un plan de base stocké dans une base de données. Si la moindre différence est détectée, le logiciel en informe la ressource Adobe (AM/IE) spécifiée et le personnel du client par courrier électronique.

Les éléments suivants contribuent à une implémentation réussie :

* Le document des bonnes pratiques, semblable à celui-ci, s’adresse au client. Il explique les processus de manière détaillée.
* Le document de validation dont se sert l’utilisateur pour tester l’implémentation.
* Un formulaire d’accord et d’acceptation d’implémentation que doit signer le client.
* Une application de contrôle qui procède à la validation des balises en continu.
* Une relation avec Accenture afin de faciliter les tests d’implémentation.
* Utilitaires et/ou outils de comparaison des pages vues et/ou commandes. Ces comparaisons peuvent se révéler particulièrement complexes.
* Méthode ou procédé permettant d’obtenir rapidement le journal de débogage pour un jour donné, en fonction de l’ID de suite de rapports.

