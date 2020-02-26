---
description: La page Facturation vous permet d’accéder aux informations de facturation, dont les détails de trafic de chaque suite de rapports. Seul un administrateur autorisé peut accéder à cette page.
title: Facturation
topic: Admin tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Facturation

La page Facturation vous permet d’accéder aux informations de facturation, dont les détails de trafic de chaque suite de rapports. Seul un administrateur autorisé peut accéder à cette page.

> [!NOTE] Si l’accès à l’onglet Facturation est désactivé pour votre société, contactez votre gestionnaire de compte.

Les données de vue d’ensemble du trafic issues de la page de facturation vous permettent de mettre en relation les données des rapports et les appels serveur facturables figurant sur votre facture. La page [!UICONTROL Facturation] vous permet d’effectuer les opérations suivantes :

* Vérifier votre facture.
* Ventiler les coûts par suite de rapports à des fins de comptabilité interne.
* Visualiser la distribution des appels des serveurs principal et secondaire.

La page [!UICONTROL Facturation] classe les informations par mois.

Pour afficher des données d’aperçu du trafic mensuelles, recherchez le mois dont vous souhaitez visualiser les données de trafic, puis cliquez sur **[!UICONTROL Afficher]**.

Le rapport [!UICONTROL Facture mensuelle] obtenu comprend les informations suivantes :

| Colonne | Description |
|--- |--- |
| Suite de rapports | Suite de rapports impliquée dans l’activité de collecte de données. |
| Emplacement | Le centre de données qui stocke les données des suites de rapports : San José (Californie), Dallas (Texas), Nord-ouest Pacifique (États-Unis), Londres (Royaume-Uni) ou Singapour. Dans la plupart des cas, toutes les suites de rapports se trouvent dans le même centre de données. |
| Appels du serveur principal | Demandes transmises directement par les navigateurs des visiteurs du site web ou l’API d’insertion de données. Inclut les accès principaux (pages vues), les événements personnalisés principaux, les événements de téléchargement principaux et les événements de sortie principaux. |
| Appels aux serveurs secondaires | Copies des appels au serveur principal créées par des balises multi-suite ou copiées/déplacées par une règle VISTA.  Si un appel du serveur secondaire a été déplacé (et non copié) dans une autre suite de rapports par une règle VISTA, la page Facturation identifie ce transfert par un chiffre négatif. Dans ce cas, les appels secondaires cumulés sont déduits des appels du serveur principal. |
| Nombre total d’appels serveur | Il s’agit du total des appels des serveurs principal et secondaire combinés pour cette suite de rapports à un emplacement donné. |
| Pages vues | Total des pages vues pour chaque suite de rapports. Vous pouvez vérifier les valeurs des pages vues dans Mesures du site > Pages vues. |
| Téléchargements | Nombre total de téléchargements pour chaque suite de rapports. Vous pouvez vérifier les valeurs de téléchargement dans Contenu du site > Liens > Téléchargements de fichiers. |
| Liens personnalisés | Nombre total de liens personnalisés pour chaque suite de rapports. Vous pouvez vérifier les valeurs des liens personnalisés dans Contenu du site > Liens > Liens personnalisés. |
| Liens de sortie | Nombre total de liens de sortie pour chaque suite de rapports. Vous pouvez vérifier les valeurs des liens de sortie dans Contenu du site > Liens > Liens de sortie. |

> [!NOTE] Pour obtenir une copie de travail du rapport [!UICONTROL Facture mensuelle], copiez ce dernier dans le presse-papiers, puis collez-le dans un tableur tel que Microsoft Excel*.

## Comparaison de la date de création du rapport et de la date de traitement {#section_51A48C2F223F4904BE1407C13333C457}

Dans l’interface utilisateur de création de rapports, les données présentées sont toujours jointes à la **Date de création du rapport**, qui est l’horodatage joint à l’événement.

L’utilisation/la facturation, par contre, utilise systématiquement la **Date de traitement**, ou la date à laquelle les données ont été réellement traitées dans le système. En raison des différences de latence de base, d’importation des données ou de fuseau horaire des événements (tout est traité en heure du Pacifique (PST)), la date de création du rapport et la date de traitement ne correspondent généralement pas parfaitement.
