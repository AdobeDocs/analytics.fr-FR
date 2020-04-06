---
description: Groupe de rapports basé sur le chemin d’accès  . Techniquement, le cheminement signifie passer d’un nom de page à un autre (d’une valeur à une autre).
title: Cheminement
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Cheminement

Groupe de rapports basé sur le chemin d’accès  . Techniquement, le cheminement signifie passer d’un nom de page à un autre (d’une valeur à une autre).

Utilisez le [Flux d’Analysis Workspace](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/flow.html) pour des options de cheminement souples.

>[!NOTE] Pour activer le cheminement, accédez à **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**. Pour activer le cheminement pour les rapports Section Site et Serveur, contactez le service à la clientèle.

Si vous devez connaître l’ordre dans lequel les valeurs sont collectées, vous devez activer le cheminement pour la variable qui collecte ces valeurs. Le cheminement est activé par défaut pour les pages. Par défaut, le cheminement n’est activé pour aucune props, car il n’est approprié que dans certains cas. Contactez le service à la clientèle pour activer le cheminement sur une prop.

>[!NOTE] Dans les Ad Hoc Analysis, lorsque vous activez des classifications sur une prop, les mesures de cheminement sont disponibles pour l’ensemble des classifications configurées.

**Exemple - Cheminement sur les sections de site**

L’activation du cheminement pour la variable  *`s.channel`* vous permet de suivre le mode de déplacement des visiteurs entre les différentes sections de votre site (à mesure que la valeur change).

![](assets/path_sections.png)

Le cheminement est ensuite disponible dans divers rapports de chemins, tels que [!UICONTROL Next Site Section Flow], qui indique comment les se déplacent dans des groupes de pages ou des sections de votre site.

![](assets/paths_report.png)

**Exemple - Cheminement sur les recherches**

Le concept de déplacement entre plusieurs valeurs s’applique également à d’autres variables de trafic, dont  *`s.props`*. Si vous activez, par exemple, le cheminement pour votre terme de recherche interne *`s.prop`*, vous pouvez visualiser le chemin emprunté par les visiteurs via les termes de recherche.

**Exemple - Cheminement par état de connexion**

Vous souhaitez peut-être savoir comment les visiteurs parcourent votre site en fonction de l’état de connexion  du. Pour afficher ces informations, vous ne devez pas consulter les rapports de cheminement pour connaître l’état de connexion, car ils indiquent comment les ont modifié les valeurs de ce rapport, ni comment les ont pu changer du statut de connexion à celui de déconnecté. Concaténez plutôt la valeur du segment avec la variable  *`s.pageName`* puis tracez la variable obtenue. Voici un exemple de code de cheminement de page par état de membre :

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

Activez ensuite le cheminement pour que la variable  *`s.prop19`* visualise le cheminement des membres à travers les différentes pages.

>[!NOTE] Si vous effectuez des Ad Hoc Analysis, vous pouvez segmenter les chemins de page sans avoir à concaténer des valeurs de segment et appliquer tout segment à des rapports de cheminement.

