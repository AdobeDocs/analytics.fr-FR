---
description: Affiche les moyennes des mesures du groupe de rapports des campagnes. Les mesures par défaut sont les clics publicitaires, les ventes totales, les commandes et les recettes.
title: Entonnoir de conversion de campagne
topic: Reports
uuid: b0a90917-e4c7-40da-854e-58649de09742
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Entonnoir de conversion de campagne

Affiche les moyennes des mesures du groupe de rapports des campagnes. Les mesures par défaut sont les clics publicitaires, les ventes totales, les commandes et les recettes.

**[!UICONTROL Campagnes]** &gt; **[!UICONTROL Entonnoir de conversion de campagne]**

Le haut d’un graphique en forme d’entonnoir affiche les données de conversion. La partie inférieure affiche les statistiques pour tous les événements de la zone du haut, en fonction des commandes et éventuellement de deux autres mesures : recettes et unités.

Gardez ces informations à l’esprit lorsque vous interprétez les données d’entonnoir de conversion :

* Les statistiques relatives aux périodes actuelles peuvent ne pas être complètes lorsque vous affichez les données, ce qui peut affecter les tendances par rapport à un jour précédent.
* Quand aucun filtre n’est appliqué à l’entonnoir, la mesure Visites représente les visites de conversion ou les visites pendant lesquelles la variable de campagne, toute variable eVar ou un événement de succès a été déclenché. Les visites pendant lesquelles aucune de ces propriétés n’a été transmise ne sont pas incluses dans ce total.
* Lorsqu’un filtre est appliqué à l’entonnoir, la mesure Visites représente les instances (ou clics publicitaires). Cette valeur correspond au nombre total de fois où la variable donnée a été renseignée par les utilisateurs sur votre site, à l’exclusion des instances qui ne remplissent pas les critères du filtre. Une visite unique peut impliquer plusieurs instances.
* Il est possible que des niveaux plus détaillés de l’entonnoir signalent des chiffres plus élevés que les niveaux de surface. Vous pouvez par exemple voir plus de commandes que de clics publicitaires, ou plus de passages en caisse que de consultations de produits. Un certain nombre de raisons peuvent expliquer cette situation :

   * Vous avez plus de commandes que de clics publicitaires si la variable Code de suivi est définie pour une longue durée de vie du cookie (un mois, par exemple) et si les utilisateurs n’utilisent qu’un seul clic publicitaire, mais reviennent plusieurs fois et passent plusieurs commandes pendant la période antérieure à l’expiration de la valeur Code de suivi.
   * Vous avez plus de passages en caisse que de consultations de produits si l’utilisateur peut ignorer la page d’affichage du produit (comme dans le cas d’une vente par montée en gamme) ou s’il peut enregistrer son panier et revenir ultérieurement pour terminer sa commande. Si la consultation de produit est survenue avant la plage de dates sélectionnée et que le passage en caisse survient après, vous voyez un passage en caisse et aucune consultation de produit. Si vous constatez une divergence, cela n’indique pas un problème dans la création de rapports, ni même une erreur de mise en œuvre. Vous pouvez, à la place, utiliser ces données pour comprendre comment les utilisateurs interagissent avec votre site, même si cela ne correspond pas à l’entonnoir que vous espériez.

