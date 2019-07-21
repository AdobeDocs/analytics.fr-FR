---
description: Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.
keywords: Mise en œuvre d’Analytics
seo-description: Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.
seo-title: Effectuer un suivi sur différents types d'implémentation
solution: Analytics
title: Effectuer un suivi sur différents types d'implémentation
topic: Développeur et mise en œuvre
uuid: a 0 a 3229 a -79 a 2-4 dc 2-b 0 be -4 b 8 fac 2 a 3 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Effectuer un suivi sur différents types d'implémentation

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.

Si vous utilisez plusieurs types d’implémentation (des demandes d’image codées en dur et JavaScript, par exemple), assurez-vous que les variables suivantes sont spécifiées et qu’elles correspondent :

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (en cas d’utilisation de SSL)

Si chacune de ces variables ne correspond pas sur les différentes implémentations, les utilisateurs peuvent être suivis en tant que visiteurs distincts. 
