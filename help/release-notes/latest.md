---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 66%

---

# Notes de mise à jour actuelles d’Adobe Analytics (septembre 2024)


**Dernière mise à jour** : jeudi 11 septembre 2024

Ces notes de mise à jour portent sur la période du 11 septembre 2024 au début du mois d’octobre. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
|--- | --- | --- | --- |
| **Informations supplémentaires dans la colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de segments** | La colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de segments contient les nouvelles zones de rapports suivantes :<ul><li>**Report Builder** : indique le nombre de mesures calculées ou de segments utilisés dans le Report Builder.</li><li>**Composants ad hoc** : indique le nombre de mesures calculées ad hoc ou de segments ad hoc utilisés dans les projets. Ces mesures calculées et segments ad hoc (également appelés « mesures calculées rapides » et « segments rapides ») ne peuvent être utilisés que dans le projet dans lequel ils ont été créés. Ils sont donc rapportés séparément de la zone de rapport « Projet » dans la colonne « Utilisation dans ».</li></ul>Pour plus d’informations, voir [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager) et [Gestionnaire de segments](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage). |  | 11 septembre 2024 |
| **Extension v3 Activity Map** | L’extension Activity Map v3 est désormais disponible. Si l’extension v2 est installée, désinstallez-la avant d’installer l’extension v3. Accédez à **[!UICONTROL Outils]** > **[!UICONTROL Activity Map]** pour obtenir la dernière version de l’extension. |  | 3 septembre 2024 |


## Correctifs dans Adobe Analytics

A4T : AN-355736
Activity Map : AN-353779
Analysis Workspace : AN-348485 ; AN-349693 ; AN-357247
Application mobile Analytics : AN-352645
Classifications : AN-355636 ; AN-355651 ; AN-355753 ; AN-356005 ; AN-356439 ; AN-356540 ; AN-356577 ; AN-356622
Analyses entre appareils : AN-355138
Flux de données : AN-356258 ; AN-357133
Data Warehouse : AN-339292 ; AN-353807
Exporter les emplacements : AN-356912
API de confidentialité : AN-352420
Report Builder : AN-352555 ; AN-354316
Projets planifiés : AN-355971
Segmentation : AN-352095;
Rapport Target : AN-355748

Autres correctifs : AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | 20 août 2024 | La version du moteur de traitement des accès Analytics du **20 août 2024** applique une expiration de 13 mois des `cust_visids` enregistrés. Si l’option « Activer la connexité des visiteurs » est activée dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Auparavant, il n’y avait aucune expiration du mappage d’un `cust_visid` pour une valeur `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |
| **Champs XDM de détails de mise en oeuvre supplémentaires automatiquement mappés** | 11 septembre 2024 | Lors de l’utilisation de l’Edge Network Adobe Experience Platform pour envoyer des données à Adobe Analytics, les champs XDM `xdm.implementationdetails.name` et `xdm.implementationdetails.environment` sont désormais toujours associés aux variables de données contextuelles `c.a.x.implementationdetails.name` et `c.a.x.implementationdetails.environment`. Auparavant, certains scénarios empêchaient le renseignement de ces valeurs. Ajustez les règles de traitement appropriées en fonction de la disponibilité de ces valeurs. |

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
