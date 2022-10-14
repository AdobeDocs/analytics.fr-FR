---
title: Indications du client
description: Découvrez comment les indications du client remplaceront progressivement la chaîne Agent-utilisateur en tant que source des informations sur le périphérique.
source-git-commit: 1bd34bd2bdbe5ad8abb75be81554837e53c112fb
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 75%

---


# Présentation et FAQ des indications du client

Les indications du client sont des informations individuelles sur le périphérique d’un utilisateur. Elles sont fournies par les navigateurs Chromium tels que Google Chrome et Microsoft Edge. Pour ces navigateurs, les indications du client remplaceront progressivement la chaîne Agent-utilisateur comme source d’informations sur l’appareil. Adobe Analytics mettra à jour son processus de recherche du périphérique de sorte qu’il utilise des indications du client en plus de la chaîne Agent-utilisateur pour déterminer les informations sur le périphérique.

Google divise les indications du client Agent-utilisateur en deux catégories : les indications à faible entropie et à entropie élevée.

* Les **indications à faible entropie** contiennent des informations plus génériques sur les périphériques. Ces indications sont automatiquement fournies par les navigateurs Chromium.

* Les **indications à entropie élevée** contiennent des informations plus détaillées. Ces indications ne sont disponibles que sur demande. AppMeasurement et SDK Web [peuvent être configurés](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) pour demander des indications à entropie élevée. Par défaut, les deux bibliothèques ne demandent **pas** d’indications à entropie élevée.

>[!NOTE]
>
>À compter d’octobre 2022, les nouvelles versions des navigateurs Chromium commenceront à « figer »la version du système d’exploitation représentée dans la chaîne Agent-utilisateur. La version du système d’exploitation est une indication à entropie élevée. Pour garantir la précision de la version du système d’exploitation dans vos rapports, il est donc nécessaire de configurer votre bibliothèque de collections pour collecter ces indications à entropie élevée. Au fil du temps, d’autres informations sur les périphériques de la chaîne Agent-utilisateur seront figées, nécessitant alors des indications du client pour maintenir la précision des rapports sur les périphériques.

>[!NOTE]
>
>AAM nécessite la collecte d’indices à forte entropie pour préserver toutes les fonctionnalités. Si vous utilisez [transfert côté serveur vers AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=fr) vous pouvez ensuite activer la collecte de conseils à forte entropie.

## Questions fréquentes

+++**Où puis-je en savoir plus sur les indications du client ?**

Cet [article de blog Google](https://web.dev/user-agent-client-hints/) est une bonne référence et un bon point de départ.

+++

+++**Comment activer la collecte des indications du client ?**

Les indications à entropie élevée sont automatiquement fournies par le navigateur et incluses dans le processus d’Adobe pour la dérivation des informations sur le périphérique et le navigateur. Les nouvelles versions d’AppMeasurement (commençant par 2.23.0) et du SDK Web (commençant par 2.12.0) peuvent être configurées pour collecter des indications à entropie élevée. Pour les deux bibliothèques, la collecte d’indications à entropie élevée est **désactivée par défaut**.

+++

+++**Comment capturer des indications à entropie élevée ?**

Les indications à entropie élevée peuvent être configurées avec le SDK Web et les bibliothèques AppMeasurement via leurs extensions de balises respectives ou directement avec l’indicateur collectHighEntropyUserAgentHints.

+++

+++**Puis-je choisir les indications à entropie élevée que je collecte ?**

Pas pour le moment. Vous pouvez choisir de collecter toutes les indications à entropie élevée ou aucune.

+++

+++**Quelles sont les différentes valeurs d’indice client ?**

Le tableau ci-dessous décrit les conseils aux clients en date d’octobre 2022.

| Indication | Description | Entropie élevée ou faible | Exemple |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navigateur et version significative | Faible | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Équipement mobile (true ou false) | Faible | TRUE |
| Sec-CH-UA-Platform | Système d’exploitation/plateforme | Faible | &quot;Android&quot; |
| Sec-CH-UA-Arch | Architecture du site | Élevé | &quot;arm&quot; |
| Sec-CH-UA-Bitness | Architecture Bitness | Élevé | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Version complète du navigateur | Élevé | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Liste des marques avec leur version | Élevé | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modèle de périphérique | Élevé | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Version du système d’exploitation/de la plateforme | Élevé | &quot;10&quot; |

+++

+++**Les rapports sur les périphériques seront-ils modifiés dans Analytics ?**

Les champs de périphérique disponibles pour la création de rapports ne changeront pas. Les données capturées pour ces champs peuvent changer en fonction du champ et de la manière dont vous avez configuré la collecte des indications du clients.

+++

+++**Quels champs de rapport Analytics sont dérivés de la chaîne Agent-utilisateur ?**

Ces champs sont directement dérivés de User-Agent, mais User-Agent peut être utilisé pour dériver des valeurs pour d’autres champs liés à l’appareil, en fonction des détails de l’appareil.

* [Navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=fr)
* [Type de navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=fr)
* [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=fr)
* [Types de systèmes d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=fr)
* [Appareils mobiles et type d’appareils mobiles](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=fr)

+++

+++**Quels champs de création de rapports Analytics sont dérivés de valeurs stockées dans des indications à entropie élevée ?**

Cela changera au fil du temps, car Google &quot;gèle&quot; d’autres parties de l’agent utilisateur. Le premier champ à être directement impacté est &quot;Système d’exploitation&quot; qui inclut la version du système d’exploitation Selon le calendrier publié par Google pour le &quot;blocage&quot; des indices User-Agent, la version du système d’exploitation sera gelée à compter de la fin octobre 2022 avec la version 107 de Chromium. À ce stade, la version du système d’exploitation dans l’agent utilisateur sera inexacte dans certains cas.

Reportez-vous à la section [chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) pour voir le délai de figement d’autres parties d’Agent-utilisateur.

+++

+++**Comment Adobe utilisera-t-il les indications du client pour obtenir des informations sur le périphérique ?**

Adobe utilise un tiers, Device Atlas, qui utilisera les astuces du client et User-Agent pour obtenir des informations sur l’appareil.

+++

+++**Quels navigateurs sont affectés par les indications du client ?**

Les conseils client s’appliquent uniquement aux navigateurs Chromium tels que Google Chrome et Microsoft Edge. Les données d’autres navigateurs ou applications mobiles ne sont pas modifiées.

+++

+++**Les conseils client sont-ils pris en charge sur les connexions non sécurisées ?**

Non. Les indications du client ne peuvent être collectées que par le biais d’une connexion HTTP sécurisée, telle que HTTPS.

+++

+++**Des indications du client seront-elles disponibles dans les données envoyées à AEP et CJA via le connecteur source d’Adobe ?**

Adobe prévoit d’inclure des indications du client dans les données par l’intermédiaire du connecteur source d’Adobe au cours du premier semestre 2023.

+++

+++**Comment les indications du client sont-elles représentées dans XDM ?**

Voir [documentation sur les schémas](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) dans Adobe Experience Platform.

+++

+++**Quelles parties de la chaîne Agent-utilisateur sont « figées » et quand ?**

Voir [la chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Elle peut être sujette à des modifications.

+++

+++**AAM transfert côté serveur prend-il en charge les conseils du client ?**

Oui. Les indices client seront inclus dans les données transférées à AAM. Notez que AAM nécessite la collecte d’indices à forte entropie pour préserver toutes les fonctionnalités. Si vous utilisez [transfert côté serveur vers AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) vous pouvez ensuite activer la collecte d’indices à forte entropie.

+++

