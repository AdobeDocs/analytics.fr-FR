---
description: En suivant et en enregistrant les sites de référence des visiteurs pour chaque visite, vous pouvez déterminer de quelle façon les visiteurs sont parvenus sur votre site pour chaque visite.
title: Type de référent
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Type de référent

En suivant et en enregistrant les sites de référence des visiteurs pour chaque visite, vous pouvez déterminer de quelle façon les visiteurs sont parvenus sur votre site pour chaque visite.

La liste ci-dessous définit les divers types de référents :

**Autres sites web :** d’autres référents sont enregistrés lorsque les visiteurs cliquent sur un lien figurant sur la page d’un autre site (non défini comme faisant partie de votre site) et arrivent sur votre site.

**Moteurs de recherche** : les référents de moteur de recherche sont enregistrés lorsque les visiteurs utilisent un moteur de recherche pour accéder à votre site. La valeur de référence doit être considérée comme un moteur de recherche par Adobe et ne peut pas être un sous-domaine qui n’est pas considéré comme un moteur de recherche ([!DNL mail.yahoo.com], par exemple, n’est pas un moteur de recherche, car il s’agit du domaine utilisé pour le courrier électronique).

**[!UICONTROL Réseaux sociaux]** : la valeur de référence doit être considérée comme un réseau social par Adobe. Voir [Liste des réseaux sociaux](https://helpx.adobe.com/analytics/kb/list-social-networks.html).

**Courrier électronique** : un domaine référent est considéré comme un domaine référent de courrier électronique lorsque les visiteurs cliquent sur un lien dans un courrier électronique contenant le protocole [!DNL imap://] ou [!DNL mail://] et arrivent sur votre site. Par exemple, les messages provenant de [!DNL https://mail.yahoo.com] ne sont pas considérés comme des référents « courriel », car le protocole est [!DNL https://]. Les courriels d’Outlook sont signalés dans la ligne Tapé/Marqué, alors que les référents avec un protocole HTTP où le domaine est un moteur de recherche connu sont signalés dans la ligne Moteur de recherche.

**Tapé/marqué** : les référents sont comptabilisés quand un visiteur tape directement l’URL de votre site dans son navigateur ou qu’il y accède au moyen de ses signets. Les périphériques mobiles signalent désormais un type de référent *`typed/bookmarked`* s’il n’y a pas de référent pour le premier accès de la visite.

**[!UICONTROL Dans votre site]** : ces éléments sont des URL balisées par les filtres URL internes. Ces éléments ne sont pas comptabilisés comme *`referrer instances`*, mais ils sont visibles lors de la génération de rapports sur d’autres mesures.

## Types de référents par interface {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Analyses ad hoc </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Types de référents reportés </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Autres sites web </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Moteurs de recherche </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Tapé/Marqué </li> 
    </ul> <p> Ce rapport présente uniquement deux mesures prédéfinies : Instances et Visiteurs uniques. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Autres sites web </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Moteurs de recherche </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Tapé/Marqué </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Autres sites web </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Moteurs de recherche </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Tapé/Marqué </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> Dans votre site </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Remarques {#section_B83A3571D64E4E7792712FAF740D7955}

* Le référent, le type de référent et le domaine de référent sont définis au premier accès de la visite ou durant une visite lorsque le référent est externe (par exemple, si un visiteur quitte votre site, utilise un moteur de recherche, puis revient sur votre site avant l’expiration de la première visite). Ces valeurs sont définies en même temps et persistent pendant toute la visite.
* Tous les types de référents ne sont pas répertoriés dans ce rapport. En d’autres termes, les visites à l’échelle du site ne correspondent pas aux visites sur ce rapport.

## Historique des rapports {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Date | Changement |
|---|---|
| 16/1/2014 | Data Warehouse a été mis à jour pour correspondre à la logique utilisée par les Reports &amp; Analytics marketing. Auparavant, le type de référent ne persistait pas pendant la visite. |

