---
description: Le type de suivi détermine la manière dont l’implémentation d’Adobe Analytics suit les données de votre moteur de recherche. Ce type de suivi est une étape obligatoire pour compléter correctement les données Adobe Analytics avec les données du moteur de recherche.
title: Type de tracking
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 29%

---

# Type de tracking

Le type de suivi détermine la manière dont l’implémentation d’Adobe Analytics suit les données de votre moteur de recherche. Ce type de suivi est une étape obligatoire pour compléter correctement les données Adobe Analytics avec les données du moteur de recherche.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Deux modes de suivi sont pris en charge : [!UICONTROL Auto] et [!UICONTROL Manuel].

## [!UICONTROL Suivi automatique] {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

Le suivi [!UICONTROL automatique] permet au moteur Advertising Cloud de décider comment les données du moteur de recherche doivent être traitées. Le suivi automatique est l’approche la plus simple, mais peut ne pas aboutir au jeu de données le mieux intégré.

Par conséquent, vous devez cocher une case d’accusé de réception lorsque vous sélectionnez **[!UICONTROL Auto]** avant de pouvoir enregistrer le paramètre de compte.

Notez que pour configurer un compte de moteur de recherche avec le type **[!UICONTROL Auto]**, vous devez effectuer les actions suivantes :

* Le paramètre et la valeur `s_kwcid` sont ajoutés aux modèles de suivi de compte ou aux URL de page de destination dans le compte en cours d’ajout. Ce paramètre et cette valeur sont insérés à la fin de l’URL. Une action supplémentaire peut être requise de votre part si votre serveur web nécessite une certaine paire de `key=value` à la fin de l’URL. Ou une mise à jour pour prendre en charge toute nouvelle paire de `key=value` dans l’URL. Il est de votre responsabilité de vous assurer que les paramètres d’URL ajoutés persistent correctement sur la page de destination finale.
* De plus, les mots-clés peuvent être insérés dans l’URL d’entrée avec la valeur `s_kwcid`. S’ils contiennent des caractères spéciaux ou des symboles, veuillez vérifier que votre serveur web prend en charge ces caractères. Par exemple, un caractère spécial commun est `+`, qui est utilisé dans les mots-clés « Modification de la correspondance large ».

>[!IMPORTANT]
>
>Découvrez si vous devez ajouter ou non le paramètre `s_kwcid` à votre [politique de sécurité du contenu](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Suivi manuel {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Le suivi manuel vous permet de spécifier comment le processus d’intégration des données Advertising Analytics doit traiter les données du moteur de recherche.

### Ajout d’un suivi manuel au compte Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La chaîne qui doit être ajoutée au compte Google est affichée ci-dessous. Vous devez ajouter la chaîne à tous vos modèles de suivi utilisés dans l’ensemble de vos comptes.

>[!IMPORTANT]
>
>La valeur *`<Advertising Analytics ID>`* (en **gras** ci-dessous) est générique et **doit être remplacée par une chaîne spécifique à votre ID de compte**. Vous pouvez obtenir la chaîne d’identifiant de compte spécifique à partir de l’écran du compte sous la section [!UICONTROL Tracking].

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

Pour vous assurer que la chaîne persiste tout au long de la redirection vers l’URL de la page de destination finale, vous devez coder suffisamment la chaîne :

* si l’URL passe par une redirection, et
* n’utilise pas de valeur « unescapedlpurl ».


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Ajout d’un suivi manuel au compte Microsoft Advertising {#section_094F8ACA493C4D65B1F54A695558EBF2}

La chaîne qui doit être ajoutée à votre compte Microsoft Advertising est affichée ci-dessous. Vous devez ajouter la chaîne à tous les suffixes d’URL finaux utilisés dans l’ensemble de vos comptes.

>[!IMPORTANT]
>
>La valeur _`<Advertising Analytics ID>`_(en **gras**&#x200B;ci-dessous) est générique et **doit être remplacée par une chaîne spécifique à votre ID de compte**. Vous pouvez obtenir votre chaîne d’identifiant de compte spécifique à partir de l’écran du compte sous la section « Tracking ».

**Chaîne de suivi pour les campagnes :**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Ajouter des paramètres de code de suivi](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

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

Pour vous assurer que la chaîne persiste tout au long de la redirection vers l’URL de la page de destination finale, vous devez coder suffisamment la chaîne :

* si l’URL passe par une redirection, et
* n’utilise pas de valeur « unescapedlpurl ».

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
