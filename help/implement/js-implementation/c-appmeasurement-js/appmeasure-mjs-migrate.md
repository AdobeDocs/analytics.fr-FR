---
description: Le tableau ci-après contient la liste des tâches que vous devez effectuer pour migrer votre implémentation.
keywords: Implémentation d'Analytics ; appmeasurement ; migrer ; migration ; javascript
seo-description: Le tableau ci-après contient la liste des tâches que vous devez effectuer pour migrer votre implémentation.
seo-title: 'Migration vers AppMeasurement pour JavaScript '
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Migration vers AppMeasurement pour JavaScript
topic: Développeur et mise en œuvre
uuid: 5 be 345 a 8-5 a 95-4176-a 2 e 6-97139 b 9 b 46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migration vers AppMeasurement pour JavaScript

Le tableau ci-après contient la liste des tâches que vous devez effectuer pour migrer votre implémentation.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Vérifier la compatibilité des modules externes

Où : s\_ code. js

Certains modules externes ne sont plus pris en charge. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) Télécharger la nouvelle bibliothèque AppMeasurement

Où : Admin &gt; Gestionnaire de code

Le fichier .zip de téléchargement contient une version réduite du fichier AppMeasurement.js et les fichiers JavaScript pour les modules Media et Integrate.

![](assets/step3_icon.png) Copiez la personnalisation s\_ code. js dans `AppMeasurement.js`.

Où : s\_ code. js et appmeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Facultatif) Mettre à jour les modules externes

Où : Appmeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Facultatif) Mettre à jour les modules Media et Integrate

Où : Appmeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Déployer le nouveau ficher JavaScript

Où : Votre site Web

Le nouveau ficher JavaScript peut être déployé selon votre processus standard. Le code de page existant est compatible avec la nouvelle version.