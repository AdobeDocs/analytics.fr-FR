---
description: Réponse à la question « Où l’utilisateur se rend-il sur mon site après y avoir été redirigé à partir d’une campagne ? »
keywords: Mise en œuvre d’Analytics
seo-description: Réponse à la question « Où l’utilisateur se rend-il sur mon site après y avoir été redirigé à partir d’une campagne ? »
seo-title: Cheminement par code de suivi ou campagne
solution: Analytics
title: Cheminement par code de suivi ou campagne
topic: Développeur et mise en œuvre
uuid: eb 6 e 3484-1 b 40-4 ec 6-8017-ac 1003 cdf 636
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cheminement par code de suivi ou campagne

Réponse à la question « Où l’utilisateur se rend-il sur mon site après y avoir été redirigé à partir d’une campagne ? »

Pour répondre à cette question, vous devez mettre de côté une [!UICONTROL sprop] à utiliser pour ce rapport. Vous devez ensuite structurer les données à renseigner dans la prop, de telle sorte que cela ait du sens une fois le cheminement activé.

Supposons, par exemple, que vous soyez sur le point d’utiliser [!UICONTROL prop1] comme prop de cheminement de campagne. Vous souhaitez, à présent, renseigner dans cette [!UICONTROL sprop] la même valeur que celle indiquée dans la variable [!UICONTROL pageName]. Reportez-vous à l’exemple ci-dessous :

```js
s.prop1=s.pageName;
```

Vous devez procéder de la sorte sur toutes les pages, sauf si l’utilisateur a cliqué sur la page en provenance d’une campagne. Si tel est le cas, et si l’utilisateur se trouve sur la page d’entrée de la campagne, vous pouvez renseigner dans la prop une concaténation de la campagne et du [!UICONTROL pageName]. Reportez-vous à l’exemple ci-dessous :

```js
 s.prop1=s.campaign + ‘ : ’ + s.pageName;
```

Si la campagne sur laquelle il a cliqué se nomme, par exemple, « banner1234 », et que la page sur laquelle il arrive s’intitule « Home Page », la valeur de cette prop sera « banner1234 : Home Page ». Indiquez le [!UICONTROL pageName] dans la prop pour chaque page successive, comme illustré ci-dessus.

Lorsqu’un utilisateur clique sur cette campagne et consulte, au total, quatre pages au cours de la visite, vous obtenez les valeurs suivantes dans la sprop, dans l’ordre suivant :

```js
“banner1234 : Home Page” > “Page 2” > “Page 3” > “Page 4”
```

Une fois nos données capturées dans [!UICONTROL prop1] en suivant cette procédure et le cheminement activé sur cette prop, vous pouvez consulter l’un des rapports disponibles pour comprendre le cheminement des utilisateurs sur le site après avoir cliqué sur une page en provenance d’une campagne.

Vous pouvez indiquer la page de début du rapport de cheminement. Dans le cas présent, vous avez sélectionné « banner1234 : Home Page », car vous souhaitez connaître la destination des utilisateurs en provenance de la campagne « banner 1234 ». Ce rapport n’est qu’un exemple parmi les nombreux rapports de cheminement disponibles.
