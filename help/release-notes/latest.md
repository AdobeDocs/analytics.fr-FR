---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 88d60f38d5a87bacb755a49dc884700ac66039ce
workflow-type: ht
source-wordcount: '725'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (août 2024)

**Dernière mise à jour** : 14 août 2024

Ces notes de mise à jour portent sur la période du 14 août 2024 à septembre 2024. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Améliorations du SDK Web pour le suivi des liens** | Plusieurs améliorations notables sont disponibles dans la dernière version du SDK web concernant le suivi des liens, ce qui bénéficie directement à l’Activity Map. Ces nouvelles fonctionnalités sont disponibles dans la bibliothèque JavaScript du SDK Web et dans l’extension de balise du SDK Web.<ul><li>Regroupement d’événements : lorsqu’une personne clique sur un lien interne, vous pouvez choisir de regrouper les données d’événement sur la page suivante au lieu de déclencher un appel d’événement distinct pour le suivi des liens. Cette amélioration réduit le nombre d’événements que le SDK Web utilise par rapport à votre limite contractuelle.</li><li>Filtrer les propriétés de clic : un nouveau rappel qui remplace `OnBeforeLinkClickSend`. Vous pouvez utiliser ce rappel pour filtrer ou obscurcir les données liées aux liens avant de les envoyer à Adobe.</li></ul><p>Voir [clickCollection](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollection) dans le guide d’utilisation du SDK Web pour plus d’informations.</p> | La version bêta ouverte a commencé le 10 juillet 2024. | 18 juillet 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction d’un problème en raison duquel plusieurs valeurs inconnues s’affichaient dans Workspace (AN-353632)
* Correction d’un problème en raison duquel l’e-mail de notification n’était pas envoyé après l’ajout de nouvelles clientes, de nouveaux clients ou de nouveaux profils de produit Analytics dans l’Admin Console (AN-350930)

### Autres correctifs d’Analytics

AN-354361, AN-354248, AN-354211, AN-354324, AN-351532, AN-349808, AN-347831, AN-353777, AN-354092, AN-354064, AN-354202, AN-354006, AN-354097, AN-352548, AN-353819, AN-353818, AN-353628, AN-353747, AN-353527, AN-353490, AN-352647, AN-352656, AN-351274, AN-352135, AN-351519, AN-344906, AN-353697, AN-354499, AN-354402, AN-354062, AN-353905, AN-353932, AN-354142, AN-354194, AN-354182, AN-353758, AN-353039, AN-353612, AN-350799, AN-354414, AN-354636, AN-354249, AN-353637, AN-350949, AN-349402, AN-355103, AN-354174, AN-353823, AN-354819, AN-354215, AN-354219, AN-354040, AN-354763, AN-354597, AN-354478, AN-354528, AN-354335

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | 22 mai 2024 | Une prochaine version du moteur de traitement des accès Analytics, **prévue pour juillet 2024**, introduit l’expiration après 13 mois des `cust_visids` enregistrés. Si « Activer la connexité des visiteurs » est activé dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Actuellement, il n’existe aucune expiration du mappage d’un `cust_visid` pour `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
