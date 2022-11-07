---
description: Les listes de publication permettent d’envoyer aisément divers rapports spécifiques à différents groupes de votre entreprise sans créer des rapports planifiés distincts. Elles se révèlent particulièrement utiles si vous disposez de suites de rapports spécifiques à l’emplacement et souhaitez fournir à chaque division une copie d’un tableau de bord particulier. Vous pouvez également utiliser des listes de publication pour envoyer des données à plusieurs personnes sans avoir à saisir individuellement leurs adresses de courriel (si vous utilisez une seule suite de rapports).
title: Listes de publication
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 52%

---

# Listes de publication

Les listes de publication permettent d’envoyer aisément divers rapports spécifiques à différents groupes de votre entreprise sans créer des rapports planifiés distincts. Elles se révèlent particulièrement utiles si vous disposez de suites de rapports spécifiques à l’emplacement et souhaitez fournir à chaque division une copie d’un tableau de bord particulier. Vous pouvez également utiliser des listes de publication pour envoyer des données à plusieurs personnes sans avoir à saisir individuellement leurs adresses de courriel (si vous utilisez une seule suite de rapports).

Plusieurs listes de publication peuvent être spécifiées lors de la planification d’un rapport.

## Fin de vie des listes de publication

Comme vous le savez probablement, Adobe abandonnera Reports and Analytics (R&amp;A) ainsi que le produit SiteCatalyst le 31 décembre 2023. [Vous pouvez en savoir plus sur la fin de vie et comment vous y préparer ici](https://express.adobe.com/page/6WnF8JK6IRDhf/).

L’une des fonctionnalités de R&amp;A qui devrait atteindre la fin de vie à cette date est Listes de publication. Certaines fonctionnalités telles que les événements de calendrier et le rapport Résumé de la page ont/auront une version de parité dans Analysis Workspace. Cependant, les listes de publication ne font pas partie de ces listes et seront obsolètes lorsque la R&amp;A atteindra sa fin de vie. **Vous ne pourrez pas créer de listes de publication ou y accéder pour envoyer ou planifier des projets Analysis Workspace.**

Afin d’éviter toute interruption de vos processus actuels de distribution de rapports qui reposent sur des listes de publication, nous vous demandons de bien vouloir prendre en compte les alternatives suivantes :

* Si vous utilisez Listes de publication pour distribuer la même version du rapport à plusieurs utilisateurs (sans appliquer de remplacement de suite de rapports) :

   Une fois que vous avez recréé vos rapports dans Analysis Workspace en tant que projets, vous pouvez utiliser une combinaison d’un groupe de contacts ou d’une liste de distribution créés pour votre client de messagerie et de la fonction Projets planifiés de Workspace pour envoyer ou planifier la livraison récurrente du projet. Comme pour les listes de publication, une version PDF/CSV du projet est alors envoyée à chaque ID de courrier électronique faisant partie du groupe/de la liste. Vous pouvez en savoir plus sur [Projets planifiés ici](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html#:~:text=Scheduled%20Analysis%20Workspace%20projects%20can,options%20in%20the%20left%20rail.).

* Si vous utilisez Listes de publication pour distribuer plusieurs versions du rapport ou du tableau de bord à plusieurs utilisateurs (via la fonction de remplacement de la suite de rapports) :

   Analysis Workspace ne prend pas en charge les remplacements de suite de rapports. Il ne prend pas non plus en charge la possibilité de verrouiller des suites de rapports lors du partage ou de la planification de projets. Pour répliquer le workflow, vous devrez peut-être créer plusieurs versions d’un même projet avec une suite de rapports différente appliquée à chaque version, puis utiliser la fonctionnalité de projet planifiée décrite ci-dessus.

Pour toute question ou assistance supplémentaire, contactez l’assistance clientèle Adobe.

## Description des éléments du gestionnaire de listes de publication {#section_099DF8AC5691495F9B22C71266DD6004}

| Élément | Description |
|--- |--- |
| [!UICONTROL Rechercher] | Permet de filtrer le tableau à la recherche d’une liste de publication. |
| [!UICONTROL Report Suites à inclure] | Remplace la suite de rapports pour un rapport planifié ou tous les petits rapports d’un tableau de bord. Bien que, sur le plan technique, le nombre d’entrées de suites de rapports distinctes ne soit pas limité, il est conseillé de ne pas en définir plus de 50. Le nombre de courriels pouvant être inclus est, lui aussi, illimité. |
| [!UICONTROL Adresses de courriel] | Liste, délimitée par des virgules, de toutes les adresses qui recevront le rapport avec la nouvelle suite de rapports.  Cliquez sur **[!UICONTROL Cliquer pour modifier]** pour spécifier les adresses de courriel de réception. Séparez les différentes adresses électroniques à l’aide d’un point-virgule (;). Appuyez sur `<Enter>` une fois la saisie des adresses électroniques terminée. <br>Le champ Nombre d’e-mails affiche le nombre d’adresses électroniques associées actuellement à l’entrée de la suite de rapports. |
| [!UICONTROL Dupliquer] | Crée une copie de la liste de publication. |
