---
description: Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.
title: Questions fréquentes sur Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# Questions fréquentes sur Activity Map

Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.

+++Tous les clients Analytics ont-ils accès à la page dʼactivation dʼActivityMap dans les outils dʼadministration ?
Les entreprises ayant souscrit un contrat pour Adobe Analytics Standard, Premium et Ultimate ont accès à Activity Map.
+++

+++Comment Activity Map prend-il en charge les applications monopages (SPA) ?
Toutes les quelques secondes, Activity Map analyse la page Web à la recherche de modifications apportées à celle-ci. ActivityMap trouve du contenu nouveau sur la page sans avoir besoin de charger une nouvelle page. Cependant, ce nouveau contenu est toujours attribué au premier pageName trouvé lors du chargement de la page.

* Activity Map vérifie si la visibilité des liens qu’il connaît a changé. Si une modification de visibilité est trouvée, alors les liens de la page dans la colonne Présent du tableau sont mis à jour avec pour valeur [!UICONTROL Affiché] ou [!UICONTROL Masqué].

* Lorsqu’une interaction d’un utilisateur crée du contenu, tout nouvel élément détecté comme un lien par AppMeasurement sera ajouté au tableau [!UICONTROL Liens sur la page]. Activity Map envoie une nouvelle requête de données qui inclut ces nouveaux liens. Les nouveaux liens doivent apparaître dans le tableau [!UICONTROL Liens sur la page] lorsque la requête de données est traitée par l’interface utilisateur.
+++

+++Est-ce qu’Activity Map fournit des données sur les « vues » ?
Non, Adobe ne suit pas les liens qui ont été vus.
+++

+++Quels sont les navigateurs et les versions pris en charge par Activity Map ?
Activity Map prend en charge la dernière version de la plupart des navigateurs modernes.
+++

+++Activity Map augmente-t-il les appels au serveur ?
Activity Map nʼenvoie pas dʼappels au serveur par lui-même. En revanche, les variables de données contextuelles Activity Map sont incluses dans les appels de page vue Analytics sur la page suivante.
+++

+++Pourquoi les superpositions de certains éléments avec classement sont-elles manquantes ?
Certains liens avec classement, tels que les liens de sous-menu, sont masqués de la page. Par conséquent, les chevauchements de lien correspondants ne sʼaffichent pas. Le classement est calculé pour tous les liens de la page, y compris les liens masqués.
+++

+++Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?**
* **En mode dégradé et bulle** : le classement est déterminé par la colonne de mesures. Pour les liens disposant de la même valeur de mesure, le classement est déterminé selon l’ordre alphabétique des ID de lien.
* **En mode gagnant et perdant** : le classement est principalement déterminé par la colonne de pourcentage de gain. Pour les liens disposant du même gain, le classement est déterminé selon lʼordre alphabétique des ID de lien.
+++

+++Comment Activity Map fonctionne-t-il avec les pages qui utilisent plusieurs suites de rapports ?
Par défaut, Activity Map utilise la suite de rapports associée à la première balise envoyée par la page. Vous pouvez sélectionner une suite de rapports balisée différente dans l’onglet **[!UICONTROL Paramètres d’Activity Map]** > **[!UICONTROL Autres]**.
+++

+++Combien de temps Activity Map recherche-t-il Adobe Analytics sur la page ?
Activity Map recherche la présence dʼAdobe Analytics pendant 20 secondes au maximum après un événement de fin de page.
+++

+++Comment Activity Map gère-t-il le contenu dynamique ?
Activity Map vérifie toutes les 2 secondes si des changements ont été apportés à lʼétat de la page web, par exemple :

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou visible, l’application modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à visible ou de visible à masqué. Si du nouveau contenu a été injecté, lʼapplication récupère les liens associés et les données dʼanalyse correspondantes et ajoute des superpositions pour ces liens.
+++

+++Sur quelle mesure se base le rapport Flux de page ?
Toutes les données affichées se basent sur les pages vues.
+++

+++Puis-je exporter des variables de données contextuelles Activity Map par le biais du flux de données ?
Oui. Les [Colonnes de données](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) que les utilisateurs Activity Map utilisent sont `clickmaplink`, `clickmaplinkbyregion`, `clickmappage`, et `clickmapregion`.
+++

+++Les segments fonctionnent-ils en mode Live ?
Non, les segments ne fonctionnent pas en mode réel.
+++

+++Activity Map est-il compatible avec les suites de rapports virtuelles ?
Oui. Cependant, en raison des limitations des suites de rapports virtuelles, le mode réel d’Activity Map n’est pas compatible avec celles-ci.
+++

+++Comment puis-je désactiver Activity Map ?
Vous disposez de trois options :

* Supprimez la fonction `AppMeasurement_Module_ActivityMap` à partir du fichier JS.
* Ajoutez un code personnalisé qui réécrit la fonction ci-dessus avec un corps vide, par exemple :

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* Configurez AppMeasurement en définissant `s.trackClickMap` et `s.trackInlineStats` sur `false`.
+++
