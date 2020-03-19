---
title: Suivi sur différents types de mises en œuvre
description: Utilisez différents types de mise en œuvre et effectuez un suivi transparent des visiteurs entre eux.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Suivi sur différents types de mises en œuvre

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et de mise en œuvre. N’apportez des modifications à votre mise en œuvre que si vous êtes parfaitement conscient des conséquences. Si des changements de mise en œuvre s’avèrent nécessaires, contactez le responsable de compte de votre organisation.

Si vous utilisez plusieurs types de mise en œuvre (des demandes d’image codées en dur et JavaScript, par exemple), assurez-vous que les variables suivantes sont spécifiées et qu’elles correspondent :

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (en cas d’utilisation de SSL)

Si chacune de ces variables ne correspond pas sur les différentes mises en œuvre, les utilisateurs peuvent être suivis en tant que visiteurs distincts.
