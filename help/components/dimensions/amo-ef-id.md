---
title: AMO EF ID
description: Identifiant d’Adobe Media Optimizer EF, utilisé dans les intégrations Adobe Advertising.
feature: Dimensions
exl-id: 129b0235-9b00-4d75-8b02-0443dfdef091
TQID: 'https://experienceleague.adobe.com/gye9CwGtFwPppmrTbpB5CErZjIdKeAtSPr6VPUtPod4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 4%

---

# AMO EF ID

L’**[!UICONTROL AMO EF ID]** est un identifiant de clic publicitaire utilisé dans les intégrations d’Adobe Advertising. Il s’agit d’un jeton unique utilisé par Adobe Advertising pour associer l’activité à une exposition publicitaire ou à un clic en ligne au niveau du visiteur. La dimension est automatiquement créée lors de l’activation de l’intégration [Analytics pour Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview).

## Renseignement de cette dimension avec des données

Cette dimension collecte ses valeurs de plusieurs manières :

* Pour le trafic de clics publicitaires, les données sont collectées à partir du paramètre de chaîne de requête `ef_id` dans l’[URL de la page](page-url.md), généralement sur la page par laquelle le trafic piloté par les annonces accède au site.
* Le trafic de clics publicitaires peut également être capturé lorsque l’URL ne contient pas de codes de suivi, mais que le JavaScript Adobe Advertising détecte un clic au cours des deux minutes précédentes.
* Pour le trafic d’affichage publicitaire pris en charge, Adobe Advertising complète les valeurs sur le serveur principal à l’aide d’un ID supplémentaire (`SDID`).

>[!NOTE]
>
>Les identifiants d’éléments d’expérience sont sensibles à la casse. Si votre implémentation force le suivi des URL à passer en minuscules, Adobe Advertising ne reconnaît pas l’identifiant de l’EF.

## Éléments de dimension

Les éléments Dimension incluent les identifiants de clics publicitaires générés par les réseaux publicitaires pris en charge. Le format de la chaîne dépend du réseau et du canal qui l’ont générée.

### Google Ads search ads

```text
{gclid}:G:{s}
```

* **`gclid`** : ID de clic Google (GCLID).
* **`s`** : type de réseau (`"s"` pour la recherche).

### Annonces de recherche Microsoft Advertising

```text
{msclkid}:G:{s}
```

* **`msclkid`** : ID de clic Microsoft (MSCLKID).
* **`s`** : type de réseau (`"s"` pour la recherche).

### Affichage des annonces et des annonces de recherche sur d’autres moteurs de recherche

```text
{amovid}:{ts}:{channel}
```

* **`amovid`** : identifiant visiteur Adobe Advertising, également appelé identifiant surfer.
* **`ts`** : date et heure générées par Adobe Advertising.
* **`channel`** : type de canal responsable du clic ou de l’exposition :
   * **`d`** : clic sur une publicité display DSP (clic publicitaire sur l’affichage).
   * **`i`** : impression sur une publicité display DSP (affichage publicitaire).
   * **`s`** : clic sur une publicité de recherche (clic publicitaire de recherche).

### Exemples

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
