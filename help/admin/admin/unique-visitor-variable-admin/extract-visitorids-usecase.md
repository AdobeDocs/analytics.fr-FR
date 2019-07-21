---
description: Data Warehouse propose une fonctionnalité qui vous permet d’extraire une liste d’ID de visiteur. Il ne s’agit pas d’ID de cookie, mais des ID que vous capturez dans l’une de vos variables de conversion. Bien qu’il soit possible d’obtenir ces informations par d’autres moyens, l’exemple suivant permet de générer plus rapidement une demande Data Warehouse.
seo-description: Data Warehouse propose une fonctionnalité qui vous permet d’extraire une liste d’ID de visiteur. Il ne s’agit pas d’ID de cookie, mais des ID que vous capturez dans l’une de vos variables de conversion. Bien qu’il soit possible d’obtenir ces informations par d’autres moyens, l’exemple suivant permet de générer plus rapidement une demande Data Warehouse.
seo-title: Scénario d’utilisation - Extraction d’ID de visiteur
solution: Analytics
title: Scénario d’utilisation - Extraction d’ID de visiteur
topic: Outils d’administration
uuid: ed 228334-619 c -43 d 7-b 781-a 18 af 73 b 00 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Scénario d’utilisation - Extraction d’ID de visiteur

Data Warehouse propose une fonctionnalité qui vous permet d’extraire une liste d’ID de visiteur. Il ne s’agit pas d’ID de cookie, mais des ID que vous capturez dans l’une de vos variables de conversion. Bien qu’il soit possible d’obtenir ces informations par d’autres moyens, l’exemple suivant permet de générer plus rapidement une demande Data Warehouse.

Supposons, par exemple, que votre entreprise envoie des courriels marketing à des clients et des prospects. Un identifiant unique est affecté à chacun des destinataires dans votre système de messagerie (comme par exemple *`EMAIL Contact ID`*). Vous configurez vos courriels de telle sorte que lorsque des contacts les reçoivent et cliquent sur l’un des liens qu’ils contiennent, le visiteur arrive sur votre site web avec un ID de campagne et un ID Contact courriel unique. Votre lien de courriel peut, par exemple, pointer vers :

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Définir ces ID dans des variables de conversion (eVars) vous permet de connaître les performances de chaque courriel (par le biais de l’ID de campagne) et la fréquence des visites de chaque destinataire du courriel (par le biais de l’ID Contact courriel).

Supposons que vous capturiez ces ID. La plupart des spécialistes du marketing souhaitent segmenter le comportement sur leur site web et déterminer s’il est possible de relancer les visiteurs qui répondent à certains critères. Ainsi, vous pouvez envoyer un courriel de relance à tous les destinataires qui ont visité votre site à partir du courriel en question et ont visualisé (ou rempli) un formulaire du site web. Pour ce faire, trouvez le moyen d’identifier les ID Contact courriel des internautes qui ont rempli le formulaire.

Une méthode consiste à utiliser un rapport Sous-relation de conversion afin de ventiler la valeur d’eVar ID de formulaire en fonction de l’eVar ID Contact courriel. Une fonctionnalité prédéfinie vous permet toutefois de procéder de la sorte à l’aide de Data Warehouse. Vous pouvez ainsi indiquer l’eVar qui stocke vos ID utilisateur uniques (ID Contact courriel, dans le cas présent) et extraire aisément ces ID à l’aide de Data Warehouse. Cette fonctionnalité vous permet de créer automatiquement une demande d’entrepôt de données qui extrait les ID de visiteurs uniques qui vous intéressent.
