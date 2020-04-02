---
description: Les Téléchargements de fichiers vous permettent de comprendre la fréquence à laquelle les visiteurs téléchargent des fichiers de votre site. Ces fichiers téléchargés sont, par exemple, des documents de traitement de texte, des feuilles de calcul, des fichiers audio, des fichiers de film, des manuels d’utilisation, etc. Ce rapport contient les fichiers enregistrés et ouverts directement à partir du navigateur, ainsi que ceux enregistrés sur l’ordinateur de l’utilisateur. Le rapport mentionne le nom du fichier en cours de téléchargement et l’URL complète d’accès à ce fichier.
title: Téléchargements de fichiers
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Téléchargements de fichiers

Les Téléchargements de fichiers vous permettent de comprendre la fréquence à laquelle les visiteurs téléchargent des fichiers de votre site. Ces fichiers téléchargés sont, par exemple, des documents de traitement de texte, des feuilles de calcul, des fichiers audio, des fichiers de film, des manuels d’utilisation, etc. Ce rapport contient les fichiers enregistrés et ouverts directement à partir du navigateur, ainsi que ceux enregistrés sur l’ordinateur de l’utilisateur. Le rapport mentionne le nom du fichier en cours de téléchargement et l’URL complète d’accès à ce fichier.

**Navigation**

**[!UICONTROL Rapports]** > **[!UICONTROL Contenu du site]** > **[!UICONTROL Liens]** > **[!UICONTROL Téléchargements de fichiers]**

Si ce rapport n’est pas disponible à l’emplacement par défaut, contactez vos administrateurs. Ils ont peut-être modifié la structure de menus par défaut pour mieux l’adapter aux besoins de votre entreprise.

Utilisez ce rapport pour :

* Savoir quels fichiers sont téléchargés le plus souvent de votre site.
* Déterminer si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Vérifier que tous les formats d’un document donné sont nécessaires.

   Par exemple, vous êtes peut-être en train de traduire vos manuels d’utilisation en douze langues pour les rendre disponibles sur votre site web. Grâce aux rapports de téléchargement de fichiers, vous connaissez la fréquence de téléchargement de chaque version des manuels d’utilisation et vous savez s’il est utile de continuer à traduire les manuels d’utilisation dans les douze langues.

**Résolution des problèmes**

Les rapports marketing capturent des informations sur les fichiers téléchargés depuis toute page de votre site qui contient du code JavaScript. Cependant, certaines variables doivent être présentes et définies correctement pour qu’il soit possible de générer des rapports sur les téléchargements de fichiers. Si ce rapport ne contient aucune donnée, ou ne présente pas les valeurs attendues, procédez comme suit pour valider votre implémentation.

1. Recherchez le fichier JavaScript global sur votre site. Il se nomme généralement [!DNL s_code.js], à moins qu’il n’ait été renommé. S’il a été renommé, vous pouvez rechercher la valeur *`s.account`* dans les fichiers JavaScript de votre site. Cette valeur fait partie du code JavaScript.

1. Recherchez ensuite la variable [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html) dans le fichier. Assurez-vous qu’elle est définie sur *true*.

1. Recherchez la variable [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html). Assurez-vous que la liste contient toutes les extensions de fichier souhaitées. Au besoin, ajoutez les extensions manquantes, telles que [!DNL .zip], [!DNL .pdf], etc.)

Si le rapport [!UICONTROL Téléchargements de fichiers] ne reçoit toujours pas de données, alors que les variables vous semblent correctement configurées, invitez les utilisateurs de votre société ayant souscrit un contrat dédié à contacter le service d’assistance clientèle.
