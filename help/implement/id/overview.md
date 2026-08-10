---
title: Identification des visiteurs dans Adobe Analytics
description: Découvrez comment identifier les visiteurs dans Adobe Analytics à l’aide des bonnes pratiques les plus récentes.
exl-id: 8d26a556-84fe-4fb5-98d6-a16b69423e5b
TQID: https://experienceleague.adobe.com/uwEv9cl3234uiWhZEZLqgAVo42b-9L-9YEIGD97Pw-Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 9%

---

# Identification des visiteurs dans Adobe Analytics

L’identification des visiteurs et visiteuses est essentielle à la valeur fournie par Adobe Analytics pour comprendre le comportement des utilisateurs et utilisatrices en ligne. Cela implique de lier les accès à la même personne au fil du temps à l’aide d’un identifiant commun. Une identification précise des visiteurs garantit des mesures fiables et soutient une stratégie d’implémentation saine. Adobe recommande aux entreprises de donner la priorité aux services d’identité modernes pour assurer la cohérence et l’intégrité des données sur toutes les plateformes.

L’identification des visiteurs dans Adobe Analytics comprend les composants suivants :

* Identifiant côté client : généralement stocké dans un cookie propriétaire. Les implémentations qui reposent sur des cookies tiers sont moins cohérentes avec l’identification des visiteurs en raison des normes modernes de confidentialité des navigateurs.
* Identifiant côté serveur : chaque identifiant visiteur Analytics est lié à un profil sur les serveurs Adobe. Ces profils de visiteur permettent la persistance sur des variables telles que [eVars](/help/components/dimensions/evar.md). Les profils sont supprimés après au moins 13 mois d’inactivité, quelle que soit l’expiration du cookie de l’identifiant visiteur.

## Ordre des opérations d’identification Adobe Analytics

Lorsqu’Adobe reçoit un accès, les vérifications suivantes sont effectuées dans l’ordre. Si une propriété donnée est présente, Adobe utilise cet identifiant pour l’accès. Si plusieurs identifiants sont présents dans un accès, seule la première méthode est utilisée. Notez que l’ordre des opérations ne reflète pas celui recommandé par Adobe pour identifier les visiteurs.

| Ordre utilisé | Paramètre de requête | Présenter quand |
|---|---|---|
| <sup>er </sup>**&#x200B;** | `vid` | La variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) est définie. |
| **2<sup>ème</sup>** | `aid` | Le visiteur possède un cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) existant. Définissez sur les mises en œuvre sans ou avant la mise en œuvre du service d’identification des visiteurs. |
| **3<sup>ème</sup>** | `mid` | Pour les implémentations basées sur AppMeasurement (y compris l’extension de balise Analytics) utilisant le [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home), le visiteur dispose d’un cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) ou `AMCV` existant. Pour les implémentations basées sur Web SDK, le visiteur possède un cookie [`kndctr_<orgId>_identity`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/web-sdk) ou `AMCV` existant. Adobe recommande d’utiliser l’ECID comme principale méthode d’identification des visiteurs pour toutes les implémentations, dans la mesure du possible. |
| **4<sup>ème</sup>** | `fid` | Le visiteur possède un cookie [`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) existant. AppMeasurement génère automatiquement un identifiant de secours si `aid` et `mid` ne peuvent pas être définis, quelle qu’en soit la raison. |
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
