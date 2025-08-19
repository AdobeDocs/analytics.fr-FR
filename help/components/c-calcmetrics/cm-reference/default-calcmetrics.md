---
description: Adobe propose différentes mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leur utilisation prévue.
title: Mesures calculées par défaut
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 98%

---

# Mesures calculées par défaut

Adobe Analytics fournit diverses mesures calculées pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées sont disponibles par défaut dans Analysis Workspace.

Voici une liste de chaque mesure calculée fournie par Adobe, avec sa fonction prévue et la formule sous-jacente utilisée pour la calculer :

>[!NOTE]
>
>Outre les mesures calculées par défaut décrites dans cette page, vous pouvez ajouter des mesures calculées supplémentaires à une suite de rapports.
>
>Vous pouvez effectuer les opérations suivantes :
>
> * Ajoutez des mesures calculées par défaut pour les services de streaming multimédia, comme décrit dans la section [Mesures calculées](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html?lang=fr)
> * Créer des mesures calculées personnalisées à partir de mesures existantes, comme décrit dans la section [Mesures calculées et avancées](/help/components/c-calcmetrics/cm-overview.md).
>

>[!TIP]
>
>Utilisez le [dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) pour examiner plus en détail la définition d’une mesure calculée par défaut et les composants individuels qui constituent cette définition.
>



| Nom de la mesure calculée | Fonction | Formule |
| --- | --- | --- |
| Clics sur des liens d’acquisition | Nombre de fois où les personnes cliquent sur un lien conçu pour générer du trafic vers le site. | `[Campaign Click-throughs]` |
| Actions | Nombre total d’actions entreprises dans l’application | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Utilisateurs et utilisatrices d’application | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Durée de session moyenne (mobile) | Temps moyen passé par les visiteurs et visiteuses sur le site au cours d’une seule session. | Vide |
| Temps moyen passé sur le site | Temps moyen qu’un visiteur ou une visiteuse passe sur le site avant de le quitter. | `[Average Time Spent on Site (Seconds)]` |
| Taux de rebond | Rapport entre les visites qui contenaient exactement un accès et le nombre de visites sur cette page. Cette mesure peut vous aider à identifier les éléments de dimension présentant le taux de rebond le plus élevé ou à afficher le taux de rebond total agrégé de votre site au fil du temps. | `[Bounces] / [Entries]` |
| Ratio de pages robot vues | Rapport entre le nombre de pages robot vues et le nombre total de pages vues. | `[Bot Page Views] / [Page Views]` |
| Vitesse du contenu | Vitesse à laquelle le nouveau contenu est créé et publié sur le site et la rapidité avec laquelle il génère de l’interaction client. | `[Page Views] / [Visits]` |
| Taux de conversion | Pourcentage de visiteurs et visiteuses qui ont effectué l’action souhaitée (un achat, par exemple). | `[Orders] / [Visits]` |
| Taux d’entrée | Pourcentage de visiteurs et visiteuses qui sont entrés sur le site sur une page donnée, par rapport au nombre total de sessions sur le site. | `[Entries] / [Visits]` |
| Nombre estimé de visiteurs et visiteuses uniques (ITP 2.1) | Pour les visiteurs et visiteuses ITP (utilisateurs et utilisatrices sur les navigateurs Safari), divisez les visiteurs et visiteuses uniques par 2 ou moins. Cette mesure calculée suppose que vous avez défini les cookies à l’aide de code JavaScript côté client (et non à l’aide d’une implémentation CNAME). Les implémentations qui définissent des cookies à l’aide de code JavaScript côté client ont été affectées à partir d’ITP 2.1. Voir [Prévention intelligente du suivi](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) pour plus d’informations. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Couverture Experience Cloud ID | Pourcentage de visiteurs et de visiteuses qui disposent d’un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Taux de sortie | Pourcentage de visiteurs et visiteuses qui quittent le site après avoir consulté une page particulière. | `[Exits] / [Visits]` |
| ITP 2.1 Visiteurs et visiteuses uniques/Visiteurs et visiteuses uniques | Pourcentage de visiteurs et visiteuses uniques utilisant un navigateur affecté par les limitations de cookies ITP 2.1. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Aide à la commande | Nombre de fois qu’un canal ou une source a contribué au parcours d’un client ou d’une cliente vers l’achat, mais n’a pas abouti à l’achat final. | `[Orders (Visit Participation)] - [Orders]` |
| Commandes/Visites | Pourcentage de visites sur le site qui ont abouti à une transaction. | `[Orders] / [Visits]` |
| Commandes/Visiteur ou visiteuse | Nombre moyen de commandes ou de transactions générées par chaque visiteur ou visiteuse du site. | `[Orders] / [Unique Visitors]` |
| Pages vues/Nombre estimé de visiteurs ou de visiteuses uniques (ITP 2.1) | Nombre moyen de pages vues pour le nombre estimé de visiteurs et visiteuses uniques (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Pages vues/Visiteur ou visiteuse unique | Nombre moyen de pages vues pour chaque visiteur ou visiteuse unique sur le site. | `[Page Views] / [Unique Visitors]` |
| Pages vues/Visites | Nombre moyen de pages vues par un utilisateur ou une utilisatrice au cours d’une seule visite sur le site. | `[Page Views] / [Visits]` |
| Vitesse de la page | Nombre de pages vues supplémentaires généré par un élément de contenu. Cette mesure peut vous aider à déterminer quel contenu génère un engagement supplémentaire. | `[Page Views] / [Visits]` |
| Actualisations/Pages vues | Pourcentage de pages vues ayant entraîné un rechargement ou une actualisation de la page. | `[Reloads] / [Page Views]` |
| Recettes/Commande | Montant moyen des revenus générés par chaque transaction ou commande effectuée sur le site. | `[Revenue] / [Orders]` |
| Recettes/Visites | Montant moyen des revenus générés par une seule visite sur le site. | `[Revenue] / [Visits]` |
| Recettes/Visiteur ou visiteuse | Montant moyen des revenus générés par chaque personne visitant le site. | `[Revenue] / [Unique Visitors]` |
| Vues d’état | Nombre de vues des différents états ou écrans de l’application. | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Temps passé/Utilisateur ou utilisatrice (état) | Temps que le visiteur moyen ou la visiteuse moyenne passe dans un état particulier sur le site. | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Visiteurs et visiteuses uniques/Visiteurs et visiteuses uniques qui reviennent après 7 jours | Pourcentage de visiteurs et visiteuses uniques qui reviennent après une période de 7 jours ou plus. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Utilisateurs et utilisatrices (mobile) | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Visites/Visiteur ou visiteuse | Nombre moyen de visites qu’un visiteur ou une visiteuse unique effectue sur le site. | `[Visits] / [Unique Visitors]` |
| Taux de rebond pondéré | Fonction | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
