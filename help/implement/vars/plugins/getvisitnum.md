---
title: getVisitNum
description: Assurez le suivi du nombre de visites actuelles d’un visiteur.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe : getVisitNum

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getVisitNum` module externe renvoie le nombre de visites pour tous les visiteurs qui se rendent sur le site dans le nombre de jours souhaité. Analysis Workspace propose une dimension &quot;Nombre de visites&quot; qui offre des fonctionnalités similaires. Adobe recommande d’utiliser ce module externe si vous souhaitez avoir un meilleur contrôle sur la manière dont le nombre de visites est incrémenté. Ce plug-in n’est pas nécessaire si la dimension &quot;Nombre de visites&quot; intégrée dans Analysis Workspace est suffisante pour répondre à vos besoins de création de rapports.

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
   * Type d&#39;action : Initialiser getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getVisitNum` méthode utilise les arguments suivants :

* **`rp`**(facultatif, entier OU chaîne) : Nombre de jours avant la réinitialisation du compteur du nombre de visites.  La valeur par défaut est`365`définie lorsqu’elle n’est pas définie.
   * Lorsque cet argument est `"w"`utilisé, le compteur se réinitialise à la fin de la semaine (ce samedi à 23h59)
   * Lorsque cet argument est `"m"`, le compteur est réinitialisé à la fin du mois (dernier jour du mois)
   * Lorsque cet argument est `"y"`utilisé, le compteur se réinitialise à la fin de l’année (31 décembre)
* **`erp`**(facultatif, booléen) : Lorsque l’`rp`argument est un nombre, cet argument détermine si l’expiration du nombre de visites doit être prolongée. S’il est défini sur`true`, les accès suivants à votre site réinitialisent le compteur du nombre de visites. S’il est défini sur`false`, les accès suivants à votre site ne s’étendent pas lorsque le compteur du nombre de visites est réinitialisé. Par défaut,`true`. Cet argument n&#39;est pas valide lorsque l&#39;`rp`argument est une chaîne.

Le nombre de visites augmente chaque fois que le visiteur revient sur votre site après 30 minutes d’inactivité. L’appel de cette méthode renvoie un entier représentant le nombre de visites actuel du visiteur.

Ce plug-in définit un cookie propriétaire appelé `"s_vnc[LENGTH]"` &quot;where&quot; `[LENGTH]` est la valeur transmise à l’ `rp` argument. Par exemple, `"s_vncw"`, `"s_vncm"`ou `"s_vnc365"`. La valeur du cookie est une combinaison d’un horodatage Unix qui représente le moment où le compteur de visites est réinitialisé, comme la fin de la semaine, la fin du mois ou après 365 jours d’inactivité. Il contient également le nombre de visites actuel. Ce plug-in définit un autre cookie nommé `"s_ivc"` qui est défini sur `true` et expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple n° 1

Pour un visiteur qui ne s’est pas rendu sur le site au cours des 365 derniers jours, le code suivant définit s.prop1 sur la valeur 1 :

```js
s.prop1=s.getVisitNum();
```

### Exemple n° 2

Pour un visiteur qui revient sur le site dans les 364 jours suivant sa première visite, le code suivant définit s.prop1 sur 2 :

```js
s.prop1=s.getVisitNum(365);
```

Si ce visiteur revient sur le site dans les 364 jours suivant sa deuxième visite, le code suivant définit s.prop1 sur 3 :

```js
s.prop1=s.getVisitNum(365);
```

### Exemple n° 3

Pour un visiteur qui revient sur le site dans les 179 jours suivant sa première visite, le code suivant définit s.prop1 sur 2 :

```js
s.prop1=s.getVisitNum(180,false);
```

Cependant, si ce visiteur revient sur le site 1 ou plus de jours après sa deuxième visite, le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum(180,false);
```

Lorsque le second argument de l’appel est égal à false, la routine qui détermine le moment où le nombre de visites doit être &quot;réinitialisé&quot; sur 1 le fait que &quot;x&quot; nombre de jours (dans cet exemple, 365 jours) après la première visite du visiteur sur le site.

Lorsque le second argument est égal à true (ou n’est pas du tout défini), le plug-in réinitialise le nombre de visites à 1 uniquement après le nombre de jours &quot;x&quot; (365 jours) d’inactivité du visiteur dans cet exemple.

### Exemple n° 4

Pour tous les visiteurs qui viennent sur le site pour la première fois au cours de la semaine en cours - à partir du dimanche - le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("w");
```

### Exemple n° 5

Pour tous les visiteurs qui viennent sur le site pour la première fois au cours du mois en cours - à compter du premier jour de chaque mois - le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("m");
```

N’oubliez pas que le module externe getVisitNum ne prend pas en compte les calendriers de vente au détail (c’est-à-dire 4-5-4, 4-4-5, etc.).

### Exemple n° 6

Pour tous les visiteurs qui se rendent sur le site pour la première fois au cours de l’année en cours - à compter du 1er janvier - le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("y");
```

### Exemple n° 7

Si vous souhaitez effectuer le suivi du nombre de visites d’un visiteur pour la semaine, du nombre de visites d’un visiteur pour le mois et du nombre de visites d’un visiteur pour l’année (toutes dans des variables Analytics différentes), utilisez un code qui ressemble à ce qui suit :

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

Dans ce cas, le plug-in crée trois cookies différents - un pour chacune des différentes périodes - pour suivre le nombre de visites individuelles par période.

## Historique des versions

### 4.11 (30 septembre 2019)

* Correction d’un problème en raison duquel l’ `erp` argument était explicitement défini sur `false`.

### 4.1 (21 mai 2018)

* Mise à jour du `endOfDatePeriod` module externe vers la version 1.1.

### 4.0 (17 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).
* Suppression des arguments de cookie lorsque le module externe génère désormais dynamiquement des cookies en fonction de l’ `rp` argument)

### 3.0 (5 juin 2016)

* Révision complète
* Combinez toutes les solutions précédentes disponibles dans différentes versions du `getVisitNum` module externe.
