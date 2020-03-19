---
title: addProductEvar
description: Ajoute des eVars de marchandisage à la variable products.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : addProductEvar

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `addProductEvar` module externe vous permet d’ajouter facilement une eVar de marchandisage Adobe Analytics qui utilise la syntaxe du produit à la variable products sans vous soucier de savoir si le contenu existant de la variable products sera modifié/déplacé/supprimé. Adobe recommande d’utiliser ce module externe si vous souhaitez ajouter facilement des eVars de marchandisage de syntaxe de produit à la [`products`](../page-vars/products.md) variable. Vous n’avez pas besoin d’utiliser le `addProductEvar` module externe si vous n’utilisez pas d’eVars de marchandisage avec la syntaxe du produit.

> [!NOTE] Ce module externe ne remplace pas les eVars qui existent déjà dans une entrée de produit. Il ajoute uniquement les valeurs que vous avez définies à l’aide de ce module externe. Soyez prudent lorsque vous ajoutez des eVars qui existent déjà pour ce produit.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe   une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l&#39; [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Catalog] bouton
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si vous ne l’avez pas déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   *  : Core - Bibliothèque chargée (Haut de la page)
1. Ajouter une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser addProductEvar
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous l’extension Adobe Analytics.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvar v1.0 */
s.addProductEvar=function(en,ev,ap){if("string"===typeof en&&"string"===typeof ev&&""!==ev)if(ap=ap||!1,this.products){var e=this.products.split(","),f=e.length;ap=ap?0:f-1;for(var a;ap<f;ap++)a=e[ap].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+en+"="+ev:a[5]?a[5]=en+"="+ev:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=en+"="+ev),e[ap]=a.join(";");this.products=e.join(",")}else this.products=";;;;;"+en+"="+ev};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

Le `addProductEvar` module externe utilise les arguments suivants :

* **`en`** (obligatoire, chaîne) : eVar à ajouter à la dernière entrée actuellement contenue dans la variable products. Si la variable products est vide, le plug-in crée une entrée de produit &quot;vide&quot; avec la valeur eVar attachée à la fin de l’entrée.
* **`ev`** (obligatoire, chaîne) : Valeur affectée à l’eVar.
* **`ap`** (facultatif, booléen) : Si la variable products contient actuellement plusieurs entrées de produit, la valeur true (ou 1) ajoute l’eVar à **toutes les** entrées de produit.  La valeur par défaut est false (ou 0), ce qui ajoute l’eVar à la **dernière** entrée contenue dans la variable products.

Le `addProductEvar` module externe ne renvoie rien. Il ajoute plutôt l’eVar (et la valeur eVar) spécifiée dans l’ `en` argument et `ev` à la `products` variable.

## Exemples

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium");
s.addProductEvar("eVar24", "women");
s.addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium", true);
s.addProductEvar("eVar24", "women", true);
s.addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
s.addProductEvar("eVar1", "blue");
```

## Historique des versions

### 1.0 (7 octobre 2019)

* Version initiale.
