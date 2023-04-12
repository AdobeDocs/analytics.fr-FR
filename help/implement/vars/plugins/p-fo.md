---
title: p_fo (Page First Only)
description: Permet de s’assurer que certaines routines ne se déclenchent qu’une seule fois par page.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 78%

---

# Plug-in Adobe : p_fo (Page First Only)

{{plug-in}}

Le plug-in `p_fo` est un utilitaire qui vérifie l’existence d’un objet JavaScript spécifique. Si l’objet n’existe pas, alors le plug-in le crée et renvoie la valeur `true`. Si l’objet JavaScript existe déjà sur la page, alors il renvoie la valeur `false`. Ce plug-in est utile pour exécuter le code une seule fois sur une page. Plusieurs autres plug-ins dépendent de ce code pour fonctionner. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin de connaître le nombre de fois que le code s’exécute sur une page ou si vous n’utilisez aucun plug-in dépendant.

## Installation du module externe à l’aide de l’extension SDK Web

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK Web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** sur la gauche, puis cliquez sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** sur la gauche, puis cliquez sur le bouton **[!UICONTROL Catalogue]** tab
1. Recherchez et installez le **[!UICONTROL Plug-ins SDK Web courants]** extension .
1. Cliquez sur **[!UICONTROL Éléments de données]** sur la gauche, puis cliquez sur l’élément de données souhaité.
1. Définissez le nom de l’élément de données souhaité avec la configuration suivante :
   * Extension : Plug-ins SDK Web courants
   * Élément de données: `p_fo`
1. Enregistrez et publiez les modifications sur l’élément de données.

## Installation manuelle du plug-in implémentant le SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans une mise en oeuvre manuelle du SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de p_fo
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `p_fo` utilise les arguments suivants :

* **on** (obligatoire, chaîne) : nom de l’objet JavaScript créé par le plug-in si celui-ci n’existe pas encore sur la page.

Si lʼobjet nʼexiste pas encore, cette fonction renvoie la valeur `true` et crée lʼobjet. Si lʼobjet existe déjà, cette fonction renvoie la valeur `false`.

## Exemples d’appels

### Exemple 1

Le code suivant vérifie l’existence de l’objet « myobject » dans la page.  Si l’objet « myobject » n’existe pas, le code le crée et renvoie la valeur true.  Par conséquent, le code de l’instruction conditionnelle (c’est-à-dire Console.log(&#39;hello&#39;);) s’exécutera.

D’autre part, si l’objet « myobject » existe déjà au moment de l’appel p_fo, la fonction p_fo renvoie la valeur false et, par conséquent, l’instruction conditionnelle est définie sur false.  Dans ce cas, le code de l’instruction conditionnelle ne s’exécute pas.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**REMARQUE :** chaque fois quʼun nouveau modèle DOM/nouvel objet de page se charge (ou que la page active se recharge), lʼobjet spécifié dans lʼargument on disparaît et le plug-in p_fo renvoie à nouveau la valeur true la première fois quʼil sʼexécute après la fin du chargement de la page.

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2,0

* Nouvelle version (recompilé, taille de code réduite).
* Modification du type de la valeur renvoyée, qui passe d’un entier à une valeur booléenne.

### 1.0

* Version initiale.
