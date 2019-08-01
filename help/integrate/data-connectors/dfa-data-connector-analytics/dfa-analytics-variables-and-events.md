---
description: L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.
keywords: DFA
seo-description: L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.
seo-title: Variables et événements Analytics
solution: Analytics
title: Variables et événements Analytics
topic: Connecteurs de données
uuid: 8996 cb 58-c 793-4600-99 ef-af 3064642 b 29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Variables et événements Analytics{#analytics-variables-and-events}

L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.

Outre la variable de campagne, vous pouvez utiliser les événements et eVars Analytics de votre choix. Après avoir identifié les événements et eVars à utiliser avec cette intégration DFA, activez-les dans la console d’administration Analytics. Les variables d’intégration doivent être activées avant l’intégration DFA. Le tableau suivant décrit les variables Analytics nécessaires pour l’intégration DFA.

| Variable | Nom convivial | Méthode de remplissage | Description |
|---|---|---|---|
| s.campaign ou eVar | Code de suivi de publicité | Automatiquement renseignée par le connecteur de données pour les campagnes DFA. | Effectue le suivi des conversions de clic publicitaire pour toutes les campagnes. |
| eVar* | Affichage publicitaire | Automatiquement renseignée par le biais des règles VISTA et DFA pour les campagnes DFA. | Suivi des données d’affichage publicitaire pour les identifiants DFA. Cette eVar doit avoir la même expiration que la variable *`s.campaign`* . Must be the same conversion variable as identified in the Variable Provider ID (See [Update Your Website’s Data Collection Code](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). Veillez à ce que les sous-relations de l’eVar soient entièrement activées. Le coût d’activation de cette fonction est inclus dans les frais d’intégration des Connecteurs de données. |
| eVar* | Erreurs de requête DFA | (Facultatif) Renseignée par le biais du code de collecte JavaScript. | Contient l’un des codes d’erreur renvoyés depuis DFA (voir le tableau à la section [Configuration de l’intégration](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858) pour obtenir une liste de ces codes d’erreur). |
| event* | Décompte des affichages publicitaires | Automatiquement renseignée par le connecteur de données pour les campagnes DFA. | Capture le nombre de fois où les utilisateurs ont affiché une publicité, n’ont pas cliqué dessus mais sont parvenus sur votre site. |
| event* | Impressions | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Effectue le suivi du nombre de fois où une publicité DFA spécifique a été diffusée. |
| event* | Clics | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Effectue le suivi du nombre de fois où les utilisateurs ont cliqué sur une bannière publicitaire DFA spécifique. Il existe plusieurs raisons pour lesquelles cette mesure peut générer des résultats différents de ceux de la mesure des clics publicitaires Analytics natifs. Voir [Rapprochement des écarts de mesures](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) pour en savoir plus. |
| event* | Dépassements de délai DFA | (Facultatif) Renseignée par le biais du code de collecte JavaScript. | Comptabilise le nombre de fois où DFA ne parvient pas à répondre avant l’expiration du délai de *`s.maxDelay`*. Ceci peut vous aider à déterminer tout problème de mise en œuvre DFA. |
| event* | Coût des médias DFA | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Contient les mesures de coût des médias qui ont été saisies dans l’interface DFA. Cette fonction doit être activée côté DFA pour que ces mesures s’affichent. |

*Sélectionnez une eVar ou un événement personnalisé inutilisé(e).
