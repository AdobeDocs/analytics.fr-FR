---
title: Indications du client
description: Découvrez comment les indications du client remplaceront progressivement la chaîne Agent-utilisateur en tant que source des informations sur le périphérique.
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---


# Présentation et FAQ des indications du client

Les indications du client sont des informations individuelles sur le périphérique d’un utilisateur. Elles sont fournies par les navigateurs Chromium tels que Google Chrome et Microsoft Edge. Pour ces navigateurs, les indications du client remplaceront progressivement la chaîne Agent-utilisateur comme source d’informations sur l’appareil. Adobe Analytics mettra à jour son processus de recherche du périphérique de sorte qu’il utilise des indications du client en plus de la chaîne Agent-utilisateur pour déterminer les informations sur le périphérique.

Google divise les indications du client Agent-utilisateur en deux catégories : les indications à faible entropie et à entropie élevée.

* Les **indications à faible entropie** contiennent des informations plus génériques sur les périphériques. Ces indications sont automatiquement fournies par les navigateurs Chromium.

* Les **indications à entropie élevée** contiennent des informations plus détaillées. Ces indications ne sont disponibles que sur demande. AppMeasurement et SDK Web [peuvent être configurés](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) pour demander des indications à entropie élevée. Par défaut, les deux bibliothèques ne demandent **pas** d’indications à entropie élevée.

>[!NOTE]
>
>À compter d’octobre 2022, les nouvelles versions des navigateurs Chromium commenceront à « figer »la version du système d’exploitation représentée dans la chaîne Agent-utilisateur. Lorsque les utilisateurs mettent à niveau leurs périphériques, le système d’exploitation dans la chaîne Agent-utilisateur ne change pas. Ainsi, au fil du temps, les informations relatives à la version d’exploitation telles qu’elles sont représentées dans la chaîne Agent-utilisateur deviendront moins précises. La version du système d’exploitation est une indication à entropie élevée. Pour garantir la précision de la version du système d’exploitation dans vos rapports, il est donc nécessaire de configurer votre bibliothèque de collections pour collecter ces indications à entropie élevée. Au fil du temps, d’autres informations sur les périphériques de la chaîne Agent-utilisateur seront figées, nécessitant alors des indications du client pour maintenir la précision des rapports sur les périphériques.

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

+++**Les rapports sur les périphériques seront-ils modifiés dans Analytics ?**

Les champs de périphérique disponibles pour la création de rapports ne changeront pas. Les données capturées pour ces champs peuvent changer en fonction du champ et de la manière dont vous avez configuré la collecte des indications du clients.

+++

+++**Quels champs de rapport Analytics sont dérivés de la chaîne Agent-utilisateur ?**

* [Navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=fr)
* [Type de navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=fr)
* [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=fr)
* [Types de systèmes d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=fr)
* [Appareils mobiles et type d’appareils mobiles](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=fr)
* [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr)

+++

+++**Quels champs de création de rapports Analytics sont dérivés de valeurs stockées dans des indications à entropie élevée ?**

À compter de septembre 2022, la chronologie publiée par Google pour les indications Agent-utilisateur « figées » indique que la version du système d’exploitation ne sera plus mise à jour à compter d’octobre 2022. Lorsque les utilisateurs effectuent la mise à niveau de leur système d’exploitation, la version du système d’exploitation dans Agent-utilisateur n’est pas mise à jour. Sans une entropie élevée, la précision de la version du système d’exploitation, incluse dans la dimension « Système d’exploitation » d’Analytics, va progressivement se dégrader.

Reportez-vous à la section [chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) pour voir le délai de figement d’autres parties d’Agent-utilisateur.

+++

+++**Comment Adobe utilisera-t-il les indications du client pour obtenir des informations sur le périphérique ?**

Adobe utilise un tiers, Device Atlas, qui utilisera les indications du client et la chaîne Agent-utilisateur pour obtenir des informations sur le périphérique.

+++

+++**Quels navigateurs sont affectés par les indications du client ?**

Les indications du client s’appliquent uniquement aux navigateurs Chromium tels que Google Chrome et Microsoft Edge. Les données d’autres navigateurs ou applications mobiles ne sont pas modifiées.

+++

+++**Les indications du client sont-elles prises en charge pour les connexions non sécurisées ?

Non. Les indications du client ne peuvent être collectées que par le biais d’une connexion HTTP sécurisée, telle que HTTPS.

+++

+++**Des indications du client seront-elles disponibles dans les données envoyées à AEP et CJA via le connecteur source d’Adobe ?**

Adobe prévoit d’inclure des indications du client dans les données par l’intermédiaire du connecteur source d’Adobe au cours du premier semestre 2023.

+++

+++**Comment les indications du client sont-elles représentées dans XDM ?**

Voir [documentation sur les schémas](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) dans Adobe Experience Platform.

+++

+++**Quels sont les différents champs d’indications ? Quels sont ceux qui affectent les rapports sur les périphériques ?**

Le tableau ci-dessous décrit les indications du client depuis septembre 2022.

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



+++**Quelles parties de la chaîne Agent-utilisateur sont « figées » et quand ?**

Voir [la chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Elle peut être sujette à des modifications.

+++
