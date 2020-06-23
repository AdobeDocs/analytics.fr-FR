---
description: Des FAQ relatives à la configuration automatique du déploiement d’Adobe Analytics. La méthode de configuration automatique gère le code AppMeasurement pour vous.
keywords: Dynamic Tag Management;plug-ins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: FAQ sur l’outil Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# FAQ sur l’outil Adobe Analytics

Des FAQ relatives à la configuration automatique du déploiement d’Adobe Analytics. La méthode de configuration automatique gère le code [!DNL AppMeasurement] pour vous.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Où placer mes plug-ins lors de la mise en œuvre d’Adobe Analytics via DTM ? </p> </td> 
   <td colname="col2"> <p> Si vous utilisez DTM pour héberger manuellement la variable <code> s_code</code>, vous pouvez ajouter des plug-ins dans le même éditeur que la variable <code> s_code</code> hébergée, simplement comme vous le feriez dans une mise en œuvre d’Adobe Analytics classique. </p> <p>Cependant, vous pouvez également placer les plug-ins logiciels dans l’éditeur dans la section <span class="term"> Personnalisation du code de page</span> des paramètres de l’outil. Les deux méthodes de mise en œuvre doivent être d’efficacité égale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si j’apporte des modifications de configuration dans la nouvelle version de l’outil, puis-je le tester lors de l’évaluation avant de le publier pour production ? </p> </td> 
   <td colname="col2"> <p>Oui. </p> <p>Toutes les modifications peuvent être testées lors de l’évaluation comme vous le feriez avant le déploiement dans un environnement de production. Si vous choisissez de ne pas publier car vous remarquez des problèmes lors de l’évaluation, le code de production continuera à fonctionner comme avant que la nouvelle intégration soit publiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si je passe de la configuration manuelle (le paramètre par défaut pour les outils existants) à la configuration automatique, mes paramètres actuels seront-ils affectés ? </p> </td> 
   <td colname="col2"> <p>Non. </p> </td> 
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

Reportez-vous à la section [Ajout de l’outil Adobe Analytics](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md) pour obtenir des informations de configuration.

## Pièges potentiels {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Il peut arriver, mais c’est très improbable, que l’intégration provoque des problèmes de collecte des données si vous utilisez actuellement [!DNL Adobe Analytics]. Ces problèmes pourraient survenir uniquement si vous publiez votre bibliothèque en production à la suite de la version. (Le code de production reste intact jusqu’à ce que la publication se produise.)

Pour éviter ces problèmes, assurez-vous que :

* Les identifiants de suites de rapports sont correctement saisis dans l’outil.
* Les identifiants de suites de rapports dans l’outil correspondent aux identifiants du code [!DNL AppMeasurement].
* Les champs de configuration du code de devise, du jeu de caractères, du serveur de suivi et du serveur de suivi SSL sont correctement définis avec des valeurs prises en charge.
* Le code personnalisé est défini dans [!DNL Library Management].

