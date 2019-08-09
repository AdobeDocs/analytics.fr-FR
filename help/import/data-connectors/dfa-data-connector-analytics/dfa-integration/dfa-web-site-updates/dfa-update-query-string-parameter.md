---
description: valeur nulle
keywords: DFA
seo-description: valeur nulle
seo-title: Mise à jour du paramètre de chaîne de requête DFA
solution: Analytics
title: Mise à jour du paramètre de chaîne de requête DFA
topic: Connecteurs de données
uuid: adf 585 ac -84 ff -44 c 1-a 48 d-b 072726 c 8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Mise à jour du paramètre de chaîne de requête DFA{#update-your-dfa-query-string-parameter}

Si vous effectuiez déjà le suivi des campagnes publicitaires avec Adobe Analytics avant l’intégration de DFA, il est possible que toutes les campagnes (publipostage, recherche ou bannière) utilisent le même paramètre de chaîne de requête pour reconnaître l’identifiant de campagne référent sur la page d’entrée.

Afin de comprendre quand demander des données de clics publicitaires et d’affichages publicitaires auprès des données DFA pour vos campagnes publicitaires DFA, les connecteurs de données doivent détecter quand un visiteur a cliqué sur une bannière publicitaire d’une campagne DFA. Pour ce faire, vous devez ajouter un paramètre de chaîne de requête différencié à l’URL de page d’entrée de la campagne publicitaire DFA afin que les connecteurs de données puissent distinguer les pages de la campagne publicitaire DFA des autres pages de campagne publicitaire qui peuvent apparaître sur votre site Web. Le `dfa_overrideParam` module externe JavaScript (voir [Mise à jour du code de collecte de données de votre site Web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) est utilisé pour DFA.

>[!CAUTION]
>
>Bien que la variable Campaign puisse être utilisée pour d'autres campagnes, n'utilisez pas celle-ci pour les campagnes DFA. Si vous définissez la variable Campaign sur une page d’entrée de campagne DFA, Adobe ne peut pas lier les impressions et clics aux clics publicitaires de la campagne DFA. Une fois par visite, les serveurs de collecte Adobe vérifient s’il existe un clic ou affichage publicitaire antérieur sur les serveurs DFA. C’est pourquoi vous devez inclure le code du module externe DFA (voir [Mise à jour du code de collecte de données de votre site web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) seulement sur les pages d’entrées courantes afin d’éviter des redirections superflues susceptibles de ralentir le temps de chargement des pages, en particulier quand les connexions Internet sont lentes.

