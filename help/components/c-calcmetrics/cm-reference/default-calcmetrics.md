---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: Mesures calculées par défaut
feature: Calculated Metrics
source-git-commit: b383e856374791be7d85b1f25566e8d98a099ec8
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 4%

---

# Mesures calculées par défaut

Adobe Analytics fournit diverses mesures calculées pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées sont disponibles par défaut dans Analysis Workspace.

Vous trouverez ci-dessous une liste de chaque mesure calculée fournie par Adobe, avec sa fonction prévue et la formule sous-jacente utilisée pour le calcul :

>[!NOTE]
>
>Outre les mesures calculées par défaut décrites sur cette page, vous pouvez ajouter d’autres mesures calculées à une suite de rapports.
>
>Vous pouvez :
> * Ajout de mesures calculées par défaut pour les médias en flux continu, comme décrit dans la section [Mesures calculées](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Créez des mesures calculées personnalisées à partir de mesures existantes, comme décrit dans la section [Mesures calculées ou calculées avancées (dérivées)](/help/components/c-calcmetrics/cm-overview.md).



| Nom de la mesure calculée | Fonction | Formule |
|---------|----------|---------|
| Taux de rebond | Le rapport entre les visites qui contenait exactement un accès et le nombre de visites sur cette page. Cela peut vous aider à comprendre les éléments de dimension présentant le taux de rebond le plus élevé ou à afficher le taux de rebond total agrégé de votre site au fil du temps. | `[Bounces] / [Entries]` |
| Recettes / Visiteur | Montant moyen des recettes générées par chaque visiteur du site. | `[Revenue] / [Unique Visitors]` |
| Commandes / Visiteur | Nombre moyen de commandes ou de transactions générées par chaque visiteur du site. | `[Orders] / [Unique Visitors]` |
| Recettes / Visites | Montant moyen des recettes générées par une seule visite sur le site. | `[Revenue] / [Visits]` |
| Recettes / Commande | Montant moyen des recettes générées par chaque transaction ou commande terminée sur le site. | `[Revenue] / [Orders]` |
| Commandes / Visites | Pourcentage de visites sur le site qui entraînent la réalisation d’une transaction. | `[Orders] / [Visits]` |
| Pages vues / Visites | Nombre moyen de pages qu’un utilisateur consulte au cours d’une seule visite sur le site. | `[Page Views] / [Visits]` |
| Visites / Visiteur | Nombre moyen de visites qu’un visiteur unique effectue sur le site. | `[Visits] / [Unique Visitors]` |
| Actualisations / Pages vues | Pourcentage de pages vues qui ont entraîné un rechargement ou une actualisation de la page. | `[Reloads] / [Page Views]` |
| Taux de rebond moyen | Fonction | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Aide à la commande | Le nombre de fois où un canal ou une source a contribué au parcours d’un client à effectuer un achat, mais n’a pas donné lieu à l’achat final. | `[Orders (Visit Participation)] - [Orders]` |
| Taux de sortie | Pourcentage des visiteurs qui quittent le site après avoir consulté une page spécifique. | `[Exits] / [Visits]` |
| Taux d’entrée | Pourcentage des visiteurs ayant accédé au site sur une page donnée, par rapport au nombre total de sessions sur le site. | `[Entries] / [Visits]` |
| Durée moyenne du site | Durée moyenne passée par un visiteur sur le site avant de quitter le site ou de quitter le site. | `[Average Time Spent on Site (Seconds)]` |
| Durée de la visite/de l’utilisateur (état) | Durée passée par le visiteur moyen dans un état particulier pendant sa visite sur le site | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Utilisateurs (mobile) | Nombre total d’utilisateurs d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Utilisateurs de l’application | Nombre total d’utilisateurs d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Vues d’état | Nombre d’affichages pour les différents états ou écrans de l’application | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Actions | Nombre total d’actions entreprises dans l’application | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Clics sur les liens d’acquisition | Nombre de clics sur un lien conçu pour diriger le trafic vers le site. | `[Campaign Click-throughs]` |
| Vitesse de la page | Nombre de pages vues supplémentaires générées par un élément de contenu. Cela peut vous aider à déterminer quel contenu génère un engagement supplémentaire. | `[Page Views] / [Visits]` |
| Taux de conversion | Pourcentage de visiteurs qui ont effectué une action souhaitée, telle qu’un achat. | `[Orders] / [Visits]` |
| Durée de session moyenne (mobile) | Durée moyenne passée par les visiteurs sur le site au cours d’une seule session. | Vide |
| Couverture des identifiants Experience Cloud | Pourcentage de visiteurs disposant d’un identifiant Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Vitesse du contenu | La vitesse à laquelle le nouveau contenu est créé et publié sur le site et la vitesse à laquelle il génère l’engagement des utilisateurs. | `[Page Views] / [Visits]` |
| Visiteurs uniques ITP 2.1 / Visiteurs uniques | Pourcentage de visiteurs uniques utilisant un navigateur affecté par les restrictions des cookies ITP 2.1. En d’autres termes, les clients n’utilisant pas de mise en oeuvre CNAME. (Cela s’applique aux clients qui définissent des cookies via JavaScript côté client.) | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Visiteurs uniques / Visiteurs uniques revenant après 7 jours | Pourcentage de visiteurs uniques qui reviennent après une période de 7 jours ou plus. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Pages vues / Visiteur unique | Nombre moyen de pages vues pour chaque visiteur unique du site. | `[Page Views] / [Unique Visitors]` |
| Visites / Visiteurs | Nombre moyen de visites qu’un visiteur unique effectue sur le site . | `[Visits] / [Unique Visitors]` |
| Nombre estimé de visiteurs uniques (ITP 2.1) | Pour les visiteurs ITP (utilisateurs sur les navigateurs Safari), divisez les visiteurs uniques par 2 ou moins. Cette mesure calculée suppose que vous définissez des cookies à l’aide de code JavaScript côté client (sans utiliser d’implémentation CNAME). Les mises en oeuvre qui définissent des cookies à l’aide de JavaScript côté client ont été affectées à partir d’ITP 2.1. Voir [Prévention intelligente du suivi](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) pour plus d’informations. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Pages vues / Nombre estimé de visiteurs uniques (ITP 2.1) | Nombre moyen de pages vues pour l’estimation du nombre de visiteurs uniques (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |

{style="table-layout:auto"}
