---
title: Intégration DFA - Informations sur la fin de vie
description: Pourquoi le connecteur de données DFA est-il en fin de vie en Adobe et quelles alternatives existe-t-il ?
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Intégration DFA - Informations sur la fin de vie

L&#39;Adobe a récemment annoncé [ses plans pour le connecteur de données de fin de vie](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), un ensemble d&#39;outils hérité pour l&#39;intégration de données tierces (par exemple, ESP, VOC, etc.) avec Adobe Analytics.

## Pourquoi les connecteurs de données entrent-ils en fin de vie ?

La plate-forme d’intégration des partenaires prise en charge est [Adobe Exchange](https://exchange.adobe.com/experiencecloud), conçue pour faciliter l’intégration des applications d’Adobe Digital Experience, l’intégration CXM tierce et pour prendre en charge les diverses exigences de données des clients et des partenaires bien à l’avenir. De nombreux partenaires qui ont développé leurs intégrations à l’aide de Connecteurs de données ont déjà migré ces intégrations vers Adobe Exchange, d’autres partenaires ayant prévu de le faire.

## Pourquoi l’intégration DFA entre en fin de vie ?

Dans [janvier 2020, Google a annoncé](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) qu’il supprimerait progressivement les cookies tiers dans Chrome d’ici 2022. Cela respecte les normes du secteur que Apple et Mozilla ont mises en place pour leurs navigateurs Safari et Firefox, respectivement. L’intégration DFA repose en grande partie sur les cookies tiers et deviendra donc inefficace et obsolète avec la suppression des cookies tiers sur les trois principaux navigateurs Internet. Google [a renforcé cette position en mars 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) en annonçant qu&#39;ils ne publieront pas de solution alternative.

Malheureusement, Google — qui est propriétaire de l’intégration DFA — a peu de chances de la reproduire sur la plate-forme Adobe Exchange. Par conséquent, nous avançons dans l’hypothèse que, une fois que les connecteurs de données seront déconnectés, l’intégration existante cessera de fonctionner et ne sera plus remplacée par une version productive.

La capacité de &quot;vue publicitaire&quot; de l’intégration DFA constitue un facteur important et supplémentaire. Il permet à Adobe Analytics de suivre les cas où un utilisateur a vu une annonce publicitaire, n’a pas cliqué, mais a ensuite visité le site Web. Les &quot;Vues publicitaires&quot; sont basées sur des cookies tiers, qui continueront d&#39;être supprimés progressivement au cours de l&#39;année 2021. Il s&#39;agit d&#39;une question de marché, et pas seulement d&#39;une question d&#39;Adobe. Pour l&#39;instant, il n&#39;existe aucune alternative à la réplication de ces données.

## Quelles alternatives existent pour vous ?

Pour les clients qui souhaitent intégrer des données d’affichage publicitaire (sans vue publicitaire) dans Adobe Analytics, nous disposons actuellement des options suivantes :

* Les clients Adobe Advertising Cloud DSP peuvent tirer parti [d’une intégration productive avec Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) pour définir les données d’annonce d’affichage de Google vers Adobe Analytics. Cette intégration est notre meilleure alternative et serait notre recommandation pour les clients. L’DSP Ad Cloud permet aux clients de fournir des expériences connectées sur tous les canaux publicitaires, y compris la recherche payante, l’affichage, la vidéo et d’autres. En savoir plus [ ici](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). Cependant, la DSP Ad Cloud sera également touchée par la perte de cookies tiers.
* Adobe Experience Platform et [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), qui offrent des fonctionnalités d’affichage et d’intégration avec d’autres sources de données. Les clients peuvent télécharger leurs données d’affichage à partir de leur fournisseur de recherche payante et les transférer vers un Experience Platform. Ensuite, ils amènent les données directement dans CJA pour les analyser à côté de leurs autres ensembles de données.
* Adobe Consulting (Engineering Architects) peut créer une solution personnalisée pour intégrer des mesures d&#39;affichage publicitaire dans Adobe Analytics. Cette solution est encore en développement et tous les clients intéressés à rejoindre la version bêta sont les bienvenus. Des détails supplémentaires sur les fonctionnalités, la disponibilité et les coûts seront fournis au fur et à mesure de leur disponibilité.
* Vous pouvez gérer votre propre intégration d’annonces d’affichage à l’aide de la fonctionnalité Sources de données ainsi que des classifications dans Adobe Analytics. Importez vos recherches payantes et affichez manuellement les données à l’aide des sources de données et des classifications [comme décrit ici](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Remarque : ce document fait référence à la recherche payante, mais le cas d&#39;utilisation et le concept sont identiques et peuvent être appliqués à l&#39;affichage).

Pour toute question ou assistance supplémentaire, contactez le service à la clientèle [Adobe ](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html).