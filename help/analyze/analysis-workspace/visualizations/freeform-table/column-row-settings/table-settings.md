---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Tableaux à structure libre
role: Business Practitioner, Administrator
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '392'
ht-degree: 100%

---

# Paramètres des lignes

Les configurations des lignes varient selon le composant déposé dans le tableau. Pour accéder aux paramètres de ligne d’un tableau, cliquez sur l’icône Paramètres en regard d’une dimension, d’un segment, d’une mesure, d’une période ou d’une ventilation :

![](assets/row-settings.png)

| Paramètre | Description |
|--- |--- |
| Alignement des dates | Il s’agit d’un paramètre au niveau du tableau qui aligne les dates de chaque colonne afin qu’elles commencent toutes à partir de la même ligne. L’alignement des dates est activé par défaut lorsqu’une dimension temporelle est utilisée dans les lignes du tableau et que différentes périodes sont appliquées dans les colonnes. Par exemple, dans un tableau quotidien auquel les colonnes d’octobre et de septembre sont appliquées, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre. |
| Ventilation par position | Par défaut, ce paramètre est désactivé et les ventilations sont fixées aux éléments de la ligne statique. Par exemple, imaginons que vous ventilez les éléments de dimension des 3 premières pages (page d’accueil, résultats de recherche et passage en caisse) par canal marketing. Ensuite, vous quittez le projet et revenez deux semaines plus tard. Lors de la réouverture du projet, les 3 premières pages ont changé. Désormais, la page d’accueil, les résultats de recherche et le passage en caisse figurent sur les 4 à 6 premières pages. Par défaut, les ventilations des canaux marketing apparaîtront toujours sous la page d’accueil, les résultats de recherche et le passage en caisse, même si elles se trouvent maintenant dans les lignes 4 à 6. <br> En revanche, la **ventilation par position** répartit toujours les 3 premiers éléments, quelle que soit leur nature. Pour revenir à notre exemple, lorsque vous rouvrez votre projet, les ventilations des canaux marketing sont liées aux 3 premières pages du tableau, et non à la page d’accueil, aux résultats de recherche et au passage en caisse qui se trouvent maintenant dans les lignes 4 à 6. |
| Pourcentages | **Calculer les pourcentages par colonne** est le paramètre par défaut. Les pourcentages visibles dans une colonne sont calculés en fonction du total de la colonne. <br>**Calcul des pourcentages par ligne** oblige le tableau à structure libre à calculer les pourcentages des cellules par ligne, et non pas par colonne, avec le total général comme dénominateur. Cette fonctionnalité est particulièrement utile pour les pourcentages de tendance. Ce paramètre est activé par défaut lors de l’utilisation de l’icône Visualiser. |
| Totaux des colonnes | Ces paramètres sont uniquement disponibles pour les lignes [statiques](manual-vs-dynamic-rows.md). <br> **Afficher comme somme des lignes actuelles** affiche la somme des lignes du tableau côté client, ce qui signifie que le total ne dédupliquera *pas* de mesures telles que les visites ou les visiteurs. <br> **Afficher le total général** indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures. |
