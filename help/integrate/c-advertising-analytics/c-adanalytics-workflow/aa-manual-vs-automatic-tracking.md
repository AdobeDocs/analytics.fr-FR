---
description: Le type de suivi détermine la manière dont l’implémentation d’Adobe Analytics suit les données de votre moteur de recherche. Ce type de suivi est une étape requise pour augmenter correctement les données Adobe Analytics avec les données du moteur de recherche.
title: Type de suivi
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 243da53fda562c856d95db0f6d13b7ee1a9adae5
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 32%

---

# Type de suivi

Le type de suivi détermine la manière dont l’implémentation d’Adobe Analytics suit les données de votre moteur de recherche. Ce type de suivi est une étape requise pour augmenter correctement les données Adobe Analytics avec les données du moteur de recherche.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Deux modes de suivi sont pris en charge : [!UICONTROL Auto] et [!UICONTROL Manuel].

## [!UICONTROL Auto] Tracking {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL Auto] tracking permet au moteur Advertising Cloud de décider comment gérer les données du moteur de recherche. Le suivi automatique est l’approche la plus simple, mais il se peut qu’elle ne produise pas le meilleur jeu de données intégré.

Par conséquent, vous devez cocher une case de confirmation lorsque vous sélectionnez **[!UICONTROL Auto]** avant de pouvoir enregistrer le paramètre du compte.

Pour configurer un compte de moteur de recherche avec **[!UICONTROL Auto]** , vous êtes responsable des actions suivantes :

* La variable `s_kwcid` Les paramètres et valeurs sont ajoutés aux modèles de suivi de compte ou aux URL de page d’entrée dans le compte ajouté. Ce paramètre et cette valeur sont insérés à la fin de l’URL. Une action supplémentaire peut être requise de votre part si votre serveur web requiert une certaine `key=value` à la fin de l’URL. Ou une mise à jour pour prendre en charge toute nouvelle `key=value` dans l’URL. Il vous appartient de vous assurer que les paramètres d’URL ajoutés demeurent correctement à la dernière page d’entrée.
* De plus, les mots-clés peuvent être insérés dans l’URL d’entrée avec la valeur `s_kwcid`. S’ils contiennent des caractères spéciaux ou des symboles, veuillez vérifier que votre serveur web prend en charge ces caractères. Par exemple, un caractère spécial commun est `+`, qui est utilisé dans les mots-clés &quot;En correspondance large modifiée&quot;.

>[!IMPORTANT]
>
>Découvrez si vous devez ajouter ou non le paramètre `s_kwcid` à votre [politique de sécurité du contenu](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Suivi manuel {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Le suivi manuel vous permet de spécifier comment le processus d’intégration des données Advertising Analytics doit traiter les données du moteur de recherche.

### Ajout d’un suivi manuel à un compte Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La chaîne qui doit être ajoutée au compte Google est affichée ci-dessous. Vous devez ajouter la chaîne à tous vos modèles de suivi utilisés dans l’ensemble de vos comptes.

>[!IMPORTANT]
>
>La valeur *`<Advertising Analytics ID>`* (en **gras** ci-dessous) est générique et **doit être remplacée par une chaîne spécifique à votre ID de compte**. Vous pouvez obtenir votre chaîne d’ID de compte spécifique à partir de l’écran du compte sous la balise [!UICONTROL Tracking] .

**Chaîne de suivi pour les campagnes :**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

Exemples de codes de suivi dans divers formats de modèles de suivi :

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`avec un paramètre d’URL supplémentaire**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Tiers (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Tiers (DoubleClick)`{lpurl}`**

Pour vous assurer que la chaîne persiste par le biais de la redirection vers l’URL de la dernière page d’entrée, vous devez encoder suffisamment la chaîne :

* si l’URL passe par une redirection, et
* n’utilise pas de valeur &quot;unescapedlpurl&quot;.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Ajout d’un suivi manuel à un compte Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

La chaîne qui doit être ajoutée au compte Bing est affichée ci-dessous. Vous devez ajouter la chaîne à tous les suffixes d’URL finaux utilisés dans l’ensemble de vos comptes.

>[!IMPORTANT]
>
>La valeur _`<Advertising Analytics ID>`_(en **gras**ci-dessous) est générique et **doit être remplacée par une chaîne spécifique à votre ID de compte**. Vous pouvez obtenir la chaîne d’ID de compte spécifique à partir de l’écran du compte sous la section &quot;Suivi&quot;.

**Chaîne de suivi pour les campagnes :**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Bing](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

Exemples de codes de suivi dans divers formats de suffixes d’URL finaux :

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`avec un paramètre d’URL supplémentaire**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Tiers (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Tiers (DoubleClick)`{lpurl}`**

Pour vous assurer que la chaîne persiste par le biais de la redirection vers l’URL de la dernière page d’entrée, vous devez encoder suffisamment la chaîne :

* si l’URL passe par une redirection, et
* n’utilise pas de valeur &quot;unescapedlpurl&quot;.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
