---
description: L’intégration Genesis pour DFA met à profit l’identifiant de configuration DFA Floodlight (dfa_SPOTID), qui améliore la cohérence du rapport entre DFA et le système de collecte de données Adobe.
keywords: DFA
seo-description: L’intégration Genesis pour DFA met à profit l’identifiant de configuration DFA Floodlight (dfa_SPOTID), qui améliore la cohérence du rapport entre DFA et le système de collecte de données Adobe.
seo-title: Mise à jour du code de collecte de données de votre site web
solution: Analytics
title: Mise à jour du code de collecte de données de votre site web
topic: Connecteurs de données
uuid: a 97 d 1 b 62-f 883-48 b 1-9516-4 f 889 e 701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Mise à jour du code de collecte de données de votre site web{#update-your-web-site-s-data-collection-code}

L’intégration Genesis pour DFA met à profit l’identifiant de configuration DFA Floodlight (dfa_SPOTID), qui améliore la cohérence du rapport entre DFA et le système de collecte de données Adobe.

>[!NOTE]
>
>Le terme Spotlight a été remplacé par Floodlight dans une version récente de Google DFA. Le paramètre JavaScript `dfa_SPOTID` a été nommé en fonction de la terminologie Spotlight, mais il est utilisé avec les deux versions.

Pour activer l’intégration DFA sur votre site Web, vous devez mettre à jour le code de collecte de données JavaScript en ajoutant ce qui suit :

* Module Integrate pour DFA
* Ajout à votre code de collecte

## Module Integrate pour DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

L’intégration DFA met à profit le module Integrate d’Adobe Marketing Cloud, qui ajoute la fonctionnalité à votre code de collecte de données JavaScript ( `s_code.js`). The Integrate Module comes as part of the .zip file when you download the AppMeasurement for Javascript code from the [Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). Contactez votre conseiller Adobe uniquement si vous avez besoin d'aide supplémentaire pour le trouver.

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## Ajout à votre code de collecte {#section-8f98c727f1ba414fb8b4f02d696b8791}

Selon vos sélections lors de l’activation de l’intégration DFA dans l’assistant d’intégration, les connecteurs de données génèrent et vous envoient par courrier électronique un ajout personnalisé pour votre code de collecte de données JavaScript. Insérez ce code dans la section principale du fichier `s_code.js` (et non dans la fonction `doPlugins` ni dans une autre fonction).

L’exemple de code illustré ci-dessous est présenté à seule fin de référence ; utilisez le code qui vous a été envoyé par courrier électronique quand vous aurez exécuté l’assistant d’intégration Connecteurs de données.

Le code de collecte est constitué des composants suivants :

* Paramètres DFA Integrate
* Modules externes requis pour l’intégration

**Paramètres DFA Integrate**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

Le bloc Paramètres DFA Integrate définit les variables requises par l’intégration DFA. Les valeurs pour chacune de ces variables sont issues des sources suivantes :

**CSID** : identifiant du site client. Généré par DFA une fois que vous avez exécuté l’assistant d’intégration. Les connecteurs de données prérenseignent cette variable à l’aide de votre identifiant du site client DFA et vous envoient cette valeur dans le courrier électronique de configuration après avoir exécuté l’assistant d’intégration. Cette variable n’est pas requise si la fonction AdServing avancée est activée sur votre compte.

**SPOTID** : configuration Floodlight (précédemment appelée Spotlight ID). Les Connecteurs de données prérenseignent cette variable à l’aide de votre identifiant de configuration DFA Floodlight, en fonction des informations de compte DFA que vous avez spécifiées dans l’assistant d’intégration.

**tEvar** : variable de transfert. Les Connecteurs de données prérenseignent cette variable à l’aide du nom de variable Analytics que vous avez spécifié comme variable d’affichage publicitaire dans l’assistant d’intégration. Ne changez pas cette valeur sans en avoir soigneusement discuté avec les services techniques ou les services Adobe Engineering.

**errorEvar** : variable d’erreur. Les Connecteurs de données prérenseignent cette variable à l’aide du nom de variable Analytics que vous avez spécifié comme variable d’échec de requête DFA dans l’assistant d’intégration.

**timeoutEvent** : événement de dépassement de délai. Les Connecteurs de données prérenseignent cette variable à l’aide du nom de variable Analytics que vous avez spécifié comme variable d’événement de dépassement de délai dans l’assistant d’intégration.

**requestURL** : hôte DFA à distance auquel demander les informations publicitaires. Ne modifiez pas cette valeur, sauf si Adobe vous a demandé de le faire.

**maxDelay** : spécifie le temps d’attente par le code de collecte de données JavaScript pour obtenir une réponse du serveur DFA Floodlight, en millisecondes. Adobe recommande de faire des essais avec cette valeur afin de rechercher la valeur optimale en fonction du trafic sur votre site. Par exemple, si vous augmentez cette valeur, davantage de données DFA sont généralement collectées, mais vous risquez de perdre des données de base sur le visiteur si celui-ci quitte le site durant la période du délai. Si vous réduisez cette valeur, le risque de perdre des données d’accès est moindre, mais il est possible que moins de données DFA soient envoyées avec les données d’accès Adobe.

**visitCookie** : nom du cookie utilisé pour restreindre les appels DFA à une fois par visite.

**clickThroughParam** : chaîne de requête, généralement incluse sur toutes les publicités, qui avertit le module Integrate qu’un clic vient d’avoir lieu. La présence de ce paramètre dans la chaîne de requête provoque la demande sur les serveurs DFA Floodlight, même si le visiteur a déjà été sondé au cours des 30 dernières minutes.

**newRsidsProp** : (facultatif) valeur mappée à une variable de propriété de trafic non utilisée. L’intégration DFA collecte et stocke cette valeur dans le cookie de visite afin d’identifier les suites de rapports qui ont collecté des données pour un visiteur particulier. Cette propriété est nécessaire seulement pour les mises en œuvre personnalisées avec les services Adobe Engineering.

**Modules externes requis pour l’intégration**

L’ajout du code de collecte incorpore les modules externes supplémentaires qui améliorent le fonctionnement de l’intégration DFA :

* Limite les requêtes DFA à une requête par visite.
* Procure une certaine flexibilité eu égard au nom de cookie. La plupart des organisations utilisent s_dfa, mais vous pouvez utiliser n’importe quel nom de cookie valide pour l’intégration DFA.
* Élimine les redirections superflues. Les données d’affichage publicitaire sont collectées en temps réel ; pour cette raison, les serveurs de collecte Adobe et les serveurs DFA peuvent éventuellement échanger des données sur chaque page vue. Le module externe bloque ces échanges de données quand les informations ne sont pas nécessaires.

>[!CAUTION]
>
>L'un des mécanismes utilisés par le module externe pour éliminer les requêtes DFA superflues est un cookie de visite basé sur un domaine. Une suite de rapports d’intégration qui s’étend sur plusieurs domaines gonfle les données de clics et affichages publicitaires quand les visiteurs traversent les domaines après un affichage ou clic publicitaire influencé par DFA.

