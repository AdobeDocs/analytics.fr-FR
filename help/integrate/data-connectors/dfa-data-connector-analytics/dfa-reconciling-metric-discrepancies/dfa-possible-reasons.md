---
description: Liste d’un certain nombre de raisons pouvant expliquer les disparités des données entre les rapports Adobe Analytics et DFA.
keywords: DFA
seo-description: Liste d’un certain nombre de raisons pouvant expliquer les disparités des données entre les rapports Adobe Analytics et DFA.
seo-title: Motifs de disparités possibles
solution: Analytics
title: Motifs de disparités possibles
topic: Connecteurs de données
uuid: fd 414 cc 6-d 568-491 e -9 b 1 c -5 d 493 dcfbe 45
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Motifs de disparités possibles{#possible-reasons-for-discrepancies}

Liste d’un certain nombre de raisons pouvant expliquer les disparités des données entre les rapports Adobe Analytics et DFA.

## Les navigateurs Safari et quelques autres bloquent les cookies tiers {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

L’acceptation des cookies tiers est généralement la cause la plus courante des disparités entre les rapports Adobe Analytics et DFA. Les navigateurs Safari, entre autres, bloquent par défaut les cookies tiers. Ainsi, par défaut, Safari accepte les cookies propriétaires utilisés par la plupart des mises en œuvre Analytics, mais rejette les cookies tiers de DFA.

Un échantillon de données provenant de nos clients Analytics 15 bêta montrait que moins de 0,5 % des utilisateurs rejettent généralement les cookies propriétaires, tandis que 5-12 % rejetait les cookies tiers (la plupart de ces rejets sont probablement dus aux paramètres par défaut du navigateur).

Ceci peut générer un écart important entre les données collectées par Analytics et celles collectées par DFA.

## Pourquoi les impressions consignées dans DFA sont-elles parfois supérieures aux impressions consignées dans Adobe Analytics ? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA envoie des données vers les serveurs de collecte de données Adobe lors d’un envoi de nuit, de sorte qu’il peut y avoir jusqu’à deux jours d’écart entre les données d’impression Analytics et celles des rapports DFA.
* Adobe utilise les classifications SAINT afin de classifier les codes de suivi DFA importés à divers niveaux d’agrégation (nom de campagne, de référencement, de publicité, etc.). Si la disparité apparaît lors de l’exécution d’un rapport de classification, exécutez un test simple afin de vérifier si les classifications reflètent déjà les mesures importées :

   * Dans le rapport de classifications, localisez une ligne nommée Néant ou Aucun.
   * Ventilez cette ligne selon la même variable, en utilisant le rapport ID DFA brut (identifiant de campagne, par exemple).
   * Dans ce rapport, notez les codes de suivi DFA non classés du type DFA:XXXXX:XXXXX ...
   * Si ce type de code est fréquent, vérifiez le processus de classification SAINT de nuit.

## Pourquoi les clics DFA sont-ils parfois supérieurs aux clics publicitaires Adobe Analytics ? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA comptabilise un clic avant que le visiteur ne parvienne au site web du client. Analytics comptabilise les clics publicitaires après le chargement de la page d’entrée et l’exécution de la balise Adobe JavaScript. En général, les disparités sont dues au fait que le visiteur n’est pas encore parvenu sur la page d’entrée alors que DFA a déjà suivi un clic ou au fait que le délai *`s.maxDelay`* est dépassé.
* Assurez-vous que tous les référencements et créatifs de la configuration Floodlight comprennent le paramètre clickThroughParam dans l’URL de la page d’entrée (par exemple « ?CID=1 »). Si ce paramètre n’est pas défini, le code JavaScript Adobe Analytics omet les clics publicitaires qui surviennent après le premier accès de la visite.
* Assurez-vous que tous les référencements et créatifs correspondent à une page d’entrée balisée avec JavaScript et qu’ils contiennent le module DFA Integrate, et que l’identifiant de configuration Floodlight sur cette page d’entrée correspond à l’identifiant de configuration Floodlight des publicités diffusées. Souvent, les disparités sont dues au fait que la page d’entrée pour les publicités est paramétrée sur le site tiers ou les publicités diffusées.
* Si vous utilisez des publicités multimédias enrichies ou Flash (swf), assurez-vous que chaque fois que l’outil de suivi des clics est atteint, le navigateur du visiteur est également redirigé vers la page d’entrée avec le paramètre `clickThroughParam` inclus dans la chaîne de requête. En cas d’échec de redirection du navigateur, un clic publicitaire n’est pas comptabilisé.
* Les dépassements de délai représentent les instances où les données DFA peuvent avoir été disponibles mais où le code JavaScript n’a pas reçu de réponse à temps. Si un visiteur parvient sur la page d’entrée, Adobe JavaScript demande ses informations auprès du service fls.doubleclick.net de DFA. Le paramètre *`s.maxDelay`* détermine le délai d’attente par JavaScript pour obtenir les données de Floodlight Service (FLS). If *`s.maxDelay`* is too high, visitors can leave the site before Adobe collects the hit data; meaning that no click data is recorded. If *`s.maxDelay`* is set too low, the visitor's Internet connection cannot retrieve the FLS data in time; meaning that the hit is sent to Adobe without DFA click information. See [Tuning s.maxDelay](../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d) for a further discussion on this subject.

* Le trafic des robots peut gonfler le nombre de clics DFA. Les robots sont parfois dotés d’une fonctionnalité de clic sur une publicité, sans avoir à exécuter une balise Analytics ni à déclencher la balise de script synchrone pour charger les données de demande des serveurs Floodlight. Si ces robots ne sont pas déduits du total des clics, ils peuvent être source de disparité des données.
* Les visiteurs qui quittent la page avant l’expiration de *`s.maxDelay`* et le renvoi des données DFA seront omis ; aucune donnée DFA ou de visiteur ne sera collectée à leur sujet.
* Analytics tente d’identifier et de supprimer les clics publicitaires en double afin qu’ils ne soient comptabilisés qu’une seule fois par campagne par visite. DFA comptabilise comme des clics ACM supplémentaires les visiteurs qui cliquent sur « Retour » et franchissent plusieurs fois la redirection de publicité, tandis qu’Analytics ne les comptabilise pas comme des clics publicitaires multiples.
* Les balises DFA Floodlight n’impliquent pas l’activation de JavaScript, contrairement à Analytics. C’est pourquoi il arrive que DFA comptabilise un accès alors qu’Analytics ne le fait pas. Afin d’identifier la présence potentielle d’un problème, utilisez le rapport Analytics JavaScript dans le menu Profil du visiteur.

## Pourquoi les activités post-impression de DFA sont-elles parfois supérieures aux affichages publicitaires Adobe Analytics ? {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics tente d’identifier et de supprimer les clics publicitaires en double afin qu’ils ne soient comptabilisés qu’une seule fois par campagne par visite. DFA comptabilise comme des clics ACM supplémentaires les visiteurs qui cliquent sur « Retour » et franchissent plusieurs fois la redirection de publicité, tandis qu’Analytics ne les comptabilise pas comme des clics publicitaires multiples.
* Les balises DFA Floodlight n’impliquent pas la désactivation de JavaScript, contrairement à Analytics. C’est pourquoi il arrive que DFA comptabilise un accès alors qu’Analytics ne le fait pas.
* DFA comptabilise les activités post-impression lors de l’utilisation des balises Floodlight, qui peuvent être placées sur le site web client. Analytics comptabilise les affichages publicitaires après l’exécution de la balise JavaScript (demande d’image). Le référencement du code sur la page web peut déterminer si le chargement abandonné d’une page est comptabilisé comme une activité post-impression ou comme un affichage publicitaire.

## Que faire si les disparités dépassent largement la marge acceptable et qu’aucun des motifs ci-dessus ne s’applique ? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Consultez votre conseiller en intégration ou le service à la clientèle d’Adobe afin de documenter les disparités et de les signaler à l’équipe technique des Connecteurs de données. Pour que le traitement de votre demande soit plus rapide, préparez 2 ou 3 jours de données en comparant les mesures en question (au niveau du code de campagne). Dans votre demande, identifiez toutes les actions que vous avez déjà entreprises pour résoudre les disparités.
