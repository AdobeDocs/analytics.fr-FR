---
description: Les variables de trafic personnalisé, appelées également props (s.prop) ou variables de propriété, sont en réalité des compteurs qui comptabilisent le nombre de fois où chaque valeur est envoyée dans Analytics.
keywords: Analytics Implementation;Traffic prop;prop;conversion;evar;s.prop;custom conversion insight;traffic variable
title: Propriétés et eVars - Aperçu
topic: Developer and implementation
uuid: 522cab2b-1ef8-4f10-b216-c82b21431487
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Propriétés et eVars - Aperçu

Les variables de trafic personnalisé, appelées également props (s.prop) ou variables de propriété, sont en réalité des compteurs qui comptabilisent le nombre de fois où chaque valeur est envoyée dans Analytics.

Lorsque vous déterminez l’emplacement d’affectation des différentes variables, il importe de faire clairement la distinction entre les fonctionnalités Prop et eVar. Etre en mesure d’identifier ces différences permet à votre entreprise de déterminer le type de variable idéal à utiliser. Pour plus d’informations, voir [Comparaison des propriétés et des eVars](/help/implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md).

Les props vous permettent également de corréler des données personnalisées avec des événements de trafic spécifiques. Ces variables sont intégrées au code d’[!DNL Analytics] dans chaque page de votre site Web. Grâce aux variables [!UICONTROL s.prop], [!DNL Analytics] vous permet de créer des rapports personnalisés, propres aux objectifs de votre organisation, de votre industrie ou de votre entreprise.

Si vous êtes, par exemple, un fabricant automobile, il peut s’avérer intéressant de consulter le « Modèle de voiture le plus populaire » afin de compléter votre rapport « Pages ». Pour ce faire, vous pouvez allouer l’une de vos propriétés de trafic afin de représenter le modèle de voiture. Implémentez ensuite votre code pour transmettre le modèle de voiture sur les pages appropriées.

> [!NOTE] [!DNL Analytics] prend en charge jusqu’à 75 variables [!UICONTROL s.prop].

Les props sont utilisées dans les rapports de cheminement ou de corrélation. Vous pouvez, par exemple, utiliser des variables de [!UICONTROL propriété] pour afficher un type de contenu, une sous-section ou un nom du modèle. Les rapports [!UICONTROL Trafic personnalisé] obtenus présentent alors le type de contenu, la sous-section ou le modèle consulté le plus souvent.

Les variables de trafic personnalisées permettent de répondre à un nombre incalculable de questions, en fonction des éléments capturés sur votre site Web. La liste suivante présente quelques objectifs courants :

* Comprendre la navigation des utilisateurs sur le site Web
* Comprendre le comportement de recherche interne des utilisateurs
* Segmenter le trafic par navigation ou par catégorie
* Segmenter le comportement des visiteurs par données démographiques

Les eVars (ou variables d’[!UICONTROL aperçu de conversion personnalisée]) servent à identifier la contribution d’attributs ou d’actions spécifiques à des événements de succès sur votre site. Dans le cas d’un site de médias, par exemple, les eVars peuvent être utilisées pour identifier l’incidence des promotions internes sur le taux d’enregistrement des visiteurs. Lorsqu’un visiteur clique sur la promotion interne, une eVar peut être utilisée pour stocker un identifiant unique qui lui est associé. Lorsque le même visiteur procède à son enregistrement et qu’un événement de succès personnalisé est déclenché, l’identifiant unique d’origine reçoit du crédit pour l’événement d’enregistrement.

Sur un site de conversion, vous pouvez utiliser des eVars pour effectuer une comparaison entre les visiteurs connectés et non connectés en ce qui concerne l’exécution d’un achat. Lorsqu’un visiteur se connecte, une eVar est définie sur « connecté ». Lorsque ce même visiteur atteint la page de passage en caisse, l’événement correspondant se voit attribuer la valeur « connecté ». Lorsqu’un visiteur atteint la page de remerciement affichée après l’achat, la valeur « connecté » est attribuée aux produits et au montant des achats. Le rapport [!UICONTROL eVar personnalisée] obtenu affiche le nombre total de passages en caisse et de commandes pour les utilisateurs connectés et non connectés.

Pour plus d’informations, voir [Variable de trafic](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) dans l’aide et le document de référence d’Analytics.

Pour plus d’informations sur la configuration des propriétés dans Digital Tag Management, voir [Création d’une propriété web](/help/implement/c-implement-with-dtm/t-create-web-property.md).
