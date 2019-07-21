---
description: Les Téléchargements de fichiers vous permettent de comprendre la fréquence à laquelle les visiteurs téléchargent des fichiers de votre site. Ces fichiers téléchargés sont, par exemple, des documents de traitement de texte, des feuilles de calcul, des fichiers audio, des fichiers de film, des manuels d’utilisation, etc. Ce rapport contient les fichiers enregistrés et ouverts directement à partir du navigateur, ainsi que ceux enregistrés sur l’ordinateur de l’utilisateur. Le rapport mentionne le nom du fichier en cours de téléchargement et l’URL complète d’accès à ce fichier.
seo-description: Les Téléchargements de fichiers vous permettent de comprendre la fréquence à laquelle les visiteurs téléchargent des fichiers de votre site. Ces fichiers téléchargés sont, par exemple, des documents de traitement de texte, des feuilles de calcul, des fichiers audio, des fichiers de film, des manuels d’utilisation, etc. Ce rapport contient les fichiers enregistrés et ouverts directement à partir du navigateur, ainsi que ceux enregistrés sur l’ordinateur de l’utilisateur. Le rapport mentionne le nom du fichier en cours de téléchargement et l’URL complète d’accès à ce fichier.
seo-title: Téléchargements de fichiers
solution: Analytics
title: Téléchargements de fichiers
topic: Présentation
uuid: 897 fc 221-aa 30-4 eac-aca 6-bccb 76 adaf 71
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Téléchargements de fichiers

Les Téléchargements de fichiers vous permettent de comprendre la fréquence à laquelle les visiteurs téléchargent des fichiers de votre site. Ces fichiers téléchargés sont, par exemple, des documents de traitement de texte, des feuilles de calcul, des fichiers audio, des fichiers de film, des manuels d’utilisation, etc. Ce rapport contient les fichiers enregistrés et ouverts directement à partir du navigateur, ainsi que ceux enregistrés sur l’ordinateur de l’utilisateur. Le rapport mentionne le nom du fichier en cours de téléchargement et l’URL complète d’accès à ce fichier.

**Navigation**

**[!UICONTROL Rapports]** &gt; **[!UICONTROL Contenu du site]** &gt; **[!UICONTROL Liens]** &gt; Téléchargements **[!UICONTROL de fichiers]**

Si ce rapport n’est pas disponible à l’emplacement par défaut, contactez vos administrateurs. Ils ont peut-être modifié la structure de menus par défaut pour mieux l’adapter aux besoins de votre entreprise.

Utilisez ce rapport pour :

* Savoir quels fichiers sont téléchargés le plus souvent de votre site.
* Déterminer si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Vérifier que tous les formats d’un document donné sont nécessaires.

   Par exemple, vous êtes peut-être en train de traduire vos manuels d’utilisation en douze langues pour les rendre disponibles sur votre site web. Grâce aux rapports de téléchargement de fichiers, vous connaissez la fréquence de téléchargement de chaque version des manuels d’utilisation et vous savez s’il est utile de continuer à traduire les manuels d’utilisation dans les douze langues.

**Résolution des incidents**

Les rapports marketing capturent des informations sur les fichiers téléchargés depuis toute page de votre site qui contient du code JavaScript. Cependant, certaines variables doivent être présentes et définies correctement pour qu’il soit possible de générer des rapports sur les téléchargements de fichiers. Si ce rapport ne contient aucune donnée, ou ne présente pas les valeurs attendues, procédez comme suit pour valider votre implémentation.

1. Recherchez le fichier JavaScript global sur votre site. Il se nomme généralement [!DNL s_code.js], à moins qu’il n’ait été renommé. If it has been renamed, you can search the JavaScript files on your site for the value *`s.account`*, which is a part of the JavaScript code.

1. Recherchez ensuite la variable [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackdownllinks) dans le fichier. Assurez-vous qu’elle est définie sur *true*.

1. Recherchez la variable [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkdownfiletypes). Assurez-vous que la liste contient toutes les extensions de fichier souhaitées. If necessary, add missing extensions like [!DNL .zip], [!DNL .pdf], and so on.)

Si le rapport [!UICONTROL Téléchargements de fichiers] ne reçoit toujours pas de données, alors que les variables vous semblent correctement configurées, invitez les utilisateurs de votre société ayant souscrit un contrat dédié à contacter le service d’assistance clientèle.
