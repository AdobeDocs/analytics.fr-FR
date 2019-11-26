---
description: Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.
solution: Analytics
title: Gestionnaire de sécurité
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 229ce50a24bd7b86e3859775bb4fbeba1c6a5668

---


# Gestionnaire de sécurité

Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; Paramètres **** de la société &gt; **[!UICONTROL Sécurité]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Requiert des mots de passe difficiles à deviner </span> </td> 
   <td colname="col2">Force l’utilisateur à créer des mots de passe plus sécurisés qui satisfont aux règles suivantes : 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Comporter au moins huit caractères. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Comporter au moins un symbole/caractère numérique entre le premier et le dernier caractères. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Comporter au moins un caractère alphabétique. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">Ne pas figurer dans un dictionnaire ou ne contenir aucun mot du dictionnaire (anglais). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">Ne pas inclure trois (3) caractères consécutifs figurant dans le nom de connexion de l’utilisateur. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Être différent des 10 mots de passe précédents. </li> 
    </ul> <p>Remarque : Cette fonctionnalité est appliquée sur les nouveaux mots de passe. Elle ne vérifie pas les mots de passe existants, ni ne force les utilisateurs à les modifier. C’est pourquoi il est conseillé d’activer l’expiration du mot de passe pour forcer les utilisateurs à modifier leurs mots de passe et à se conformer aux nouvelles règles en matière de mots de passe renforcés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expiration du mot de passe</span> </td> 
   <td colname="col2"> Force les utilisateurs à changer régulièrement le mot de passe de leur compte utilisateur. Vous pouvez indiquer l’intervalle d’expiration des mots de passe et les forcer à expirer immédiatement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Exiger des restrictions d’identification par IP</span> </td> 
   <td colname="col2"> <p>(Cette fonctionnalité ne peut pas être utilisée conjointement avec la connexion à Experience Cloud. Notez que cette fonctionnalité ne sera plus disponible à compter d’octobre 2020.) Limite l’accès aux rapports à des adresse IP ou à des plages d’adresses spécifiques. </p> <p>Vous pouvez ajouter jusqu’à 100 entrées dans la liste Filtre d’adresses IP ; chaque entrée peut être une adresse spécifique ou une plage d’adresses. </p> <p>  L’option <span class="wintitle">Exiger des restrictions d’identification par IP</span> n’est pas appliquée tant que la liste Filtre d’adresses IP ne comporte pas au moins une entrée. </p> <p> <span class="uicontrol"> Adresse</span>IP acceptée : Pour spécifier une plage d’adresses IP, placez-la entre crochets (par exemple, <code>
       192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Les échecs de connexion sont consignés et visibles dans le <a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232">Journal d’utilisation et des accès</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mettre en place les restrictions de domaine de courriel</span> </td> 
   <td colname="col2"> <p>Filtre les adresses et domaines de courriel auxquels Analytics envoie des signets, des rapports téléchargeables et des alertes. </p> <p>La liste Filtre de courriel prend en charge jusqu’à 100 entrées ; chacune d’elles pouvant être une adresse ou un domaine de courriel complet. </p> <p>Si un rapport planifié contient une destination de courriel non approuvée, Analytics envoie une notification par courriel du problème, ainsi qu’un lien pour annuler la planification du rapport. </p> <p>  L’option <span class="wintitle">Mettre en place les restrictions de domaine de courriel</span> n’est pas appliquée tant que la liste <span class="wintitle">Filtre de domaine de courriel accepté</span> ne comporte pas au moins une entrée. </p> <p> <span class="uicontrol"> Adresse électronique et domaines</span>acceptés : Pour spécifier une plage d’adresses IP, placez-la entre crochets (par exemple, <code>
       192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notification de récupération de mot de passe</span> </td> 
   <td colname="col2"> <p>Avertit les administrateurs spécifiés lorsqu’un utilisateur tente de réinitialiser un mot de passe de compte utilisateur. </p> <p> <span class="uicontrol"> Admins disponibles</span> : affiche tous les administrateurs. Vous pouvez utiliser les combinaisons Ctrl + clic et Maj + clic pour sélectionner plusieurs administrateurs. </p> <p> <span class="uicontrol">Membres de la messagerie</span> : affiche le groupe de messagerie défini actuellement. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fin de vie pour l’ [!UICONTROL application des restrictions d’identification par IP]

La fonctionnalité **[!UICONTROL Mettre en place les restrictions]** de connexion par IP est une fonctionnalité d’Analytics qui va bientôt être héritée. Elle vous permet de mettre en liste blanche des adresses IP spécifiques jugées sécurisées, afin de permettre les connexions réussies et l’accès à votre environnement Adobe Analytics. Dans de nombreux cas, cette fonctionnalité est utilisée pour configurer une adresse IP d’entreprise comme la seule adresse IP sécurisée à partir de laquelle les utilisateurs peuvent se connecter. Par conséquent, pour utiliser Adobe Analytics, les utilisateurs doivent se trouver dans un bureau d’entreprise ou se connecter au réseau via VPN.

### Pourquoi envisageons-nous cela pour la fin de vie ?

Cette fonctionnalité est parfois rompue par la migration de connexion à Experience Cloud et/ou la connexion à Experience Cloud. Il est connu pour être coupé pour les clients qui utilisent les attributs **** du client ou la bibliothèque d’ **[!UICONTROL audiences]**.

De plus, si vous possédez plusieurs solutions Experience Cloud, vous pouvez contourner cette exigence en vous connectant à Experience Cloud avec l’une des autres solutions, car cette fonctionnalité n’existe pas ou n’est pas prise en charge en dehors d’Analytics elle-même. Les utilisateurs peuvent également contourner ce problème en usurpant les adresses IP.

Enfin, Adobe propose une solution alternative fonctionnelle et bien plus performante via la connexion unique et les ID fédérés. Cette fonctionnalité vous permet de mieux contrôler et de mieux sécuriser l’expérience de connexion de vos utilisateurs.

### En quoi la suppression de cette fonction vous affecte-t-elle ?

Pour tous les clients qui ont configuré des restrictions **[!UICONTROL de connexion]** d’IP, cette fonctionnalité sera supprimée en octobre 2020. A ce moment-là, les restrictions d’identification par IP toujours en vigueur ne seront plus appliquées. Si vous devez encore limiter la connexion par adresse IP, vous devez examiner et mettre en oeuvre la solution recommandée pour les identifiants de connexion unique et fédérés (plus d’informations et de ressources ci-dessous).

De plus, le gestionnaire des restrictions **[!UICONTROL de connexion]** Imposer les adresses IP sera supprimé de **[!UICONTROLAdmin &gt; Paramètres de la société &gt; Gestionnaire]** de sécurité dans l’interface utilisateur d’Analytics (comme illustré ci-dessous).

![](assets/sec-manager2.png)

### Quelles sont tes autres options ?

Comme indiqué ci-dessus, cette fonction Analytics sera en fin de vie. Afin de vous donner le temps de mettre en oeuvre l’authentification unique et les Federated ID, nous avons reporté la date de fin de vie à octobre 2020.

Les SSO et les Federated ID sont des solutions supérieures à la fonctionnalité de restriction d'identification par IP que nous avons en place aujourd'hui et vous apporteront plus de contrôle, de sécurité et de fonctionnalités.

Pour plus d’informations sur la configuration des identifiants fédérés/SSO, vous trouverez la documentation d’aide suivante. Nous vous recommandons de les lire attentivement et de collaborer avec votre service informatique pour les mettre en oeuvre :

* [Connexion unique et Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Console d’administration - Documentation de configuration des identités](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Console d’administration - Didacticiel sur la configuration des identités (vidéo)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Didacticiel de configuration des ID fédérés (vidéo)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Connexion unique - Questions fréquentes](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Types d’identité pris en charge par Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Si vous souhaitez continuer à exprimer votre soutien aux restrictions d’identification par IP et demander qu’elles soient fournies par Experience Cloud, vous pouvez voter pour cette fonctionnalité sur notre page [](https://forums.adobe.com/ideas/11648)Forum. Pour toute question ou information supplémentaire sur les SSO/Federated ID et l'EXC, veuillez contacter Ryan Monger (monger@adobe.com).
