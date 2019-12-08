---
description: Le tableau ci-après contient la liste des tâches que vous devez effectuer pour migrer votre implémentation.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
subtopic: JavaScript AppMeasurement
title: Migration vers AppMeasurement pour JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Migration vers AppMeasurement pour JavaScript

Le tableau ci-après contient la liste des tâches que vous devez effectuer pour migrer votre implémentation.

>[!NOTE]
>
>Nous vous recommandons de migrer vers le [service d’identité](/help/implement/js-implementation/c-unique-visitors/visid-service.md) lorsque vous migrez vers [!DNL AppMeasurement] pour JavaScript.

![](assets/step1_icon.png) Vérifier la compatibilité des modules externes

Où : s\_code.js

Certains modules externes ne sont plus pris en charge. Reportez-vous à la section [Prise en charge des modules externes dans AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

![](assets/step2_icon.png) Télécharger la nouvelle bibliothèque AppMeasurement

Où : Admin &gt; Gestionnaire de code

Le fichier .zip de téléchargement contient une version réduite du fichier AppMeasurement.js et les fichiers JavaScript pour les modules Media et Integrate.

![](assets/step3_icon.png) Copiez votre personnalisation de s\_code.js dans le fichier `AppMeasurement.js`.

Où : s\_code.js et AppMeasurement.js

Déplacez le code situé au-dessus de la section `DO NOT ALTER ANYTHING BELOW THIS LINE` du fichier s\_code.js au début du fichier AppMeasurement.js.

![](assets/step4_icon.png) (Facultatif) Mettre à jour les modules externes

Où : AppMeasurement.js

Si vous utilisez le module externe getQueryParam, mettez à jour ces appels afin d’avoir recours au nouvel utilitaire, [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

![](assets/step5_icon.png) (Facultatif) Mettre à jour les modules Media et Integrate

Où : AppMeasurement.js

Si vous utilisez un de ces modules, copiez le code du fichier AppMeasurement\_Module\_Media.js et/ou du fichier AppMeasurement\_Module\_Integrate.js et collez-le avant la section `DO NOT ALTER ANYTHING BELOW THIS LINE` du fichier AppMeasurement.js.

![](assets/step6_icon.png) Déployer le nouveau ficher JavaScript

Où : votre site web

Le nouveau ficher JavaScript peut être déployé selon votre processus standard. Le code de page existant est compatible avec la nouvelle version.
