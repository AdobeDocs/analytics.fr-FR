---
description: 'Adobe utilise les termes suivants pour parler des mesures liées à l''intégration DFA '
keywords: DFA
seo-description: 'Adobe utilise les termes suivants pour parler des mesures liées à l''intégration DFA '
seo-title: Définitions des mesures
solution: Analytics
title: Définitions des mesures
topic: Connecteurs de données
uuid: 062 f 6863-3 daa -4 e 8 a-b 6 ea -84279 d 49 c 388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Définition des mesures{#metric-definitions}

Adobe utilise certains termes spécifiques pour désigner les mesures liées à l’intégration DFA.

**Impressions** : les impressions se rapportent au nombre de fois où une publicité a été affichée. Les impressions sont consignées publicité par publicité, mais peuvent également être agrégées dans des groupes de publicités ou d’autres groupements de plusieurs publicités. La mesure d’impressions dans Analytics est importée à partir de DFA par l’intermédiaire d’une importation de nuit des sources de données.

**Clics** : les clics se rapportent au nombre de fois où on a cliqué sur une publicité, comme signalé par DFA. Les clics sont enregistrés sur la page de redirection DFA avant que le visiteur ne parvienne sur le site web du client. Comme les impressions, la mesure de clics dans Analytics est importée à partir de DFA par l’intermédiaire d’une importation de nuit des sources de données.

**Clics publicitaires** : les clics publicitaires renvoient au nombre de fois où l’utilisateur est parvenu sur la page d’entrée, après avoir cliqué sur une publicité. Cette mesure peut différer légèrement des clics.

**Affichages publicitaires** : les affichages publicitaires désignent le nombre de fois où un visiteur est parvenu sur le site web du client après avoir affiché une publicité, mais SANS avoir cliqué dessus. Le visiteur doit parvenir sur le site dans le créneau de l’affichage publicitaire (30 jours par défaut). L’impression doit avoir eu lieu plus récemment que le dernier clic. Les affichages publicitaires sont enregistrés une fois par campagne, par visite et sont comptabilisés quand l’intégration renseigne l’eVar d’affichage publicitaire avec l’identifiant de campagne DFA et que l’événement d’affichage publicitaire est défini.
