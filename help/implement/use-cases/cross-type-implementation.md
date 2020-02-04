---
title: Suivi sur différents types de mises en œuvre
description: Utilisez différents types d’implémentation et effectuez un suivi transparent des visiteurs entre eux.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Suivi sur différents types de mises en œuvre

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.

Si vous utilisez plusieurs types d’implémentation (des demandes d’image codées en dur et JavaScript, par exemple), assurez-vous que les variables suivantes sont spécifiées et qu’elles correspondent :

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*(en cas d’utilisation de SSL)

Si chacune de ces variables ne correspond pas sur les différentes implémentations, les utilisateurs peuvent être suivis en tant que visiteurs distincts.
