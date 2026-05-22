---
description: Data Warehouse offre une fonctionnalité qui vous permet d’extraire une liste d’identifiants visiteur. Ces identifiants ne sont pas des identifiants de cookie, mais des identifiants que vous capturez dans l’une de vos variables de conversion. Bien qu’il existe d’autres façons d’obtenir ces informations, l’exemple suivant est un raccourci pour générer une requête Data Warehouse.
title: Scénario d’utilisation - Extraction d’ID de visiteur
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: 'https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 6%

---

# Scénario d’utilisation - Extraction d’ID de visiteur

Data Warehouse offre une fonctionnalité qui vous permet d’extraire une liste d’identifiants visiteur. Ces identifiants ne sont pas des identifiants de cookie, mais des identifiants que vous capturez dans l’une de vos variables de conversion. Bien qu’il existe d’autres façons d’obtenir ces informations, l’exemple suivant est un raccourci pour générer une requête Data Warehouse.

Supposons, par exemple, que votre entreprise envoie des courriels marketing à des clients et des prospects. Chacun de ces destinataires de messagerie dispose d’un identifiant unique dans votre système de messagerie (par exemple, *`EMAIL Contact ID`*). Vous configurez vos e-mails de sorte que lorsque les contacts reçoivent un e-mail et cliquent sur l’un de ses liens, le visiteur arrive sur votre site web avec un identifiant de campagne et un identifiant de contact E-mail unique. Par exemple, votre lien d’e-mail peut être résolu sur :

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

La définition de ces paramètres dans des variables de conversion (eVars) vous permet de voir les performances de chaque e-mail (via l’ID de campagne) et la fréquence à laquelle chaque destinataire d’e-mail a visité le site (via l’ID de contact E-mail).

Supposons que vous capturiez ces identifiants. La plupart des spécialistes du marketing souhaitent segmenter le comportement de leur site web, puis voir s’ils peuvent commercialiser à nouveau auprès de ceux qui répondent à certains critères. Par exemple, vous pouvez envoyer un e-mail de remarketing à tous les destinataires qui sont arrivés sur votre site à partir de cet e-mail et ont consulté (ou rempli) un formulaire de site web. Pour ce faire, trouvez un moyen d’identifier les ID de contact E-mail de ceux qui remplissent le formulaire spécifique.

Une façon de le faire est d’utiliser un rapport Sous-relation de conversion pour ventiler la valeur d’eVar de l’ID de formulaire par l’eVar de l’ID de contact E-MAIL. Cependant, une fonctionnalité préconfigurée est disponible pour effectuer cette opération à l’aide de Data Warehouse. Cette fonctionnalité vous permet d’identifier l’eVar qui stocke vos ID d’utilisateur uniques (dans ce cas, ID de contact E-mail) et vous permet d’extraire facilement ces ID à l’aide de l’entrepôt de données. Grâce à cette fonctionnalité, vous pouvez créer automatiquement une requête Data Warehouse qui extrait les identifiants visiteur uniques qui vous intéressent.
