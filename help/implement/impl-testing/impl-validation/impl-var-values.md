---
description: Assurez-vous que les variables renseignées à partir du script ou du code serveur ne génèrent pas de guillemets susceptibles de perturber les valeurs.
keywords: Mise en œuvre d’Analytics
seo-description: Assurez-vous que les variables renseignées à partir du script ou du code serveur ne génèrent pas de guillemets susceptibles de perturber les valeurs.
seo-title: Variables et valeurs
solution: Analytics
title: Variables et valeurs
topic: Développeur et mise en œuvre
uuid: 2 ff 4857 a -9451-4794-9146-f 417 abd 1 d 1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables et valeurs

Assurez-vous que les variables renseignées à partir du script ou du code serveur ne génèrent pas de guillemets susceptibles de perturber les valeurs.

Exemples :

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

Assurez-vous que la taille des valeurs des variables est conforme aux limites spécifiées dans ce document. Les caractères excédentaires sont tronqués au niveau des serveurs de collecte de données. Ils peuvent affecter la longueur totale, augmenter inutilement la bande passante et être à l’origine d’autres problèmes.

Les caractères $, ™, ®, © et les virgules ne sont pas autorisés dans la variable « products ». En règle générale, ces caractères ne sont utiles dans aucune variable [!DNL Analytics] et ils risquent d’affecter la capacité à interpréter ou exporter des champs. La bonne pratique consiste à limiter les caractères aux 127 premiers caractères ASCII.

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. Veillez au respect de la casse de toutes les variables et fonctions d’[!DNL Analytics], comme illustré ci-dessous.

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

Les noms de pages sont sensibles à la casse. Toute différence crée des enregistrements de page supplémentaires. Ainsi, « Home » et « home » sont deux pages différentes dans [!DNL Analytics].

>[!NOTE]
>
>Il est impossible de combiner plusieurs enregistrements de page dans des rapports.

Validez les liens signalés dans le rapport [!UICONTROL Liens personnalisés]. Assurez-vous que les paramètres corrects sont transmis à la fonction [!UICONTROL tl]. Pour plus d’informations sur les [!UICONTROL liens personnalisés], reportez-vous à la section [Suivi de liens](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
