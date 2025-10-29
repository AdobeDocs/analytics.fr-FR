---
title: FAQ sur les sources de données
description: Questions fréquentes sur les sources de données.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 7%

---

# FAQ sur les sources de données

Questions fréquentes sur les sources de données.

+++Quel est le coût d’utilisation des sources de données ?
Les sources de données n’entraînent aucun frais et ne sont pas prises en compte dans l’utilisation des appels au serveur. [sources de données à traitement complet](full-processing-eol.md) comptabilisées dans les appels au serveur avant leur suppression.
+++

+++Comment les sources de données affectent-elles l’attribution et l’expiration des eVars ?
Les sources de données n’ont aucun type d’attribution ou d’expiration.
+++

+++Comment les sources de données affectent-elles les mesures telles que les pages vues, les visites ou les visiteurs uniques ?
Les données chargées par le biais des sources de données n’ont aucune incidence sur [Pages vues](/help/components/metrics/page-views.md), [Visites](/help/components/metrics/visits.md) ou [Visiteurs uniques](/help/components/metrics/unique-visitors.md). La seule mesure par défaut affectée est [Occurrences](/help/components/metrics/occurrences.md).
+++

+++Les données chargées par le biais de sources de données sont-elles traitées de manière supplémentaire, comme les règles de traitement ?
Non. Données chargées par le biais des sources de données :

* Ne passe pas par [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
* Ne passe pas par les [règles de traitement des canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)
* ne passe pas par les [ règles VISTA ](/help/technotes/vista.md)
+++

+++Puis-je supprimer des données importées à l’aide de sources de données ?
Oui. Vous pouvez supprimer ces données à l’aide de l’[API Data Repair](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/?lang=fr). Adobe recommande vivement de charger les données des sources de données dans une suite de rapports de test avant de les charger dans une suite de rapports de production afin de réduire la nécessité de supprimer les données.
+++

+++Combien de données puis-je importer en même temps ? 
Le traitement s’interrompt au-delà de 50 Mo et ne reprend qu’une fois que le total est inférieur à 50 Mo. Assurez-vous que la taille totale de tous les fichiers sur le site FTP est inférieure à 50 Mo.
+++

+++Que se passe-t-il si je transmets des valeurs négatives dans les rapports via les sources de données ?
La valeur est diminuée en conséquence. Certaines organisations utilisent des valeurs de source de données négatives pour tenter de corriger les données. Les valeurs négatives de la source de données peuvent avoir une incidence sur les rapports de manière potentiellement indésirable ou inattendue. Adobe recommande de n’utiliser les valeurs négatives dans les sources de données qu’en dernier recours.
+++

+++Les extensions de fichiers respectent-elles la casse ?
Oui. Les fichiers dont l’extension est `.TXT` ou `.FIN` ne sont pas traités. Assurez-vous que les extensions de fichier sont toutes en minuscules.
+++

+++Combien de colonnes puis-je ajouter à un fichier de source de données ?
Vous pouvez inclure autant de colonnes que vous le souhaitez dans un fichier de source de données, si toutes les colonnes sont valides. Voir [Format de fichier](file-format.md) pour obtenir une liste des noms de variable/colonne valides.
+++

+++Puis-je utiliser des sources de données sans utiliser l’emplacement FTP fourni par Adobe ?
Vous pouvez utiliser l’[API Data Sources](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/) qui permet d’envoyer directement des appels API à Adobe. Ces appels d’API incluent une méthode `UploadData`, qui vous permet d’envoyer des données par le biais d’une payload d’objet JSON.
+++
