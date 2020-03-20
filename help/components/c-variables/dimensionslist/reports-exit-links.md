---
title: Liens de sortie
description: Affichez un rapport sur les liens les plus courants sur lesquels les visiteurs cliquent pour quitter votre site.
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# Liens de sortie

Affiche les liens les plus courants sur lesquels les visiteurs cliquent pour quitter votre site. Ces liens renvoient généralement vers des sites partenaires ou affiliés ; toutefois, il peut s’agir de n’importe quel emplacement où vous disposez d’un lien externe. Vous pouvez utiliser ce rapport pour afficher les liens de sites affiliés les plus populaires ou faciliter la validation du nombre de renvois que vous fournissez, selon les indications de vos partenaires.

Il convient de respecter certaines exigences pour que cette page soit renseignée correctement :
* Si vous utilisez le suivi manuel des liens personnalisés, une `tl()` requête doit être déclenchée avec le paramètre du milieu défini sur `e`.
* Si vous utilisez le suivi automatique de liens personnalisés, toutes les exigences doivent être respectées :
   * La variable [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) doit être activée.
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* Si l’une des conditions ci-dessus n’est pas respectée, l’accès ne renseigne pas ce rapport.
* Comme pour tous les accès de suivi de liens personnalisés, la variable [pageName](/help/implement/vars/page-vars/pagename.md) est supprimée de la demande d’image afin d’éviter le gonflement vers la mesure  de la page.
* Ce rapport est visible en tant que rapport de tendance et avec classement.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Vous pouvez créer des  [ventilations](/help/analyze/reports-analytics/reports-customize/breakdowns.md) avec toute autre variable.
