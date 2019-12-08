---
description: Séquence de pages vues lors d’une session unique. Cette mesure est généralement utilisée dans les rapports qui affichent le nombre de sessions utilisateurs au cours de la période sélectionnée.
keywords: visit
title: Visite
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visite

Séquence de pages vues lors d’une session unique. Cette mesure est généralement utilisée dans les rapports qui affichent le nombre de sessions utilisateurs au cours de la période sélectionnée.

> [!NOTE] Pour en savoir plus sur le calcul des visites et des lancements d’application mobile, voir [Comparaison des visites et des lancements d’application mobile](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) dans la base de connaissances.

Cette mesure est toujours associée à une période afin que vous sachiez si vous comptabilisez ou non une nouvelle visite si le même visiteur revient sur votre site. Une session débute lors de la première visite de l’utilisateur sur votre site et se termine lorsque l’un des scénarios suivants se présente :

* **30 minutes d’inactivité** : pratiquement toutes les sessions se terminent de cette manière. Si plus de 30 minutes se sont écoulées entre les demandes d’image, une nouvelle visite commence.
* **12 heures d’activité en continu** : si un utilisateur déclenche des demandes d’image sans intervalle de 30 minutes sur une période de 12 heures, une nouvelle visite commence automatiquement.
* **2500 accès** : si un utilisateur génère un grand nombre d’accès sans commencer une nouvelle session, une nouvelle visite est comptabilisée après 2500 demandes d’image.
* **100 accès en 100 secondes** : si une visite consiste de plus de 100 accès se produisant en moins de 100 secondes, la visite se termine automatiquement. Ce comportement indique généralement une activité de robots et cette limite est appliquée pour empêcher ces visites, gourmandes en traitement, d’augmenter la latence et le délai de génération des rapports.

> [!NOTE] La définition d’une visite peut être raccourcie pour une suite de rapports si une requête spécifique est formulée dans ce sens, mais elle ne peut pas être rallongée. Invitez l’un des utilisateurs de votre société ayant souscrit un plan d’assistance dédié à contacter le service d’assistance clientèle pour demander l’exécution de cette modification.

Une nouvelle visite n’est pas lancée dans les cas suivants :

* L’utilisateur ferme l’onglet, le rouvre, puis revient sur votre site dans un délai de 30 minutes. L’utilisateur peut également fermer son navigateur ou redémarrer son ordinateur et être comptabilisé comme une seule visite (à condition qu’il soit revenu sur votre site avant 30 minutes).
* Utilisateurs naviguant sur votre site dans plusieurs onglets. La navigation multi-onglets n’incrémente pas le nombre de visites ou de visiteurs, contrairement à l’utilisation d’un navigateur distinct. Cela est dû au fait que les différents onglets font référence aux mêmes cookies, contrairement à des navigateurs distincts.

Une visite ne coïncide pas nécessairement avec une session de navigateur. Par exemple, si un visiteur ferme le navigateur, l’ouvre de nouveau et se rend sur votre site dans les cinq minutes qui suivent, cette visite est considérée comme étant la suite de celle entamée quelques minutes plus tôt. Cela signifie également que si un visiteur reste sur une page pendant 35 minutes, la visite est fermée et traitée, et une nouvelle visite commence s’il clique sur un lien vers une autre page.

Lorsqu’une visite se termine, toutes les variables comportant une expiration de visite expirent et ne persistent pas. La mesure du nombre de visites est incrémentée lors de la visite suivante de ce visiteur.

> [!NOTE] Si vous utilisez Analytics en tant que source des rapports pour Adobe Target, reportez-vous à la section [Minimisation du nombre de visiteurs ou de visites exagéré dans A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) dans la documentation [!DNL Target].

Pour plus d’informations, voir [Identification des visiteurs uniques](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html) dans le guide Mise en œuvre d’Adobe Analytics.

**Périodes**

Une visite est signalée à chaque période où une activité se produit. Supposons, par exemple, qu’une visite commence à 23h45 le 1er décembre et se poursuit jusqu’à 0h30 le 2 décembre. La visite est comptabilisée le 1er et le 2 décembre. Ceci s’applique aux autres périodes, qu’elles soient hebdomadaires, mensuelles, trimestrielles ou annuelles.
