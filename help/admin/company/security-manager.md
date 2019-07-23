---
description: Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.
seo-description: Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.
seo-title: Gestionnaire de sécurité
solution: Analytics
title: Gestionnaire de sécurité
topic: Outils d’administration
uuid: b 3 fbdba 0-e 2 bf -4 d 67-92 e 3-ef 05711141 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gestionnaire de sécurité

Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Paramètres de la société]** &gt; **[!UICONTROL Sécurité]**

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
   <td colname="col2"> <p>Limite l’accès aux rapports à des adresse IP ou à des plages d’adresses spécifiques. </p> <p>Vous pouvez ajouter jusqu’à 100 entrées dans la liste Filtre d’adresses IP ; chaque entrée peut être une adresse spécifique ou une plage d’adresses. </p> <p>  L’option <span class="wintitle">Exiger des restrictions d’identification par IP</span> n’est pas appliquée tant que la liste Filtre d’adresses IP ne comporte pas au moins une entrée. </p> <p> <span class="uicontrol"> Adresse IP acceptée</span>: Pour spécifier une plage d'adresses IP, placez la plage entre crochets (par exemple, 
     <code>
       192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Les échecs de connexion sont consignés et visibles dans le <a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local">Journal d’utilisation et des accès</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mettre en place les restrictions de domaine de courriel</span> </td> 
   <td colname="col2"> <p>Filtre les adresses et domaines de courriel auxquels Analytics envoie des signets, des rapports téléchargeables et des alertes. </p> <p>La liste Filtre de courriel prend en charge jusqu’à 100 entrées ; chacune d’elles pouvant être une adresse ou un domaine de courriel complet. </p> <p>Si un rapport planifié contient une destination de courriel non approuvée, Analytics envoie une notification par courriel du problème, ainsi qu’un lien pour annuler la planification du rapport. </p> <p>  L’option <span class="wintitle">Mettre en place les restrictions de domaine de courriel</span> n’est pas appliquée tant que la liste <span class="wintitle">Filtre de domaine de courriel accepté</span> ne comporte pas au moins une entrée. </p> <p> <span class="uicontrol"> Adresses et domaines de courriel acceptés</span>: Pour spécifier une plage d'adresses IP, placez la plage entre crochets (par exemple, 
     <code>
       192.168.1 0.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notification de récupération de mot de passe</span> </td> 
   <td colname="col2"> <p>Avertit les administrateurs spécifiés lorsqu’un utilisateur tente de réinitialiser un mot de passe de compte utilisateur. </p> <p> <span class="uicontrol"> Admins disponibles</span> : affiche tous les administrateurs. Vous pouvez utiliser les combinaisons Ctrl + clic et Maj + clic pour sélectionner plusieurs administrateurs. </p> <p> <span class="uicontrol">Membres de la messagerie</span> : affiche le groupe de messagerie défini actuellement.  </p> </td> 
  </tr> 
 </tbody> 
</table>

