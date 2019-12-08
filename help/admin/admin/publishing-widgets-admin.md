---
description: Un widget de publication est un conteneur qui vous permet d’intégrer des rapports marketing (signets et tableaux de bord) dans une page web. Les personnes de votre société qui n’ont pas accès aux rapports marketing peuvent visualiser des données pertinentes.
title: Widget de publication
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Widget de publication

Un widget de publication est un conteneur qui vous permet d’intégrer des rapports Analytics (signets et tableaux de bord) dans une page web. Les personnes de votre société qui n’ont pas accès aux rapports Analytics peuvent consulter des données pertinentes.

Vous pouvez, par exemple, mettre à la disposition des cadres de la société un tableau de bord leur permettant de consulter le nombre de visiteurs, de visiteurs uniques, etc.

> [!CAUTION] Aucune authentification n’est requise pour afficher les données publiées par le biais du widget de publication.Vous devez donc tenir compte du fait que les données publiées ne sont pas plus protégées que celles envoyées à un groupe de courriel ou un serveur de liste. Utilisez le widget de publication uniquement en conformité avec les normes de sécurité de votre société, les conditions contractuelles existantes et la législation en vigueur. Le widget de publication permet de limiter l’emplacement de publication des données en fonction de l’adresse IP ou du chemin de domaine. Toutefois, ces mécanismes sont destinés uniquement à empêcher la distribution sans surveillance des données et ils ne sont pas efficaces pour sécuriser l’accès aux données distribuées via le widget de publication.
>
> Adobe décline toute responsabilité quant aux données exposées via le widget de publication.

Les widgets de publication peuvent générer des volumes de trafic importants. Adobe se réserve donc le droit, à sa discrétion exclusive, de désactiver les widgets de publication d’une société en raison d’une utilisation incorrecte ou d’un trafic excessif ayant une incidence sur les performances globales.

## Résolution des incidents – Cache du widget de publication

La première fois qu’un utilisateur voit le widget de publication déployé, ce dernier exécute le rapport. Une fois le rapport exécuté, les résultats sont ajoutés à un cache et sont valides pendant 1 heure. Tout utilisateur suivant qui voit le widget de publication pendant cette heure voit la version mise en cache (elle est renvoyée instantanément). Une fois l’heure écoulée, tout utilisateur suivant qui voit le widget de publication le force à exécuter à nouveau le rapport et, là encore, les résultats sont mis en cache, etc. Ainsi, il est garanti que les données datent, au plus, d’une heure.

Si vous constatez des différences entre le widget de publication et l’interface de création de rapports, il se peut que vous deviez vider le cache du widget de publication.

1. Cliquez dans le widget de publication (de telle sorte que le widget soit activé).
1. Cliquez sur **[!UICONTROL Enregistrer]** dans le widget.
1. Exécutez à nouveau le widget. (Le mode d’aperçu n’utilise pas le cache du widget.)

> [!NOTE] La publication des widgets présente uniquement la première colonne des données d’un rapport.

## Description des widgets de publication {#section_D67478AECCA946B19A3E4C7071EB4871}

| Élément | Description |
|--- |--- |
| Nom | Nom du widget. |
| Description | (Facultatif) Entrez une description pour le widget. |
| Rapport | Dans la liste déroulante Rapport supérieure, sélectionnez un dossier ou un tableau de bord. Dans la liste déroulante Rapport inférieure, sélectionnez un mini-rapport ou un signet.  Aucune authentification des visiteurs n’est requise pour ces rapports. <br>Lorsqu’un visiteur charge une page web qui inclut un widget de publication, ce dernier affiche automatiquement le rapport associé à l’aide des données de rapport actuelles. Les modifications apportées à un widget de publication (modifier le rapport associé, par exemple) mettent automatiquement à jour l’affichage des rapports pour toutes les pages Web qui utilisent ce widget, sans qu’il faille redéployer ces pages.</br> |
| Destination | Indiquez la destination du widget.   Les destinations doivent présenter un format URL valide, y compris le préfixe https:// ou https://. Les destinations de widgets de publication sont inclusives, ce qui signifie que le widget de publication fonctionne sur toutes les URL qui contiennent la destination spécifiée. <br>Une destination de https://www.corp1.com/sales/ accepte, par exemple, des widgets de publication sur toutes les pages web au niveau ou au-dessous de la page ventes du site web www.corp1.com.</br> |
