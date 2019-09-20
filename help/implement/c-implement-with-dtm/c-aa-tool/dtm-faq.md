---
description: Des FAQ relatives à la configuration automatique du déploiement d’Adobe Analytics. La méthode de configuration automatique gère le code AppMeasurement pour vous.
keywords: Gestion dynamique des balises;modules externes;test;effet sur les paramètres actuels;historique des révisions;risques potentiels;ID de suite de rapports;code de devise;serveur de suivi;serveur de suivi ssl;code personnalisé;gestion de bibliothèque
seo-description: Des FAQ relatives à la configuration automatique du déploiement d’Adobe Analytics. La méthode de configuration automatique gère le code AppMeasurement pour vous.
seo-title: FAQ sur l’outil Adobe Analytics
solution: Experience Cloud,Analytics,Target,Gestion dynamique des balises
title: FAQ sur l’outil Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# FAQ sur l’outil Adobe Analytics

Des FAQ relatives à la configuration automatique du déploiement d’Adobe Analytics. The automatic configuration method manages the [!DNL AppMeasurement] code for you.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Où placer mes modules logiciels enfichables lors de l’implémentation d’Adobe Analytics via la gestion dynamique des balises ? </p> </td> 
   <td colname="col2"> <p> Si vous utilisez la gestion dynamique des balises pour héberger manuellement la variable <code>s_code</code>, vous pouvez ajouter des modules logiciels enfichables dans le même éditeur que la variable <code>s_code</code> hébergée, simplement comme vous le feriez dans une implémentation d’Adobe Analytics classique. </p> <p>Cependant, vous pouvez également placer les modules externes dans l’éditeur dans la section <span class="term"> Personnaliser le code</span> de page des paramètres de l’outil. Les deux méthodes d’implémentation doivent être d’efficacité égale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si j’apporte des modifications de configuration dans la nouvelle version de l’outil, puis-je le tester lors de l’évaluation avant de le publier pour production ? </p> </td> 
   <td colname="col2"> <p>Oui. </p> <p>Toutes les modifications peuvent être testées lors de l’évaluation comme vous le feriez avant le déploiement dans un environnement de production. Si vous choisissez de ne pas publier car vous remarquez des problèmes lors de l’évaluation, le code de production continuera à fonctionner comme avant que la nouvelle intégration soit publiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si je passe de la configuration manuelle (le paramètre par défaut pour les outils existants) à la configuration automatique, mes paramètres actuels seront-ils affectés ? </p> </td> 
   <td colname="col2"> <p>Non.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si je passe de la gestion manuelle de la bibliothèque à l’option Géré par Adobe, mes paramètres ou mon code actuel sera-t-il affecté ? </p> </td> 
   <td colname="col2"> <p>Tout code utilisateur que vous avez indiqué est remplacé par la bibliothèque <span class="keyword">AppMeasurement</span> de base. Vous devez déplacer ce code vers la nouvelle section <span class="wintitle">Code de page personnalisé</span> à la fin de la configuration de l’outil afin que le code continue à s’exécuter. Cette méthode permet de gérer (et de mettre à niveau) la bibliothèque <span class="keyword">AppMeasurement</span> séparément du code personnalisé de l’utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>L’historique des révisions de l’outil <span class="keyword">Adobe Analytics</span> est-il conservé lorsque la nouvelle intégration est publiée ? </p> </td> 
   <td colname="col2"> <p>Oui. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Add Adobe Analytics Tool](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8) for configuration information.

## Pièges potentiels {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Il peut arriver, mais c’est très improbable, que l’intégration provoque des problèmes de collecte des données si vous utilisez actuellement [!DNL Adobe Analytics]. Ces problèmes pourraient survenir uniquement si vous publiez votre bibliothèque en production à la suite de la version. (Le code de production reste intact jusqu’à ce que la publication se produise.)

Pour éviter ces problèmes, assurez-vous que :

* Les identifiants de suites de rapports sont correctement saisis dans l’outil.
* Les identifiants de suites de rapports dans l’outil correspondent aux identifiants du code [!DNL AppMeasurement].
* Les champs de configuration du code de devise, du jeu de caractères, du serveur de suivi et du serveur de suivi SSL sont correctement définis avec des valeurs prises en charge.
* Le code personnalisé est défini dans [!DNL Library Management].

