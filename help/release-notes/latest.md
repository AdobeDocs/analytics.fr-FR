---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: ht
source-wordcount: '732'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (juillet 2024)

**Dernière mise à jour** : 17 juillet 2024

Ces notes de mise à jour portent sur la période du 17 juillet 2024 à août 2024. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Améliorations du SDK Web pour le suivi des liens** | Plusieurs améliorations notables sont disponibles dans la dernière version du SDK web concernant le suivi des liens, ce qui bénéficie directement à l’Activity Map. Ces nouvelles fonctionnalités sont disponibles dans la bibliothèque JavaScript du SDK Web et dans l’extension de balise du SDK Web.<ul><li>Regroupement d’événements : lorsqu’une personne clique sur un lien interne, vous pouvez choisir de regrouper les données d’événement sur la page suivante au lieu de déclencher un appel d’événement distinct pour le suivi des liens. Cette amélioration réduit le nombre d’événements que le SDK Web utilise par rapport à votre limite contractuelle.</li><li>Filtrer les propriétés de clic : un nouveau rappel qui remplace `OnBeforeLinkClickSend`. Vous pouvez utiliser ce rappel pour filtrer ou obscurcir les données liées aux liens avant de les envoyer à Adobe.</li></ul><p>Voir [clickCollection](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollection) dans le guide d’utilisation du SDK Web pour plus d’informations.</p> | La version bêta ouverte a commencé le 10 juillet 2024. | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction d’un problème qui empêchait de se connecter à l’interface d’utilisation Analytics (AN-352953)
* Correction d’un problème qui empêchait de se connecter à l’application mobile Analytics (AN-352463)
* Correction d’un problème qui empêchait le téléchargement du projet en tant que PDF (AN-352680)
* Correction d’un problème en raison duquel les classifications n’étaient pas importées (AN-352178)

### Autres correctifs d’Analytics

AN-352905; AN-352902; AN-352693; AN-352905, AN-352902, AN-352693, AN-352659, AN-352619, AN-352577, AN-352575, AN-352572, AN-352571, AN-352549, AN-352501, AN-352499, AN-352478, AN-352466, AN-352437, AN-352378, AN-352355, AN-352341, AN-352318, AN-352297, AN-352272, AN-352267, AN-352263, AN-352088, AN-352019, AN-352018, AN-351978, AN-351908, AN-351809, AN-351750, AN-351689, AN-351624, AN-351564, AN-351524, AN-351507, AN-351416, AN-351414, AN-351405, AN-351299, AN-351283, AN-351231, AN-350710, AN-349912, AN-349786, AN-348300, AN-348061, AN-347865, AN-347676, AN-347478, AN-343611, AN-343114, AN-334124

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
