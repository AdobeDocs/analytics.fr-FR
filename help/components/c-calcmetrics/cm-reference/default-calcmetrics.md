---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leur utilisation prévue.
title: Mesures calculées par défaut
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 40%

---

# Mesures calculées par défaut

Adobe Analytics fournit diverses mesures calculées pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées sont disponibles par défaut dans Analysis Workspace.

Voici une liste de chaque mesure calculée fournie par Adobe, avec sa fonction prévue et la formule sous-jacente utilisée pour la calculer :

>[!NOTE]
>
>Outre les mesures calculées par défaut décrites sur cette page, vous pouvez ajouter des mesures calculées supplémentaires à une suite de rapports.
>
>Vous pouvez :
>
> * Ajoutez des mesures calculées par défaut pour la collection de médias en flux continu, comme décrit dans [Mesures calculées](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Créez des mesures calculées personnalisées à partir de mesures existantes, comme décrit dans la section [Mesures calculées et avancées](/help/components/c-calcmetrics/cm-overview.md).


| Nom de la mesure calculée | Fonction | Formule |
| --- | --- | --- |
| Clics sur le lien d’acquisition | Nombre de fois où les personnes cliquent sur un lien conçu pour générer du trafic vers le site. | `[Campaign Click-throughs]` |
| Actions | Nombre total d’actions entreprises dans l’application | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Utilisateurs de l’application | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Durée De Session Moyenne (Mobile) | Temps moyen que les visiteurs et visiteuses passent sur le site au cours d’une seule session. | Vide |
| Temps moyen passé sur le site | Temps moyen qu’un visiteur ou une visiteuse passe sur le site avant de le quitter. | `[Average Time Spent on Site (Seconds)]` |
| Taux de rebond | Taux de visites contenant exactement un accès par rapport au nombre de visites sur cette page. Cette mesure peut vous aider à identifier les éléments de dimension qui présentent le taux de rebond le plus élevé ou à afficher le taux de rebond total agrégé de votre site au fil du temps. | `[Bounces] / [Entries]` |
| Ratio de pages robot vues | Rapport entre le nombre de pages vues par les robots et le nombre total de pages vues. | `[Bot Page Views] / [Page Views]` |
| Vitesse du contenu | Vitesse à laquelle le nouveau contenu est créé et publié sur le site et rapidité avec laquelle il génère l’engagement de la clientèle. | `[Page Views] / [Visits]` |
| Taux de conversion | Le pourcentage de visiteurs et visiteuses qui ont effectué l’action souhaitée (un achat, par exemple). | `[Orders] / [Visits]` |
| Taux d’entrée | Le pourcentage de visiteurs et visiteuses qui sont entrés sur le site sur une page donnée, par rapport au nombre total de sessions sur le site. | `[Entries] / [Visits]` |
| Estimation du nombre de visiteurs uniques (ITP 2.1) | Pour les visiteurs ITP (utilisateurs sur les navigateurs Safari), divisez les visiteurs uniques par 2 ou moins. Cette mesure calculée suppose que vous avez défini les cookies à l’aide de JavaScript côté client (et non à l’aide d’une implémentation CNAME). Les implémentations qui définissent des cookies à l’aide de JavaScript côté client ont été affectées à partir d’ITP 2.1. Voir [ Prévention intelligente du suivi ](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) pour plus d’informations. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Couverture Experience Cloud ID | Pourcentage de visiteurs et de visiteuses qui disposent d’un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Taux de sortie | Pourcentage de visiteurs et visiteuses qui quittent le site après avoir consulté une page particulière. | `[Exits] / [Visits]` |
| ITP 2.1 Visiteurs uniques/Visiteurs uniques | Pourcentage de visiteurs et visiteuses uniques utilisant un navigateur affecté par les limitations de cookies ITP 2.1. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Aide à la commande | Le nombre de fois qu’un canal ou une source a contribué au parcours d’un client ou d’une cliente vers l’achat, mais n’a pas abouti à l’achat final. | `[Orders (Visit Participation)] - [Orders]` |
| Commandes/Visites | Pourcentage de visites sur le site qui ont abouti à une transaction. | `[Orders] / [Visits]` |
| Commandes / Visiteur | Nombre moyen de commandes ou de transactions générées par chaque visiteur et visiteuse individuel du site | `[Orders] / [Unique Visitors]` |
| Pages vues/Nombre estimé de visiteurs uniques (ITP 2.1) | Nombre moyen de pages vues pour le nombre estimé de visiteurs et visiteuses uniques (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Pages vues/Visiteur unique | Nombre moyen de pages vues pour chaque visiteur ou visiteuse unique sur le site. | `[Page Views] / [Unique Visitors]` |
| Pages vues/Visites | Le nombre moyen de pages vues par un utilisateur ou une utilisatrice au cours d’une seule visite sur le site. | `[Page Views] / [Visits]` |
| Vitesse de la page | Nombre de pages vues supplémentaires générées par un élément de contenu. Cette mesure peut vous aider à déterminer quel contenu génère un engagement supplémentaire. | `[Page Views] / [Visits]` |
| Rechargements/Pages vues | Le pourcentage de pages vues ayant entraîné un rechargement ou une actualisation de la page. | `[Reloads] / [Page Views]` |
| Chiffre d’affaires/Commande | Montant moyen des revenus générés par chaque transaction ou commande effectuée sur le site. | `[Revenue] / [Orders]` |
| Chiffre d’affaires/visites | Montant moyen du revenu généré par une seule visite sur le site. | `[Revenue] / [Visits]` |
| Chiffre d’affaires/visiteur | Le montant moyen des revenus générés par chaque personne individuelle visitant le site. | `[Revenue] / [Unique Visitors]` |
| Vues d’état | Nombre de vues des différents états ou écrans de l’application | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Durée De La Visite/Utilisateur (État) | Durée passée par le visiteur moyen ou la visiteuse moyenne dans un état particulier sur le site | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Visiteurs uniques / Visiteurs uniques qui reviennent après 7 jours | Le pourcentage de visiteurs et visiteuses uniques qui reviennent après une période de 7 jours ou plus. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Utilisateurs (Mobile) | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Visites/Visiteur | Nombre moyen de visites qu’un visiteur ou une visiteuse unique effectue sur le site. | `[Visits] / [Unique Visitors]` |
| Taux de rebond moyen | Fonction | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
