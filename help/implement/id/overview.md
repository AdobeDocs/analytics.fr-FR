---
title: Identification des visiteurs dans Adobe Analytics
description: Découvrez comment identifier les visiteurs dans Adobe Analytics à l’aide des bonnes pratiques les plus récentes.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 10%

---

# Identification des visiteurs dans Adobe Analytics

L’identification des visiteurs et visiteuses est essentielle à la valeur fournie par Adobe Analytics pour comprendre le comportement des utilisateurs et utilisatrices en ligne. Cela implique de lier les accès à la même personne au fil du temps à l’aide d’un identifiant commun. Une identification précise des visiteurs garantit des mesures fiables et soutient une stratégie d’implémentation saine. Adobe recommande aux entreprises de donner la priorité aux services d’identité modernes pour assurer la cohérence et l’intégrité des données sur toutes les plateformes.

L’identification des visiteurs dans Adobe Analytics comprend les composants suivants :

* Identifiant côté client : généralement stocké dans un cookie propriétaire. Les implémentations qui reposent sur des cookies tiers sont moins cohérentes avec l’identification des visiteurs en raison des normes modernes de confidentialité des navigateurs.
* Identifiant côté serveur : chaque identifiant visiteur Analytics est lié à un profil sur les serveurs Adobe. Ces profils de visiteur permettent la persistance sur des variables telles que [eVars](/help/components/dimensions/evar.md). Les profils sont supprimés après au moins 13 mois d’inactivité, quelle que soit l’expiration du cookie de l’identifiant visiteur.

## Ordre des opérations d’identification Adobe Analytics

Lorsqu’Adobe reçoit un accès, les vérifications suivantes sont effectuées dans l’ordre. Si une propriété donnée est présente, Adobe utilise cet identifiant pour l’accès. Si plusieurs identifiants sont présents dans un accès, seule la première méthode est utilisée. Notez que l’ordre des opérations ne reflète pas celui recommandé par Adobe pour identifier les visiteurs.

| Ordre utilisé | Paramètre de requête | Présent quand |
|---|---|---|
| **<sup>er</sup>** | `vid` | La variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) est définie. |
| **2<sup>ème</sup>** | `aid` | Le visiteur possède un cookie [`s_vi`](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/cookies/analytics) existant. Défini lors de l’implémentation, sans ou avant l’implémentation du service d’identifiant de visiteur. |
| **3<sup>ème</sup>** | `mid` | Le visiteur possède un cookie [`s_ecid`](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/cookies/analytics) existant. Définissez sur les implémentations à l’aide du service d’identités Adobe Experience Cloud [&#128279;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Adobe recommande d’utiliser le service d’ID pour toutes les implémentations lorsque cela est possible. |
| **4<sup>ème</sup>** | `fid` | Le visiteur possède un cookie [`s_fid`](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/cookies/analytics) existant. AppMeasurement génère automatiquement un identifiant de secours si `aid` et `mid` ne peuvent pas être définis, quelle qu’en soit la raison. |
| **5<sup>ème</sup>** | Adresse IP + agent utilisateur | Utilisé en dernier recours pour identifier un visiteur unique si le navigateur du visiteur n’accepte pas les cookies. Un identifiant visiteur haché est généré avant l’[obscurcissement d’IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). Si l’adresse IP n’est pas disponible, d’autres détails IP (tels que l’adresse IP de la passerelle) sont utilisés à la place. |

L’identifiant visiteur sélectionné est ensuite haché et devient son identifiant côté serveur. Cet identifiant côté serveur est disponible sous la forme `visid_high` + `visid_low` dans [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md).

## Comportement affectant le nombre de visiteurs uniques

Les identifiants de visiteur unique sont généralement stockés dans un cookie de navigateur. Un nouveau visiteur unique est comptabilisé si un visiteur effectue l’une des actions suivantes :

* Efface leurs cookies à tout moment. Un visiteur unique est comptabilisé pour un accès après chaque effacement de son cache.
* Les cookies d’identifiant visiteur expirent en raison des paramètres de confidentialité de leur navigateur. Certains navigateurs incluent des méthodes de prévention du suivi qui limitent la durée de vie des cookies.
* Ouvre un navigateur différent sur le même ordinateur. Un visiteur unique est comptabilisé par navigateur.
* Ouvre une session de navigation privée (comme l’onglet Chrome Incognito ). Un visiteur unique est comptabilisé par session de navigation une fois tous les onglets fermés.
* Visite votre site sur différents appareils. Un visiteur unique est comptabilisé par appareil.
* Visite votre site après plus de 13 mois d’inactivité.

Envisagez d’utiliser l’[assemblage](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/stitching/overview) dans Customer Journey Analytics pour identifier la même personne à l’aide de plusieurs navigateurs ou appareils.

## Comportement qui n’affecte pas le nombre de visiteurs uniques

Un nouveau visiteur unique n’est *pas* comptabilisé tant que l’identifiant du visiteur est conservé :

* Ferme son navigateur (depuis moins de 13 mois)
* Mise à niveau du navigateur vers la version la plus récente
* Redémarre son ordinateur.
