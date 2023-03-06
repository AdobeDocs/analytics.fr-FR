---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: 'Référence : fonctions de base'
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 2874ea66765e650a92bc39537d6a9eb8cebcd6a4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 10%

---

# Mesures calculées par défaut

Adobe Analytics fournit diverses mesures calculées pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées sont disponibles par défaut dans Analysis Workspace.

Vous trouverez ci-dessous une liste de chaque mesure calculée fournie par Adobe, avec sa fonction prévue et la formule sous-jacente utilisée pour le calcul :

>[!NOTE]
>
>Outre les mesures calculées par défaut décrites sur cette page, vous pouvez ajouter d’autres mesures calculées à une suite de rapports.
>
>Vous pouvez :
> * Ajout de mesures calculées par défaut pour les médias en flux continu, comme décrit dans la section [Mesures calculées](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Créez des mesures calculées personnalisées à partir de mesures existantes, comme décrit dans la section [Mesures calculées ou calculées avancées (dérivées)](/help/components/c-calcmetrics/cm-overview.md).



| Nom de la mesure calculée | Fonction | Formule |
|---------|----------|---------|
| Taux de rebond | Le rapport entre les visites qui contenait exactement un accès et le nombre de visites sur cette page. Cela peut vous aider à comprendre les éléments de dimension présentant le taux de rebond le plus élevé ou à afficher le taux de rebond total agrégé de votre site au fil du temps. | Taux de rebond |
| Recettes / Visiteur | Montant moyen des recettes générées par chaque visiteur du site. | <p>Chiffre dʼaffaires</p><p>/</p><p>Visiteurs uniques</p> |
| Commandes / Visiteur | Nombre moyen de commandes ou de transactions générées par chaque visiteur du site. | <p>Commandes par défaut</p><p>/</p><p>Visiteur</p> |
| Recettes / Visites | Montant moyen des recettes générées par une seule visite sur le site. | <p>Chiffre dʼaffaires</p><p>/</p><p>Visites uniques</p> |
| Recettes / Commande | Montant moyen des recettes générées par chaque transaction ou commande terminée sur le site. | <p>Chiffre dʼaffaires</p><p>/</p><p>Commande</p> |
| Commandes / Visites | Pourcentage de visites sur le site qui entraînent la réalisation d’une transaction. | <p>Commande</p><p>/</p><p>Visites</p> |
| Pages vues / Visites | Nombre moyen de pages qu’un utilisateur consulte au cours d’une seule visite sur le site. | <p>Pages vues</p><p>/</p><p>Visites</p> |
| Visites / Visiteur | Nombre moyen de visites qu’un visiteur unique effectue sur le site. | <p>Visites</p><p>/</p><p>Visiteurs uniques</p> |
| Actualisations / Pages vues | Pourcentage de pages vues qui ont entraîné un rechargement ou une actualisation de la page. | <p>Actualisations</p><p>/</p><p>Pages vues</p> |
| Taux de rebond moyen | Fonction | if(visites>percentile(visites),bouncerate,0) |
| Aide à la commande | Le nombre de fois où un canal ou une source a contribué au parcours d’un client à effectuer un achat, mais n’a pas donné lieu à l’achat final. | <p>Commandes (Participation\|Visite)</p><p>-</p><p>Commandes</p> |
| Taux de sortie | Pourcentage des visiteurs qui quittent le site après avoir consulté une page spécifique. | <p>Sorties</p><p>/</p><p>Visites</p> |
| Taux d’entrée | Pourcentage des visiteurs ayant accédé au site sur une page donnée, par rapport au nombre total de sessions sur le site. | <p>Entrées</p><p>/</p><p>Visites</p> |
| Durée moyenne du site | Durée moyenne passée par un visiteur sur le site avant de quitter le site ou de quitter le site. | Durée moyenne de la visite du site (secondes) |
| Durée de la visite/de l’utilisateur (état) | Durée passée par le visiteur moyen dans un état particulier pendant sa visite sur le site | Mesure Durée par visiteur (secondes) + segment Application mobile |
| Utilisateurs (mobile) | Nombre total d’utilisateurs d’une application mobile | Mesure Visiteurs uniques + segment Utilisateurs de l’application mobile |
| Utilisateurs de l’application | Nombre total d’utilisateurs d’une application mobile | Mesure Visiteurs uniques + segment Applications mobiles |
| Vues d’état | Nombre d’affichages pour les différents états ou écrans de l’application | Mesure Pages vues + segment Application mobile |
| Actions | Nombre total d’actions entreprises dans l’application | Mesure Instances de lien personnalisé + comporte un segment Action |
| Clics sur les liens d’acquisition | Nombre de clics sur un lien conçu pour diriger le trafic vers le site. | Mesure des clics publicitaires de campagne |
| Vitesse de la page | Nombre de pages vues supplémentaires générées par un élément de contenu. Cela peut vous aider à déterminer quel contenu génère un engagement supplémentaire. | <p>Pages vues</p><p>/</p><p>Visites</p> |
| Taux de conversion | Pourcentage de visiteurs qui ont effectué une action souhaitée, telle qu’un achat. | <p>Commandes</p><p>/</p><p>Visites</p> |
| Durée de session moyenne (mobile) | Durée moyenne passée par les visiteurs sur le site au cours d’une seule session. | Vide |
| Couverture des identifiants Experience Cloud | Pourcentage de visiteurs disposant d’un identifiant Experience Cloud. | <p>Visiteurs avec un Experience Cloud ID</p><p>/</p><p>Visiteurs uniques</p> |
| Vitesse du contenu | La vitesse à laquelle le nouveau contenu est créé et publié sur le site et la vitesse à laquelle il génère l’engagement des utilisateurs. | <p>Pages vues</p><p>/</p><p>Visites</p> |
| Visiteurs uniques ITP 2.1 / Visiteurs uniques | Pourcentage de visiteurs uniques utilisant un navigateur affecté par les restrictions des cookies ITP 2.1. En d’autres termes, les clients n’utilisant pas de mise en oeuvre CNAME. (Cela s’applique aux clients qui définissent des cookies via JavaScript côté client.) | <p>Mesure Visiteurs uniques + segment Visiteurs ITP</p><p>/</p><p>Visiteurs uniques</p> |
| Visiteurs uniques / Visiteurs uniques revenant après 7 jours | Pourcentage de visiteurs uniques qui reviennent après une période de 7 jours ou plus. | <p>Mesure Visiteurs uniques + utilisateurs revenant après un segment de 7 jours</p><p>/</p><p>Visiteurs uniques</p> |
| Pages vues / Visiteur unique | Nombre moyen de pages vues pour chaque visiteur unique du site. | <p>Pages vues</p><p>/</p><p>Visiteurs uniques</p> |
| Visites / Visiteurs | Nombre moyen de visites qu’un visiteur unique effectue sur le site . | <p>Visites</p><p>/</p><p>Visiteurs uniques</p> |
| Nombre estimé de visiteurs uniques (ITP 2.1) | <p>Pour les visiteurs ITP (utilisateurs sur les navigateurs Safari), divisez les visiteurs uniques par 2 ou moins.</p><p>Cela suppose que vous définissez des cookies à l’aide de code JavaScript côté client (sans utiliser d’implémentation CNAME). Les mises en oeuvre qui définissent des cookies à l’aide de JavaScript côté client ont été affectées à partir d’ITP 2.1. Voir : [https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)</p> | <p>Segment Visiteurs uniques + Visiteurs ITP (ITP 2.1, implémentations non CNAME)</p><p>/</p><p>Segment de mesures Visiteurs uniques + visiteurs non ITP (ITP 2.1, implémentations non CNAME)</p> |
| Pages vues / Nombre estimé de visiteurs uniques (ITP 2.1) | Nombre moyen de pages vues pour l’estimation du nombre de visiteurs uniques (ITP 2.1). | <p>Segment Visiteurs uniques + Visiteurs ITP (ITP 2.1, implémentations non CNAME)</p><p>/</p><p>Segment de mesures Visiteurs uniques + visiteurs non ITP (ITP 2.1, implémentations non CNAME)</p> |

{style="table-layout:auto"}
