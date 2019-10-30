---
description: L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.
keywords: DFA
seo-description: L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.
seo-title: Variables et événements Analytics
solution: Analytics
title: Variables et événements Analytics
topic: Connecteurs de données
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variables et événements Analytics{#analytics-variables-and-events}

L’intégration des Connecteurs de données pour DFA effectue le suivi des résultats de campagne DFA à l’aide des variables Analytics.

Outre la variable de campagne, vous pouvez utiliser les événements et eVars Analytics de votre choix. Après avoir identifié les événements et eVars à utiliser avec cette intégration DFA, activez-les dans la console d’administration Analytics. Les variables d’intégration doivent être activées avant l’intégration DFA. Le tableau suivant décrit les variables Analytics nécessaires pour l’intégration DFA.

| Variable | Nom convivial | Méthode de remplissage | Description |
|---|---|---|---|
| s.campaign ou eVar | Code de suivi de publicité | Automatiquement renseignée par le connecteur de données pour les campagnes DFA. | Effectue le suivi des conversions de clic publicitaire pour toutes les campagnes. |
| eVar* | Affichage publicitaire | Automatiquement renseignée par le biais des règles VISTA et DFA pour les campagnes DFA. | Suivi des données d’affichage publicitaire pour les identifiants DFA. Cette eVar doit avoir la même expiration que la variable Variable *`s.campaign`*. Doit être la même variable de conversion que celle identifiée dans l’ID du fournisseur de variables. Veillez à ce que les sous-relations de l’eVar soient entièrement activées. Le coût d’activation de cette fonction est inclus dans les frais d’intégration des Connecteurs de données. |
| eVar* | Erreurs de requête DFA | (Facultatif) Renseignée par le biais du code de collecte JavaScript. | Contient l’un des codes d’erreur renvoyés par DFA. |
| event* | Décompte des affichages publicitaires | Automatiquement renseignée par le connecteur de données pour les campagnes DFA. | Capture le nombre de fois où les utilisateurs ont affiché une publicité, n’ont pas cliqué dessus mais sont parvenus sur votre site. |
| event* | Impressions | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Effectue le suivi du nombre de fois où une publicité DFA spécifique a été diffusée. |
| event* | Clics | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Effectue le suivi du nombre de fois où les utilisateurs ont cliqué sur une bannière publicitaire DFA spécifique. Il existe plusieurs raisons pour lesquelles cette mesure peut générer des résultats différents de ceux de la mesure des clics publicitaires Analytics natifs. Voir [Rapprochement des écarts de mesures](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) pour en savoir plus. |
| event* | Dépassements de délai DFA | (Facultatif) Renseignée par le biais du code de collecte JavaScript. | Comptabilise le nombre de fois où DFA ne parvient pas à répondre avant l’expiration du délai de *`s.maxDelay`*. Ceci peut vous aider à déterminer tout problème de mise en œuvre DFA. |
| event* | Coût des médias DFA | Valeur automatiquement renseignée par le biais d’un flux de données depuis DFA. | Contient les mesures de coût des médias qui ont été saisies dans l’interface DFA. Cette fonction doit être activée côté DFA pour que ces mesures s’affichent. |

*Sélectionnez une eVar ou un événement personnalisé inutilisé(e).
