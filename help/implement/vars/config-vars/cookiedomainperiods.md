---
title: cookieDomainPeriods
description: Permet d’aider AppMeasurement à comprendre quel domaine doit conserver les cookies si votre domaine comporte un point dans son suffixe.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

AppMeasurement détermine son emplacement de cookie en examinant le domaine et le suffixe de domaine. Pour les domaines tels que `example.com`, AppMeasurement définit les cookies au bon emplacement. Toutefois, pour d’autres domaines, comme `example.co.uk`, AppMeasurement peut par erreur définir des cookies sur `co.uk`. La plupart des navigateurs rejettent les cookies définis sur ce domaine non valide, ce qui entraîne des problèmes d’identification des visiteurs.

La variable `cookieDomainPeriods` permet à AppMeasurement de déterminer où les cookies Analytics sont définis en précisant que le suffixe de domaine comporte un point supplémentaire. Cette variable permet à AppMeasurement de prendre en compte le point supplémentaire dans le suffixe du domaine et de définir les cookies au bon emplacement.

* Pour les domaines tels que `example.com` ou `www.example.com`, cette variable n’a pas besoin d’être définie. Si nécessaire, vous pouvez définir cette variable sur `"2"`.
* Pour les domaines tels que `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.


>[!IMPORTANT]
>
>Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `cookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît par défaut que les cookies doivent être conservés sur `example.com`, même sur les URL comportant de nombreux sous-domaines.


## Périodes de domaine de cookie, cookies tiers et identification des visiteurs hérités

Uniquement lorsque vous utilisez l’identification héritée des visiteurs d’Adobe Analytics (au lieu du service d’identification d’Experience Cloud recommandé), la configuration implicite ou explicite de `cookieDomainPeriods` peuvent avoir des répercussions sur la manière dont les visiteurs sont identifiés, selon que les cookies tiers sont bloqués ou non.

Le tableau suivant illustre quatre scénarios possibles.

| Scénario | `cookieDomainPeriods` La configuration est ... | Les cookies tiers sont bloqués ? | Résultat lors de l’utilisation du service d’identification des visiteurs Adobe Analytics hérité |
|:---:|---|---|---|
| 1 | <span style="color:green">Correct</span> | Non | Les visiteurs sont identifiés par un `s_vi` , définissez côté serveur. |
| 2 | <span style="color:green">Correct</span> | Oui | Les visiteurs sont identifiés avec un secours `s_fid` , définissez côté client (domaine de page propriétaire). |
| 3 | <span style="color:red">Incorrect</span> | Non | Les visiteurs sont identifiés avec un identifiant de secours en fonction de la combinaison de l’agent utilisateur et de l’adresse IP. <br/>AppMeasurement est forcé de définir des cookies comme cookies tiers.<br/> La variable `s_vi` est peut-être défini lorsque `cookieDomainPeriods` n’est pas correctement transmise. |
| 4 | <span style="color:red">Incorrect</span> | Oui | Les visiteurs sont identifiés avec un identifiant de secours en fonction de la combinaison de l’agent utilisateur et de l’adresse IP.<br/>AppMeasurement est forcé de définir des cookies comme des cookies tiers bloqués, de sorte qu’aucun cookie n’est défini. |

>[!CAUTION]
>
>Vous avez peut-être configuré par inadvertance `cookieDomainPeriods` <span style="color:red">incorrect</span> (le laissant à sa valeur par défaut de `"2"`) lors de l’utilisation de domaines comme `example.co.uk`. Cette configuration implicite incorrecte entraîne l’identification des visiteurs suivant les scénarios 3 ou 4.
>
>La version 2.26.x ou ultérieure d’AppMeasurement configure `cookieDomainPeriods` automatiquement avec la valeur correcte afin que seuls les scénarios 1 ou 2 soient possibles. Lorsque vous effectuez la mise à jour vers la version 2.26.x ou ultérieure d’AppMeasurement, alors que vous identifiez incorrectement les visiteurs (scénario 3 ou 4), la mise à jour a des implications majeures.
>
>* Les identifiants de visiteur sont réinitialisés et les visiteurs apparaîtront comme de nouveaux visiteurs. Il n’y aura aucun moyen de lier une nouvelle activité à l’identifiant visiteur précédent.
>* Les cookies sont définis (comme pour le suivi des liens ou Activity Map, par exemple).`s_sq` ), ce qui entraîne des différences soudaines dans les rapports.
>
>Lors de la configuration correcte `cookieDomainPeriods` améliorera les fonctionnalités d’AppMeasurement et d’Analytics. Il est recommandé d’évaluer si vous êtes affecté par les modifications résultant de la mise à niveau de votre bibliothèque d’AppMeasurements.
>
> Voir [Cookies Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=fr) pour plus d’informations sur les cookies utilisés par l’AppMeasurement.

## Cookie des périodes de domaine à l’aide du SDK Web

Le SDK Web peut déterminer le domaine de stockage de cookies correct sans cette variable.

## Cookie des périodes de domaine à l’aide de l’extension Adobe Analytics

Les points de domaine désignent un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Points de domaine].

Définissez ce champ sur `3` uniquement pour les domaines contenant un point dans le suffixe. Sinon, ce champ peut être laissé vide.

## Cookie des points de domaine dans l’AppMeasurement de code et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez définir la variable `cookieDomainPeriods` dans la bibliothèque JavaScript d’AppMeasurement ou dans l’éditeur de code personnalisé de l’extension Analytics.

La variable `cookieDomainPeriods` est une chaîne généralement définie sur `"3"`, uniquement pour les domaines qui contiennent un point dans le suffixe. Sa valeur par défaut est `"2"`, ce qui prend en charge la plupart des domaines.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
