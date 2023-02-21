---
title: Indications du client
description: Découvrez comment les indications du client remplaceront progressivement la chaîne Agent-utilisateur en tant que source des informations sur le périphérique.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
source-git-commit: 66c314d45c4ee4f15cc2e7d05ea248b95ff3c717
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 93%

---

# Présentation et FAQ des indications du client

Les indications du client sont des informations individuelles sur le périphérique d’un utilisateur. Elles sont fournies par les navigateurs Chromium tels que Google Chrome et Microsoft Edge. Pour ces navigateurs, les indications du client remplaceront progressivement la chaîne Agent-utilisateur comme source d’informations sur l’appareil. Adobe Analytics mettra à jour son processus de recherche du périphérique de sorte qu’il utilise des indications du client en plus de la chaîne Agent-utilisateur pour déterminer les informations sur le périphérique.

## Conseils sur les clients à faible entropie et à forte entropie

Google divise les indications du client Agent-utilisateur en deux catégories : les indications à faible entropie et à entropie élevée.

* Les **indications à faible entropie** contiennent des informations plus génériques sur les périphériques. Ces indications sont automatiquement fournies par les navigateurs Chromium.

* Les **indications à entropie élevée** contiennent des informations plus détaillées. Ces indications ne sont disponibles que sur demande. AppMeasurement et SDK Web peuvent être configurés pour demander des indications à entropie élevée. Par défaut, les deux bibliothèques ne demandent **pas** d’indications à entropie élevée.

À compter d’octobre 2022, les nouvelles versions des navigateurs Chromium ont commencé à « figer » la version du système d’exploitation représentée dans la chaîne Agent-utilisateur. La version du système d’exploitation est une indication à entropie élevée. Pour garantir la précision de la version du système d’exploitation dans vos rapports, il est donc nécessaire de configurer votre bibliothèque de collections pour collecter ces indications à entropie élevée. Au fil du temps, d’autres informations sur les périphériques de la chaîne Agent-utilisateur seront figées, nécessitant alors des indications du client pour maintenir la précision des rapports sur les périphériques.

À compter de mars 2023, les conseils aux clients seront intégrés au processus de recherche des appareils Analytics. AppMeasurement et le SDK Web prennent actuellement en charge la collecte de données relatives aux indications, mais ils ne seront pas utilisés dans la recherche de périphériques avant la mi-février. Comme indiqué ci-dessous, la version du système d’exploitation a été figée à partir du mois d’octobre, mais en raison d’un déploiement progressif et de la mise à disposition d’une version figée du système d’exploitation par de nombreux agents utilisateurs (plus d’informations [ici](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=fr)), nous estimons que cela affectera moins de 3 % des visiteurs Chrome.

>[!NOTE]
>
> Depuis janvier 2023, certaines versions des systèmes d’exploitation Mac et Windows sont incorrectement représentées dans l’agent utilisateur, mais correctement représentées dans les indices client à forte entropie. Consultez [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=fr) pour plus d’informations.

AAM nécessite la collecte d’indices à forte entropie pour préserver toutes les fonctionnalités. Si vous utilisez le [transfert côté serveur vers AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=fr), vous pouvez ensuite activer la collecte d’indications à entropie élevée.

## Questions fréquentes

+++**Où puis-je en savoir plus sur les indications du client ?**

Cet [article de blog Google](https://web.dev/user-agent-client-hints/) est une bonne référence et un bon point de départ.

+++

+++**Comment activer la collecte des indications du client ?**

Les indications à faible entropie sont automatiquement fournies par le navigateur et ingérées pour la dérivation des informations sur le périphérique et le navigateur. Les nouvelles versions du SDK Web (à partir de 2.12.0) et de AppMeasurement (à partir de 2.23.0) peuvent être configurées pour collecter des indications à entropie élevée via leurs extensions Balises respectives ou directement via une option de configuration. Consultez les instructions pour le [SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=fr#enabling-high-entropy-client-hints) et [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=fr).

Pour les deux bibliothèques, la collecte d’indications à entropie élevée est **désactivée par défaut**.

Pour les données envoyées via l’API, par exemple via l’[API Data Insertion](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou l’[API Bulk Data Insertion](https://experienceleague.adobe.com/docs/analytics/import/bulk-data-insert.html?lang=fr), les indications doivent être explicitement incluses dans le payload. Consultez la documentation correspondante pour plus de détails.

+++

+++**Puis-je choisir les indications à entropie élevée que je collecte ?**

Pas pour le moment. Vous pouvez choisir de collecter toutes les indications à entropie élevée ou aucune.

+++

+++**Quelles sont les différentes valeurs des indications du client ?**

Le tableau ci-dessous décrit les indications du client depuis octobre 2022.

| Indication | Description | Entropie élevée ou faible | Exemple |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navigateur et version significative | Faible | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | Équipement mobile (true ou false) | Faible | `true` |
| Sec-CH-UA-Platform | Système d’exploitation/plateforme | Faible | `"Android"` |
| Sec-CH-UA-Arch | Architecture du site | Élevé | `"arm"` |
| Sec-CH-UA-Bitness | Architecture Bitness | Élevé | `"64"` |
| Sec-CH-UA-Full-Version | Version complète du navigateur | Élevé | `"84.0.4143.2"` |
| Sec-CH-UA-Full-Version-List | Liste des marques avec leur version | Élevé | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| Sec-CH-UA-Model | Modèle de périphérique | Élevé | `"Pixel 3"` |
| Sec-CH-UA-Platform-Version | Version du système d’exploitation/de la plateforme | Élevé | `"10"` |

* Les indices à faible entropie sont collectés via l’en-tête de la requête.
* Les indices à forte entropie sont collectés via JavaScript et transmis par le biais de valeurs de paramètre de chaîne de requête. Les paramètres de chaîne de requête utilisent `h.` comme préfixe dans la demande d’image.

Les indications à entropie élevée sont collectées via un appel JavaScript et transmises via un paramètre de requête.

+++

+++**Les rapports sur les périphériques seront-ils modifiés dans Analytics ?**

Les champs de périphérique disponibles pour la création de rapports ne changeront pas. Les données capturées pour ces champs peuvent changer en fonction du champ et de la manière dont vous avez configuré la collecte des indications du clients.

+++

+++**Quels champs de rapport Analytics sont dérivés de la chaîne Agent-utilisateur ?**

Ces champs sont directement dérivés de la chaîne Agent-utilisateur, mais celle-ci peut être utilisée pour dériver des valeurs pour d’autres champs liés au périphérique, en fonction de ses informations.

* [Navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=fr)
* [Type de navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=fr)
* [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=fr)
* [Types de systèmes d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=fr)
* [Appareils mobiles et type d’appareils mobiles](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=fr)

+++

+++**Quelles parties de la chaîne Agent-utilisateur sont « figées » et quand ?**

Voir [la chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Elle peut être sujette à des modifications.

+++

+++**De quelle manière l’application Analytics dépend-elle de l’agent utilisateur ?**

Les informations sur le périphérique dans les rapports proviennent de l’agent utilisateur. Nous avons mis à jour nos processus afin d’utiliser à la fois l’agent utilisateur et les indications du client, le cas échéant.

L’identifiant de secours ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=fr)) provient de l’agent utilisateur et de l’adresse IP. Cet identifiant n’est utilisé que si un cookie ne peut pas être défini et n’est donc pas largement utilisé.

+++

+++**Quels champs de création de rapports Analytics sont dérivés de valeurs stockées dans des indications à entropie élevée ?**

Cette situation évoluera au fur et à mesure que Google « figera » d’autres parties de l’agent utilisateur. Le premier champ à être directement impacté est le « Système d’exploitation », qui inclut la version du système d’exploitation selon la chronologie publiée par Google pour les indications Agent-utilisateur « figées ». La version du système d’exploitation sera figée à compter de fin octobre 2022 avec la version 107 de Chromium. À ce stade, la version du système d’exploitation dans l’agent utilisateur sera inexacte dans certains cas.

Reportez-vous à la section [chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) pour voir le délai de figement d’autres parties d’Agent-utilisateur.

+++

+++**Comment Adobe utilisera-t-il les indications du client pour obtenir des informations sur le périphérique ?**

Adobe fait appel à un tiers, Device Atlas, qui utilise à la fois les indications du client et la chaîne Agent-Utilisateur pour obtenir des informations sur le périphérique.

+++

+++**Quels navigateurs sont affectés par les indications du client ?**

Les indications du client s’appliquent uniquement aux navigateurs Chromium tels que Google Chrome et Microsoft Edge. Les données d’autres navigateurs ou applications mobiles ne sont pas modifiées.

+++

+++**Les indications du client sont-elles prises en charge pour les connexions non sécurisées ?**

Non. Les indications du client ne peuvent être collectées que par le biais d’une connexion HTTP sécurisée, telle que HTTPS.

+++

+++**Comment inclure des données d’indication du client lors de l’utilisation de l’envoi d’API ?**

Consultez la documentation pour les inclure via l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**Des indications du client seront-elles disponibles dans les données envoyées à AEP et CJA via le connecteur source d’Adobe ?**

Adobe prévoit d’inclure des indications du client dans les données par l’intermédiaire du connecteur source d’Adobe au cours du premier semestre 2023.

+++

+++**Comment les indications du client sont-elles représentées dans XDM ?**

Voir [documentation sur les schémas](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) dans Adobe Experience Platform.

+++

+++**Le transfert côté serveur vers AAM prendra-t-il en charge les indications du client ?**

Oui. Les indications du client seront incluses dans les données transférées à AAM. Notez qu’AAM nécessite la collecte d’indications à entropie élevée pour préserver toutes les fonctionnalités. Si vous utilisez le [transfert côté serveur vers AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=fr), vous pouvez ensuite activer la collecte d’indications à entropie élevée.

+++
