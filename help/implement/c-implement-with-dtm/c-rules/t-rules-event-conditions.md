---
description: Les conditions déterminent à quel moment une règle basée sur un événement est déclenchée.
keywords: Gestion dynamique des balises ; rule ; créer une règle ; nouvelle règle ; règle basée sur un événement ; différer l'activation du lien ; apply event handler directly to element ; bubbling ; propagation d'événements
seo-description: Les conditions déterminent à quel moment une règle basée sur un événement est déclenchée.
seo-title: Création de conditions pour les règles basées sur un événement
solution: Marketing Cloud, Analytics, Target, gestion dynamique des balises
title: Création de conditions pour les règles basées sur un événement
uuid: a 847391 c -5 aec -4 d 64-8 a 35-388587731598
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Création de conditions pour les règles basées sur un événement

Les conditions déterminent à quel moment une règle basée sur un événement est déclenchée.

1. Sélectionnez le type d’interaction dont vous souhaitez effectuer le suivi (clics de souris ou envois de formulaire, par exemple).  

   ![](assets/condition-event-based.png)

   Pour plus d’informations, voir [Types d’événements](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html) dans la documentation du produit Tag Management d’Adobe.

1. Activez les options suivantes si besoin est :

   | Élément | Description |
   |--- |--- |
   | Différer l’activation du lien | Activez cette option si l’événement active un lien et si vous souhaitez retarder le lien afin que l’événement ait suffisamment de temps pour se déclencher. |
   | Appliquer directement le gestionnaire d’événements à l’élément | Permet d’appliquer le gestionnaire d’événements à l’élément spécifique qui est ciblé. Ce paramètre est lié au concept de propagation d’événements et de couche dans un navigateur. |

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. An event like a click can potentially bubble up to `<body>`. Il est important de comprendre la liaison actuelle de l’événement et de cibler spécifiquement ce dernier pour s’assurer du déclenchement correct de la règle.

   La *propation d’événements* signifie que l’événement est d’abord capturé et géré par l’élément interne puis propagé vers les éléments externes.

1. Indiquez le nom de la balise dont vous souhaitez effectuer le suivi et les autres propriétés de la balise que vous souhaitez faire correspondre.  

   ![](assets/condition-event-based2.png)

   Voir [Utilisation du sélecteur CSS](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html) dans la documentation du produit Dynamic Tag Management pour plus d’informations sur la détermination de la balise d’élément appropriée.

1. Sélectionnez d’autres types de condition ou de critère à lier à la règle, puis configurez-les.

   ![](assets/condition-event-based3.png)

1. Indiquez vos préférences concernant la propagation d’événements.

   La propagation d’événements est un moyen de propager les événements dans le modèle DOM HTML.

   | Si vous... | Activez cette option |
   |--- |--- |
   | Vous souhaitez que les interactions liées sur les éléments enfants du sélecteur de règles que vous avez identifié déclenchent la règle. | Autoriser la propagation des événements sur les éléments enfants . |
   | Vous souhaitez empêcher la propagation d’événements lorsque l’élément enfant déclenche déjà son propre événement. | Ne pas autoriser si l’élément enfant déclenche déjà un événement. |
   | Vous ne souhaitez pas que les événements du sélecteur de règles que vous avez identifié dépassent l’élément dans la hiérarchie des événements. | Ne pas autoriser la propagation des événements vers les parents. |
