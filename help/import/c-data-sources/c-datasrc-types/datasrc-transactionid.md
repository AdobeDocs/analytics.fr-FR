---
title: Sources de données d’ID de transaction
description: Découvrez le processus général d’utilisation des sources de données d’ID de transaction.
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

---


# Sources de données d’ID de transaction

Les sources de données d’ID de transaction vous permettent non seulement d’afficher les données en ligne et hors ligne côte à côte, mais également de lier les données ensemble. Elle nécessite l’utilisation de la [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable dans votre implémentation Analytics.

Lorsque vous envoyez un accès en ligne contenant une `transactionID` valeur, Adobe prend un &quot;instantané&quot; de toutes les variables définies ou conservées à ce moment-là. Si un ID de transaction correspondant transféré via la fonctionnalité Sources de données est trouvé, les données hors ligne et en ligne sont liées. Peu importe quelle source de données est vue en premier.

## Flux global de travaux des sources de données d’ID de transaction

Utilisez le processus générique suivant pour commencer à utiliser les sources de données d’ID de transaction :

1. Créez une source de données (catégorie &quot;Générique&quot; et type &quot;Source de données générique (ID de transaction)&quot;).
1. Suivez l’assistant de configuration du flux de données pour obtenir un emplacement FTP pour télécharger des données et un fichier de modèle de sources de données.
1. Mettez à jour votre implémentation pour inclure la `transactionID` variable.
1. Téléchargez un fichier de sources de données sur le site FTP avec un `.fin` fichier.
