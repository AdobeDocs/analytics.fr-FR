---
title: Conseils client
description: En savoir plus sur les
source-git-commit: b99852f4b8e0a3034ea8965e5646b1ab2f1a8c4c
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Présentation et FAQ des conseils aux clients

Les conseils client sont des informations individuelles sur l’appareil d’un utilisateur. Ils sont fournis par les navigateurs Chromium tels que Google Chrome et Microsoft Edge. Pour ces navigateurs, les conseils du client remplaceront progressivement l’agent utilisateur comme source d’informations sur le périphérique. Adobe Analytics met à jour son processus de recherche de périphérique de sorte qu’il utilise des conseils client en plus de l’agent utilisateur pour déterminer les informations sur le périphérique.

Google divise les conseils du client de l’agent utilisateur en deux catégories : indices à faible entropie et à forte entropie.

* Les indices à faible entropie contiennent des informations plus génériques sur les appareils. Ces astuces sont automatiquement fournies par les navigateurs Chromium.

* Les indices à forte entropie ont des informations plus détaillées. Ces astuces ne sont disponibles que sur demande. AppMeasurement et le SDK Web peuvent être configurés pour demander des indices à forte entropie. Par défaut, les deux bibliothèques le font **not** demander des indices à forte entropie.

>[!NOTE]
>
>À compter d’octobre 2022, les nouvelles versions des navigateurs Chromium commenceront à &quot;figer&quot; la version du système d’exploitation représentée dans la chaîne User Agent. Cela signifie que, au fil du temps, les informations de version de fonctionnement telles qu’elles sont représentées dans l’agent utilisateur deviendront moins précises. La version du système d’exploitation est une indication à forte entropie. Pour garantir la précision de la version du système d’exploitation dans vos rapports, il est donc nécessaire de configurer votre bibliothèque de collections pour collecter ces indices à forte entropie. Au fil du temps, d’autres informations sur les appareils de l’agent utilisateur seront gelées, ce qui nécessite des conseils du client pour maintenir la précision des rapports sur les appareils.

## Questions fréquentes

+++**Comment activer la collecte des conseils client ?**

Les indicateurs à faible entropie sont automatiquement fournis par le navigateur et inclus dans le processus d’Adobe pour les informations sur les périphériques. Les nouvelles versions d’AppMeasurement (à partir de TBD) et du SDK Web (à partir de TBD) peuvent être configurées pour collecter des indices à forte entropie. Pour les deux bibliothèques, la collecte de indices à forte entropie est **désactivé par défaut**. Pour plus d’informations sur la mise en oeuvre de cette méthode, voir ici .

+++**Puis-je choisir les indices à forte entropie que je recueille ?**

Pas pour le moment. Vous pouvez choisir de collecter tous les indices à forte entropie ou aucun.

+++**Y aura-t-il des modifications à la création de rapports sur les appareils dans Analytics ?**

Les champs de périphérique disponibles pour la création de rapports ne changeront pas. Les données capturées pour ces champs peuvent changer en fonction du champ et de la manière dont vous avez configuré la collecte pour les conseils aux clients.

+++**Quels champs de création de rapports Analytics sont dérivés de l’agent utilisateur ?**

* [Navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Type de navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Types de systèmes d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Appareil mobile et type d’appareil mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* Flux de données (notez que les utilisateurs doivent effectuer une mise à jour pour capturer ces champs. En outre, il existe une dépendance dans laquelle nous ne pouvons pas exposer l’ID mobile avec les informations sur l’appareil.)
* Connecteur source Analytics (non prêt)

+++**Quels champs de création de rapports Analytics sont dérivés de valeurs stockées dans des indices à forte entropie ?**

Depuis septembre 2022, la chronologie publiée par Google pour le blocage des indices User-Agent indique que la version du système d’exploitation ne sera plus mise à jour à compter d’octobre 2022. Sans indices à forte entropie, la précision de la version du système d’exploitation, incluse dans la dimension &quot;Système d’exploitation&quot; d’Analytics, va progressivement se dégrader.

Voir [chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) pour voir le délai de blocage de l’agent utilisateur.

+++**Quels navigateurs sont affectés par les conseils aux clients ?**

Les conseils client s’appliquent uniquement aux navigateurs Chromium tels que Google Chrome et Microsoft Edge. Les données d’autres navigateurs ou applications mobiles ne sont pas modifiées.

+++**Comment Adobe utilisera-t-il les conseils du client pour dériver des informations sur le périphérique ?**

Adobe utilise un tiers, Device Atlas, qui utilisera les astuces du client et l’agent utilisateur pour dériver des informations sur l’appareil.

+++**Les conseils client seront-ils disponibles dans les flux de données ?**

Oui. Consultez la documentation (à suivre).

+++**Des conseils client seront-ils disponibles dans les données envoyées à AEP et CJA via Adobe Source Connector ?**

Nous prévoyons d’inclure des conseils aux clients dans les données via Adobe Source Connector au cours du premier semestre 2023.

+++**Comment les indices client sont-ils représentés dans XDM ?**

Voir [documentation sur les schémas](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) dans Adobe Experience Platform.

+++**Où puis-je en savoir plus sur les conseils aux clients ?**

Ceci [Article de blog Google](https://web.dev/user-agent-client-hints/) est une bonne référence et un bon point de départ.

+++**Quels sont les différents champs de conseil ? Quelles sont celles qui affectent la création de rapports sur les périphériques ?**

Le tableau ci-dessous décrit les conseils aux clients depuis septembre 2022.

| Conseil (en-tête) | Conseil | Entropie élevée ou faible | Exemple | Champs de création de rapports Analytics |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | Navigateur et version significative | Faible | Google Chrome 84 | [Navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) et [Type de navigateur](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | Appareil mobile (true ou false) | Faible | TRUE | [Appareil mobile et type d’appareil mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform | Système d’exploitation/plateforme | Faible | Android | [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | Architecture du site | Élevé | &quot;arm&quot; | Aucun? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | Élevé |  | Aucun? |
| Sec-CH-UA-Full-Version | Version complète du navigateur | Élevé | &quot;84.0.4143.2&quot; | Aucun? |
| Sec-CH-UA-Full-Version-List | ??? | Élevé | ??? | Aucun? |
| Sec-CH-UA-Model | Modèle de périphérique | Élevé | &quot;Pixel 3&quot; | Aucun? |
| Sec-CH-UA-Platform-Version | Version du système d’exploitation/de la plateforme | Élevé | &quot;10&quot; | [Système d’exploitation](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**Comment capturer des indices à forte entropie ?**

Des indices à forte entropie peuvent être configurés.

* Pour AppMeasurement directement [lien vers l’entrée d’indicateur dans le guide de mise en oeuvre]
* Dans l’extension Tags Analytics
* Dans le SDK Web.

+++**Quelles données sont supprimées de l’agent utilisateur et quand ?**

Voir [chronologie publiée par Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Il peut être sujet à des modifications.

+++