---
title: getValOnce.
description: Empêchez la définition d’une variable Analytics sur la même valeur deux fois dans une ligne.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe : getValOnce

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getValOnce` module externe empêche qu’une variable soit définie plusieurs fois sur la même valeur. Adobe recommande d’utiliser ce module lorsque vous souhaitez dédupliquer des occurrences lorsqu’un visiteur actualise une page ou consulte une page à plusieurs reprises. Ce plug-in n’est pas nécessaire si vous ne vous souciez pas de la mesure Occurrences dans Analysis Workspace.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Si ce n’est déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser getValOnce
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez la section [!UICONTROL Configurer le suivi à l’aide de l’accordéon de code] personnalisé, qui affiche le bouton [!UICONTROL Ouvrir l’éditeur] .
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide `s_gi`). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getValOnce` méthode utilise les arguments suivants :

* **`vtc`**(obligatoire, chaîne) : Variable à vérifier et voir si elle a été définie pour une valeur identique
* **`cn`**(facultatif, chaîne) : Nom du cookie qui contient la valeur à vérifier. Par défaut, la valeur`"s_gvo"`
* **`et`**(facultatif, entier) : Expiration du cookie en jours (ou minutes, selon l’`ep`argument). Valeur par défaut`0`, qui expire à la fin de la session du navigateur.
* **`ep`**(facultatif, chaîne) : Définissez cet argument uniquement si l’`et`argument est également défini. Définissez cet argument sur`"m"`si vous souhaitez que l&#39;`et`argument expire en minutes et non en jours. La valeur par défaut est`"d"`, ce qui définit l’`et`argument en jours.

Si l’ `vtc` argument et la valeur du cookie correspondent, cette méthode renvoie une chaîne vide. Si l’ `vtc` argument et la valeur du cookie ne correspondent pas, la méthode renvoie l’ `vtc` argument sous forme de chaîne.

## Exemples d’appels

### Exemple n° 1

Utilisez cet appel pour empêcher la même valeur d’être transmise à s.campaign plusieurs fois de suite pendant les 30 jours suivants :

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Dans l’appel ci-dessus, le plug-in comparera d’abord la valeur déjà contenue dans le cookie s_campaign avec la valeur provenant de la variable s.campaign actuelle.   Si aucune correspondance n’est établie, le plug-in définit le cookie s_campaign sur la nouvelle valeur provenant de s.campaign, puis renvoie la nouvelle valeur.   Cette comparaison sera effectuée pour les trente prochains jours

### Exemple n° 2

Utilisez cet appel pour empêcher la même valeur d’être définie tout au long de la session :

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Ce code empêche la même valeur d’être transmise à s.eVar2 plusieurs fois de suite au cours de la session d’un utilisateur.  Il ignore également la valeur &quot;m&quot; dans le segment (à la fin de l’appel) puisque le délai d’expiration est défini sur 0.   Le code stocke également la valeur de comparaison dans le cookie s_ev2.

## Historique des versions

### 2.0

* Publication ponctuelle (recompilée, taille de code réduite).

### 1.1

* Ajout de l’option permettant de choisir des minutes ou des jours pour l’expiration via le `t` paramètre.
* Correction de la portée de la `k` variable utilisée pour la limiter au module externe uniquement. Cette modification évite toute interférence avec un autre code de la page.
