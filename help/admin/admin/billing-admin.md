---
description: La page Facturation vous permet d’accéder aux informations de facturation, y compris les détails de trafic pour chaque suite de rapports. Seul un administrateur autorisé a accès à cette page.
title: Facturation
topic: Admin tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Facturation

La page Facturation vous permet d’accéder aux informations de facturation, y compris les détails de trafic pour chaque suite de rapports. Seul un administrateur autorisé a accès à cette page.

>[!NOTE] Si l’accès à l’onglet Facturation est désactivé pour votre société, contactez votre gestionnaire de compte.

Les données d’aperçu du trafic de la page de facturation vous permettent de mettre en corrélation les données de de pages dans les rapports avec les appels de serveur facturables sur votre facture. La [!UICONTROL Billing] page vous permet d’effectuer les opérations suivantes :

* Vérifier votre facture.
* Ventiler les coûts par suite de rapports pour les répartitions comptables internes.
*  la distribution des appels serveur principal et secondaire.

La [!UICONTROL Billing] page organise les informations par mois.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

Le [!UICONTROL Monthly Invoice] rapport résultant contient les informations suivantes :

| Colonne | Description |
|--- |--- |
| Suite de rapports | Suite de rapports impliquée dans l’activité de collecte de données. |
| Emplacement | Centre de données qui stocke les données de la suite de rapports : San Jose (Californie), Dallas (Texas), Pacific Northwest (États-Unis), London (Royaume-Uni) ou Singapour. Dans la plupart des cas, toutes les suites de rapports  sont situées dans le même centre de données. |
| Appels du serveur principal | Demandes reçues directement des navigateurs de de site Web ou de l’API d’insertion de données. Inclut les accès principaux ( de page), le personnalisé principal, le de téléchargement principal et le de sortie principal. |
| Appels aux serveurs secondaires | Copies des appels au serveur principal créées par des balises multi-suite ou copiées/déplacées par une règle VISTA.  Si un appel du serveur secondaire a été déplacé (et non copié) dans une autre suite de rapports par une règle VISTA, la page Facturation identifie ce transfert par un chiffre négatif. Dans ce cas, les appels secondaires cumulés sont déduits des appels du serveur principal. |
| Nombre total d’appels serveur | Il s’agit du total des appels des serveurs principal et secondaire combinés pour cette suite de rapports à un emplacement donné. |
| Pages vues | Total des pages vues pour chaque suite de rapports. Vous pouvez vérifier les valeurs des pages vues dans Mesures du site > Pages vues. |
| Téléchargements | Nombre total de téléchargements pour chaque suite de rapports. Vous pouvez vérifier les valeurs de téléchargement dans Contenu du site > Liens > Téléchargements de fichiers. |
| Liens personnalisés | Nombre total de liens personnalisés pour chaque suite de rapports. Vous pouvez vérifier les valeurs des liens personnalisés dans Contenu du site > Liens > Liens personnalisés. |
| Liens de sortie | Nombre total de liens de sortie pour chaque suite de rapports. Vous pouvez vérifier les valeurs des liens de sortie dans Contenu du site > Liens > Liens de sortie. |

>[!NOTE] Pour obtenir une copie de travail du [!UICONTROL Monthly Invoice] rapport, copiez-la dans le Presse-papiers, puis collez-la dans un de feuille de calcul tel que Microsoft Excel*.

## Comparaison de la date de création du rapport et de la date de traitement {#section_51A48C2F223F4904BE1407C13333C457}

Dans l’interface utilisateur de , les données présentées sont toujours liées à la date **du**, qui est l’horodatage associé à la .

L’utilisation/facturation, en revanche, utilise toujours la date **de** traitement ou le moment où les données ont été réellement traitées dans le système. En raison de la latence de base, des importations de données ou des différences de fuseau horaire de  (tout est traité dans l’heure du Pacifique), les dates de  et de traitement ne correspondent généralement pas complètement.
