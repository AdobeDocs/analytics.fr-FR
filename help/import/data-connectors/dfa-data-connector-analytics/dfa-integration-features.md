---
description: 'Une fois activée, l’intégration DFA des Data Connectors fournit les mesures suivantes pour vos rapports Adobe Analytics. '
keywords: DFA
title: Fonctions d’intégration
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Fonctions d’intégration{#integration-features}

Une fois activée, l’intégration DFA des Data Connectors fournit les mesures suivantes pour les rapports Adobe Analytics :

*  publicitaires des
* Clics DFA
* Impressions
* (Facultatif) Données de coût DFA
* (Facultatif) Erreurs  DFA, Délais d’expiration

>[!NOTE] Cette intégration ne propose aucune assistance pour les outils de suivi de clics (anciennement les commandes de clic). Les outils de suivi des clics permettent d&#39;enregistrer le nombre de clics sur des liens texte, des liens dans des messages électroniques ou sur d&#39;autres éléments codés en dur sur un site Web.

L’intégration DFA Data Connectors construit automatiquement les codes de suivi DFA à partir des données renvoyées par DFA. Ces codes de suivi sont construits de façon à identifier de manière unique une publicité ainsi que son référencement et son créatif associés. L’illustration ci-après décrit la structure du code de suivi, selon la version de l’intégration. La version 1.5 ressemble à ceci :

![](assets/DFA_id_struct1_5.png)

La version 2.0 ressemble à ceci :

![](assets/DFA_id_struct2.png)

Ces identifiants servent de clé partagée entre Genesis et DFA pour associer les classifications et mesures correctes.

| ID du site | Site tiers sur lequel était hébergée la publicité. La classification Nom du site fournit un nom descriptif de cet identifiant de site. |
|---|---|
| Identifiant de publicité | Identifiant du message commercial distribué à un utilisateur. La classification du nom de publicité contient le nom de la publicité comme défini par votre organisation dans le système DFA. Par exemple : `Hybrid Coup Textlink - Build`. |
| Identifiant de référencement | Représentation dans votre compte DFA d’un site Web, d’une partie d’un site Web ou d’un groupe de sites Web sur lesquels vous avez acheté de l’espace publicitaire. |
| ID d’élément créatif | Image, fichier SWF Flash ou autre ressource qui sera présentée au visiteur. La classification Nom créatif contient le nom que vous avez fourni à ce créatif dans l’interface DFA. |

Les deux autres classifications, Outil  de (DoubleClick for Advertisers) et  de bannière publicitaire, ont les mêmes valeurs pour toute campagne DFA et permettent de distinguer les données DFA importées.

## Déduplication SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

L’intégration DFA est désormais compatible avec Adobe SearchCenter. En activant la déduplication SearchCenter via l’assistant des Data Connectors, les visiteurs en provenance de moteurs de recherche n’entraîneront pas l’extraction des données du serveur Floodlight de DFA et *`s.campaign`* ne seront pas remplis par la DFA, ce qui permettra à SearchCenter de les renseigner. En outre, DFA et SearchCenter renseignent désormais les valeurs de déduplication dans les variables de chaque produit.

Le  ci-dessous décrit la logique activée lorsque la déduplication SearchCenter est activée :

Si **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** est sélectionné dans l’assistant :

* Dans le cas d’un clic publicitaire DFA, l’intégration renseignera la chaîne « DFA Clickthrough » (clic publicitaire DFA) avec l’eVar SCM configurée.
* Dans le cas d’un affichage publicitaire DFA, l’intégration renseignera la chaîne « DFA Viewthrough » (affichage publicitaire DFA) avec l’eVar SCM.

Si **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** est sélectionné dans l’assistant :

* Dans le cas d’un affichage publicitaire DFA, l’intégration renseignera la chaîne « DFA Viewthrough » (affichage publicitaire DFA) avec l’eVar SCM.

>[!NOTE] Si l’option SearchCenter > Déduplication DFA est activée et que le paramètre de chaîne de requête SearchCenter est défini, la visite n’est pas prise en compte pour le traitement DFA. Ceci signifie que le paramètre de chaîne de requête SearchCenter doit différer du paramètre de clic publicitaire DFA et qu’aucune publicité affichée ne doit définir le paramètre de chaîne de requête SearchCenter.

