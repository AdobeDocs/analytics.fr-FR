---
title: Fin de vie de la fonction [!UICONTROL Exiger des restrictions d’identification par IP]
description: Découvrez la date de fin de vie de la fonction [!UICONTROL Exiger des restrictions d’identification par IP] et les répercussions à attendre.
translation-type: ht
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# Fin de vie de la fonction [!UICONTROL Exiger des restrictions d’identification par IP]

La fonction **[Exiger des restrictions d’identification par IP](/help/admin/company/security-manager.md)**dans Adobe Analytics vous permet de mettre certaines adresses IP (considérées comme sécurisées) sur liste blanche afin d’assurer la connexion et l’accès à votre environnement Adobe Analytics. Dans de nombreux cas, cette fonctionnalité est utilisée pour configurer une adresse IP d’entreprise comme la seule adresse IP sécurisée à partir de laquelle les utilisateurs peuvent se connecter. Par conséquent, pour utiliser Adobe Analytics, les utilisateurs doivent se trouver dans un bureau d’entreprise ou se connecter au réseau via VPN.

Nous prévoyons de mettre fin à cette fonctionnalité en octobre 2020.

## Pourquoi cette fonctionnalité est-elle abandonnée ?

Cette fonctionnalité est parfois non fonctionnelle en raison de la migration de la connexion à Experience Cloud et/ou par la connexion à Experience Cloud. Elle fonctionne généralement mal pour les clients qui utilisent les **[!UICONTROL Attributs du client]** ou la **[!UICONTROL Bibliothèque d’audiences]**.

De plus, si vous possédez plusieurs solutions Experience Cloud, vous pouvez contourner cette exigence en vous connectant à Experience Cloud avec l’une des autres solutions, car cette fonctionnalité n’existe pas ou n’est pas prise en charge en dehors d’Analytics. Les utilisateurs peuvent également contourner ce problème en usurpant les adresses IP.

Enfin, Adobe propose une solution alternative fonctionnelle et bien plus performante via l’authentification unique et les identifiants fédérés (Federated ID). Cette fonctionnalité vous permet de mieux contrôler et sécuriser l’expérience de connexion de vos utilisateurs. Plus d’informations ci-dessous.

## En quoi la suppression de cette fonction vous concerne-t-elle ?

Pour tous les clients qui ont configuré la fonction **[!UICONTROL Exiger des restrictions d’identification par IP]**, celle-ci sera supprimée en octobre 2020. À ce moment-là, les restrictions d’identification par IP toujours en vigueur ne seront plus appliquées. Si vous devez encore limiter la connexion par adresse IP, vous devez examiner et mettre en œuvre une solution recommandée : l’authentification unique ou Federated ID (plus d’informations et de ressources ci-dessous).

En outre, le paramètre **[!UICONTROL Exiger des restrictions d’identification par IP]** sera supprimé de **[!UICONTROLAAdmin > Paramètres de la société > Gestionnaire de sécurité]** dans l’interface utilisateur d’Analytics (comme illustré ci-dessous).

![](assets/sec-manager2.png)

## Quelles sont les autres options ?

Comme indiqué ci-dessus, cette fonction d’Analytics est en passe d’être abandonnée. Afin de vous donner le temps de mettre en œuvre l’authentification unique et Federated ID, nous avons reporté la date de fin de vie à octobre 2020.

L’authentification unique et Federated ID sont des solutions plus performantes par rapport à la fonctionnalité de restriction d’identification par IP que nous avons en place aujourd’hui et vous apporteront plus de contrôle, de sécurité et de fonctionnalités. Pour plus d’informations sur la configuration de l’authentification unique ou de Federated ID, la documentation suivante est susceptible de vous aider. Nous vous recommandons de la lire attentivement et de prendre contact avec votre service informatique pour les mettre en œuvre :

* [Authentification unique et Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console : documentation sur la configuration des identités](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html)
* [Admin Console : tutoriel sur la configuration des identités (vidéo)](https://helpx.adobe.com/fr/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Tutoriel de configuration de Federated ID (vidéo)](https://helpx.adobe.com/fr/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Authentification unique : questions fréquentes](https://helpx.adobe.com/fr/enterprise/using/sso-faq.html)
* [Types d’identité pris en charge par Adobe](https://helpx.adobe.com/fr/enterprise/using/identity.html)

Si vous souhaitez continuer à montrer votre soutien envers cette fonctionnalité et demander à ce qu’elle reste disponible sur Experience Cloud, vous pouvez voter pour elle sur notre [Forum](https://forums.adobe.com/ideas/11648).