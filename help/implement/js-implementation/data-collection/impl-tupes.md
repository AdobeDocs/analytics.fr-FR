---
description: Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.
keywords: Analytics Implementation
title: Suivi sur différents types de mises en œuvre
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suivi sur différents types de mises en œuvre

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.

Si vous utilisez plusieurs types d’implémentation (des demandes d’image codées en dur et JavaScript, par exemple), assurez-vous que les variables suivantes sont spécifiées et qu’elles correspondent :

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (en cas d’utilisation de SSL)

Si chacune de ces variables ne correspond pas sur les différentes implémentations, les utilisateurs peuvent être suivis en tant que visiteurs distincts.
