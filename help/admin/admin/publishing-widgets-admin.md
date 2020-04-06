---
description: Un widget de publication est un  de publication qui vous permet d’incorporer des rapports marketing (signets et  de) sur une page Web. Les personnes de votre entreprise qui n’ont pas accès aux rapports marketing peuvent des données pertinentes.
title: Widget de publication
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Widget de publication

Un widget de publication est un conteneur qui vous permet d’intégrer des rapports Analytics (signets et tableaux de bord) dans une page web. Les personnes de votre société qui n’ont pas accès aux rapports Analytics peuvent consulter des données pertinentes.

Vous pouvez, par exemple, mettre à la disposition des cadres de la société un tableau de bord leur permettant de consulter le nombre de visiteurs, de visiteurs uniques, etc.

>[!CAUTION] Aucune authentification n’est requise pour afficher les données publiées par le biais du widget de publication. Vous devez donc tenir compte du fait que les données publiées ne sont pas plus protégées que celles envoyées à un groupe de courriel ou un serveur de liste. Utilisez le widget uniquement en conformité avec les normes de sécurité de votre entreprise, les exigences contractuelles existantes et les lois applicables. Le widget de publication permet de limiter, par adresse IP ou chemin de domaine, l’emplacement de publication des données. Toutefois, ces mécanismes sont destinés uniquement à empêcher la distribution non intentionnelle des données et ne sont pas un moyen efficace de sécuriser l’accès aux données distribuées via le widget de publication.
>
> Adobe décline toute responsabilité quant aux données exposées par le biais du widget de publication.

Etant donné que le widget de publication peut générer des volumes de trafic importants, Adobe se réserve le droit, à sa seule discrétion, de désactiver un widget de publication de pour une utilisation incorrecte ou un trafic excessif qui a un impact sur les performances globales.

## Résolution des incidents – Cache du widget de publication

La première fois qu’un utilisateur voit le widget de publication déployé, le widget exécute le rapport. Une fois le rapport exécuté, les résultats sont ajoutés à un cache et sont valides pendant 1 heure. Tout utilisateur suivant qui  le widget de publication dans l’heure suivante verra la version mise en cache (elle sera renvoyée instantanément). Après une heure, tout utilisateur suivant qui  le widget de publication le force à exécuter à nouveau le rapport, puis ces résultats sont mis en cache, etc. De cette façon, les données sont garanties d&#39;avoir au plus une heure.

Si vous constatez des différences de données entre le widget de publication et l’interface  du, vous devrez peut-être effacer le cache du widget de publication.

1. Cliquez sur dans le widget de publication (afin que le widget soit activé).
1. Click **[!UICONTROL Save]** on the widget.
1. Réexécutez le widget. (Le mode  n’utilise pas le cache du widget.)

>[!NOTE] La publication des widgets présente uniquement la première colonne des données d’un rapport.

## Description des widgets de publication {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elément | Description |
|--- |--- |
| Nom | Nom du widget. |
| Description | (Facultatif) Entrez une description pour le widget. |
| Rapport | Dans le déroulant Rapport supérieur, sélectionnez un dossier ou un  de. Dans la liste déroulante Rapport inférieure, sélectionnez un mini-rapport ou un signet.  Aucune authentification des visiteurs n’est requise pour ces rapports. <br>Lorsqu’un visiteur charge une page web qui inclut un widget de publication, ce dernier affiche automatiquement le rapport associé à l’aide des données de rapport actuelles. Les modifications apportées à un widget de publication (modifier le rapport associé, par exemple) mettent automatiquement à jour l’affichage des rapports pour toutes les pages Web qui utilisent ce widget, sans qu’il faille redéployer ces pages.</br> |
| Destination | Indiquez la destination du widget.   Les destinations doivent présenter un format URL valide, y compris le préfixe https:// ou https://. Les destinations de widgets de publication sont inclusives, ce qui signifie que le widget de publication fonctionne sur toutes les URL qui contiennent la destination spécifiée. <br>Une destination de https://www.corp1.com/sales/ accepte, par exemple, des widgets de publication sur toutes les pages web au niveau ou au-dessous de la page ventes du site web www.corp1.com.</br> |
