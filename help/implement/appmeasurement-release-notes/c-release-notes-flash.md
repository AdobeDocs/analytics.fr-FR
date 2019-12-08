---
description: Notes de mise à jour cumulées pour Flash. Les applications Flash qui utilisent ActionScript peuvent être mesurées sur le poste de travail et sur le web.
subtopic: Release notes
title: Flash-Flex
topic: Developer and implementation
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Flash-Flex{#flash-flex}

Notes de mise à jour cumulées pour Flash. Les applications Flash qui utilisent ActionScript peuvent être mesurées sur le poste de travail et sur le web.

> [!NOTE] Pour connaître la version de la bibliothèque actuelle, activez la journalisation du débogage.

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## 20 avril 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**Version 4.0.3**

* Inclusion de l’API visiteur version 1.6.1.

## 18 août 2016 {#section_D72EF20672174249B864997905D7552A}

**4.0.2 - Mise à jour**

Inclusion de l’API visiteur version 1.6.0.

## jeudi 19 mai 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

**4.0.1 - Mise à jour**

Inclusion de l’API visiteur version 1.5.6

## jeudi 21 avril 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe a publié une [mise à jour de sécurité APSB16-13 ](https://helpx.adobe.com/security/products/analytics/apsb16-13.html)pour la bibliothèque [!DNL AppMeasurement] pour Flash. Cette mise à jour corrige une faille de sécurité dans la bibliothèque, survenant uniquement lorsque `debugTracking` est activé, qui pourrait être exploitée pour mener [des attaques XSS basées sur le DOM](https://www.owasp.org/index.php/DOM_Based_XSS).

>[!IMPORTANT]
>
>Ce problème affecte uniquement [!DNL AppMeasurement] pour Flash lorsque `debugTracking` a été activé (`debugTracking` est désactivé dans la configuration par défaut). **Si c’est votre cas, nous vous conseillons vivement de désactiver`debugTracking`immédiatement.** Voici un exemple de code :

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled" behavior 
```

Les versions affectées sont [!DNL AppMeasurement] pour Flash version 4.0 et antérieure sur toutes les plateformes.

> [!NOTE] Pour des raisons de sécurité, nous ne fournissons plus de version AS2 d’[!DNL AppMeasurement] pour Flash. La prise en charge de la collecte de données des projets existants basés sur la version AS2 est maintenue. Nous recommandons cependant fortement aux clients de mettre à niveau leurs mises en œuvre à AS3 et d’incorporer les dernières fonctionnalités de sécurité d’[!DNL AppMeasurement] pour Flash.

[!DNL AppMeasurement] pour les clients Flash affectés par ce problème, vous devez recréer les projets avec la bibliothèque mise à jour disponible au téléchargement depuis la [!DNL Analytics] Console [Plus...](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## 5 novembre 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Version 4.0 - Mise à jour :

* Inclusion de l’API visiteur version 1.5.3.

## jeudi 17 septembre 2015 {#section_319911C0F080452981F8C8BEA2880463}

Version 4.0 - Mise à jour :

* Inclusion de l’API visiteur version 1.5.2.

## jeudi 20 août 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Version 4.0 - Mise à jour :

* Inclusion de l’API visiteur version 1.5.1.

## jeudi 18 juin 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Version 4.0 - Mise à jour

* Inclusion de l’API visiteur version 1.5.
* Utilisez la méthode getCustomerIDs de l’API visiteur 1.5+ pour rassembler les identifiants de client et l’état d’authentification, puis envoyez-les avec les demandes de collecte de données. (AN-102131)

## 21 mai 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Version 3.9.2 - Mise à jour :

* Inclusion de l’API visiteur version 1.4

## jeudi 19 février 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Version 3.9.2:

* Inclusion de l’API visiteur version 1.3.5.
* Changement en « ne pas procéder au suivi automatique des référents » après le premier appel de suivi de sorte que le 2e, 3e, etc. appel de suivi (généralement le suivi des liens) ne comptabilise pas deux fois le référent quand *`s.referrer`* a été manuellement défini avant le premier appel de suivi. (AN-92647)
* Retrait du suivi vidéo [!UICONTROL Pulsation] obsolète incorporé dans le module Média. Le suivi vidéo [!UICONTROL Pulsation] pris en charge a été déplacé dans une bibliothèque vidéo [!DNL Analytics] distincte.

## jeudi 18 septembre 2014 {#section_80939868A2284961BF620851B000294F}

Version 3.9.1:

* Ajout du test de prise en charge des cookies à Flash (k = variable de chaîne de requête O/N) et pf=1 à la chaîne de requête quand le test de prise en charge des cookies est possible (navigateur avec accès [!DNL JavaScript]).
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.2.

## 21 août 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Version 3.9:

* Ajout de variables de latitude et de longitude.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.1.

## Version 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Date de publication : **19 juin 2014**

* Correction de la gestion des indicateurs Terminé et En attente dans les champs d’API de visiteur, par exemple l’identifiant visiteur hérité d’[!DNL Analytics], qui générait des erreurs.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.

## Version 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Date de publication : **17 avril 2014**

* Prise en charge du service [d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.

## Version 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Date de publication : **13 mars 2014**

* Plusieurs correctifs de bogue ont été ajoutés au suivi vidéo [!UICONTROL Pulsation].

## Version 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Date de publication : **6 février 2014**

* Plusieurs correctifs de bogue ont été ajoutés au suivi vidéo [!UICONTROL Pulsation].

## Version 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Date de publication : **14 novembre 2013**

* Plusieurs correctifs de bogue ont été ajoutés au suivi vidéo [!UICONTROL Pulsation].

## Version 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Date de publication : **17 octobre 2013**

* Prise en charge du [suivi vidéo Pulsation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* VisitorAPI.swc a été inclus à la prise en charge du [service d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html).
* Abandon de la prise en charge de Flash Player 9 avec ActionScript 3. Version minimale de Flash Player pour ActionScript 3 : 10.

## Version 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Date de publication : **18 septembre 2013**

* Changements internes pour la prise en charge d’une version bêta à venir.

## Version 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Date de publication : **15 août 2013**

* Désactivation de la remise en file d’attente des demandes en échec quand le suivi hors ligne était désactivé.

## Version 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Date de publication : **21 février 2013**

* Correction d’un problème lié au codage/décodage des URL dans ActionScript 2.

## Version 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Date de publication : **31 janvier 2013**

* Prise en charge de l’envoi d’URL de plus de 255 octets pour gérer l’extension du champ URL de page dans les serveurs de collecte de données Adobe. Les URL de page de plus de 255 octets sont fractionnées, les 255 premiers octets apparaissant dans le paramètre `g=`, les autres apparaissant plus tard dans la chaîne de requête dans le paramètre de `-g=`. Ceci permet d’éviter que les longues URL ne prévalent sur d’autres données en cas de troncation de navigateur, tout en permettant la saisie de longues URL.

* Ajout d’une nouvelle méthode d’identification des visiteurs de secours. Voir [Identification des visiteurs uniques](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Ajout d’un nouvel indicateur `abort` qui peut être défini dans `doPlugins`. Si ce paramètre est défini sur vrai, la bibliothèque [!DNL AppMeasurement] ne poursuit pas cet appel de suivi. L’indicateur abort est réinitialisé à chaque appel de suivi, de sorte que si un appel de suivi consécutif doit également être abandonné, l’indicateur devra être redéfini dans `doPlugins`.

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   Ceci vous permet de centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.

## Version 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Date de publication : **8 novembre 2012**

* Mises à jour internes pour l’intégration d’[!DNL Audience Manager].

## Version 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Date de publication : **22 octobre 2012**

* Modification des compilations ActionScript 3 afin d’ignorer le paramètre de `s.charSet` car UTF-8 est toujours utilisé.

## Version 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Date de publication : **13 septembre 2012**
**Modification importante concernant la liaison de variables** : dans la version 3.5, une option avait été ajoutée pour permettre aux clients de désactiver la liaison de variables afin de pouvoir placer des valeurs de chaînes littérales entre accolades. La liaison de variables à l’aide d’accolades est utilisée principalement lors de la configuration de lecteurs vidéo OSMF à l’aide de balises XML :

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

Un nouvel attribut, appelé `autoBind`, permet de remplacer le comportement par défaut dans les balises XML :

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

Si vous définissez `autoBind` sur la valeur `false`, la valeur est considérée comme une chaîne littérale, et la liaison de variables n’est pas utilisée. Lorsque cet attribut n’est pas défini sur la valeur `false`, le comportement dans les balises XML reste identique.

**Impact sur le code ActionScript**

Bien qu’elle ne soit pas fréquemment utilisée, cette syntaxe est aussi disponible pour lier des variables [!DNL AppMeasurement] dans le code ActionScript. Pour savoir si vous utilisez la liaison de variables, recherchez dans le code des valeurs de variable [!DNL AppMeasurement] entre accolades. Par exemple :

```
s.eVar1 = "{source}";
```

Si vous utilisez la liaison de variables, vous devez modifier ce code afin d’utiliser la nouvelle méthode `bindVariable` :

```
s.bindVariable("eVar1","source");
```

Au lieu de modifier chaque emplacement, vous pouvez éventuellement restaurer le comportement de la version antérieure à 3.5 en définissant `autoBindVariablesByValue` sur la valeur true :

```
s.autoBindVariablesByValue = true;
```

**Corrections supplémentaires :**

* Correction d’un problème en raison duquel l’événement vidéo terminé n’était parfois pas envoyé lors de l’utilisation d’une méthode `media.monitor` personnalisée qui contrôle l’événement de fermeture multimédia :

   ```
   If(media.event=="CLOSE") { 
   … 
   } 
   ```

## Version 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Date de publication : **19 juillet 2012**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Version 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Date de publication : **21 juin 2012**

* Désormais, les versions AS3 utilisent toujours UTF-8. Cela empêche tout problème lié aux chaînes dans des langages multioctets.

## Version 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Date de publication : **26 avril 2012**

Mesure des vidéos : correction d’une incohérence des valeurs de compensation dans le lecteur Brightcove. Désormais, si la compensation est signalée comme nulle, nous utilisons la longueur comme compensation. Ceci corrige les problèmes inhérents à la nouvelle méthode de suivi à l’aide d’une valeur de compensation.

## Version 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Date de publication : **19 janvier 2012**

* Mise à jour du suivi vidéo avec une nouvelle méthode permettant le suivi des affichages complets de vidéos.

## Version 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Date de publication : **8 septembre 2011**

* Les variables prop peuvent désormais contenir une valeur littérale de zéro "0". Auparavant, les valeurs prop avec une valeur littérale de zéro n’étaient pas envoyées.

## Version 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Date de publication : **mai 2011**

* Correction de problèmes dans OSMF liés à l’utilisation de modules externes proxy lors du suivi des lecteurs vidéo OSMF. Cette correction permet à ProxyElements OSMF d’être suivi lorsque l’élément utilisé pour établir des connexions proxy n’est pas suivi.
* Correction d’un problème qui entraînait une erreur lors de la mesure vidéo sur Flash Player 9.0.16.

