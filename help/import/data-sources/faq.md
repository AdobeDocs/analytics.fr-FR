---
title: FAQ sur les sources de données
description: Questions fréquentes sur les sources de données.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 5%

---

# FAQ sur les sources de données

Questions fréquentes sur les sources de données.

+++Quel est le coût de l’utilisation des sources de données ?
Les sources de données n’engendrent aucune charge et ne comptent pas non plus pour l’utilisation des appels au serveur. [Sources de données à traitement complet](full-processing-eol.md) comptés dans les appels au serveur avant leur retraite.
+++

+++Comment les sources de données affectent-elles l’attribution et l’expiration des eVars ?
Si un transactionID correspond entre une source de données et un accès en ligne, les valeurs de l’eVar associées assument la même attribution et la même expiration que si elles étaient définies sur l’accès en ligne.

Toutes les autres données transférées par le biais de sources de données n’ont aucun type d’attribution ou d’expiration.
+++

+++Comment les sources de données affectent-elles les mesures par défaut, telles que les pages vues, les visites ou les visiteurs uniques ?
Les données transférées au moyen des sources de données n’ont aucune incidence [Pages vues](/help/components/metrics/page-views.md), [Visites](/help/components/metrics/visits.md)ou [Visiteurs uniques](/help/components/metrics/unique-visitors.md) de quelque manière que ce soit. La seule mesure par défaut qu’ils affectent inclut [Occurrences](/help/components/metrics/occurrences.md).
+++

+++Puis-je supprimer des données importées à l’aide de sources de données ?

**Non.** Les données transférées dans les rapports à l’aide de sources de données sont **permanent**. Il ne peut pas être supprimé, même par Adobe, une fois qu’il a été importé. Adobe recommande vivement de transférer les données de sources de données dans une suite de rapports de test avant de les transférer dans une suite de rapports de production.
+++

+++Combien de données puis-je importer à la fois ?

Le traitement s’interrompt au-delà de 50 Mo et ne reprend qu’une fois que le total est inférieur à 50 Mo. Assurez-vous que la taille totale de tous les fichiers du site FTP est inférieure à 50 Mo.
+++

+++Que se passe-t-il si je transmets des valeurs négatives dans les rapports par le biais de sources de données ?

La valeur est diminuée en conséquence. Certaines organisations utilisent des valeurs de source de données négatives pour tenter de corriger les données. Les valeurs de source de données négatives peuvent avoir un impact sur les rapports de manière potentiellement indésirable ou inattendue. Adobe recommande d’utiliser des sources de données négatives uniquement en dernier recours.
+++

+++Les extensions de fichier sont-elles sensibles à la casse ?
Oui. Fichiers avec une extension de `.TXT` ou `.FIN` ne sont pas traitées. Assurez-vous que les extensions de fichier sont toutes en minuscules.
+++

+++Combien de colonnes puis-je ajouter à un fichier de source de données ?
Vous pouvez inclure autant de colonnes que vous le souhaitez dans un fichier de source de données s’il s’agit de colonnes valides. Voir [Format du fichier](file-format.md) pour une liste de noms de variables/colonnes valides.
+++

+++Puis-je utiliser des sources de données sans utiliser l’emplacement FTP fourni par l’Adobe ?
Vous pouvez utiliser la variable [API des sources de données](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), qui vous permet d’envoyer des appels d’API directement à Adobe. Ces appels API incluent une `UploadData` qui vous permet d’envoyer des données par une charge utile d’objet JSON.
+++
