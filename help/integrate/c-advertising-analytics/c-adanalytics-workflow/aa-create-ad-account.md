---
title: Configuration d’un compte Advertising
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: 0345a71bd2dd99410658cc858fe05ee2751d0013
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 81%

---


# Configuration d’un compte Advertising

Les administrateurs Adobe Analytics peuvent créer des comptes publicitaires et mapper plusieurs suites de rapports (1:1, 1:plusieurs, plusieurs:plusieurs).

Les administrateurs peuvent également [accorder l’accès à des non-administrateurs](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) pour configurer des comptes publicitaires.

![](assets/aa_accounts.png)

1. Dans Adobe Analytics, accédez à **[!UICONTROL Admin]** > **[!UICONTROL Comptes Advertising]**.
1. Acceptez les conditions du contrat de licence de l’utilisateur final (uniquement lors de la première utilisation).
1. Cliquez sur **[!UICONTROL + Ajouter]**.
1. La boîte de dialogue [!UICONTROL Nouveau compte de moteur de recherche] s’affiche :

   ![](assets/aa_new_se_account.png)

1. Définissez les **[!UICONTROL Paramètres du moteur de recherche]** en procédant comme suit :

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Type </p> </td> 
      <td colname="col2"> <p>Vous disposez de deux options : Google AdWords et Microsoft Bing Ads. </p> <p>Remarque : Yahoo Gemini a été absorbé par Microsoft Bing le 31 mars 2019. Par conséquent, l’option de compte publicitaire Yahoo Gemini n’est plus disponible.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nom du compte </p> </td> 
      <td colname="col2"> <p>Vous pouvez définir le nom que vous souhaitez donner à ce compte. C’est le nom convivial du compte qui apparaîtra dans l’interface utilisateur. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Jeton OAuth </p> </td> 
      <td colname="col2"> <p>Remarque : OAuth est un protocole libre de délégation d’accès, utilisé généralement afin d’autoriser des sites web ou des applications à accéder à leurs informations à partir d’autres sites web sans leur donner les mots de passe. </p> <p>Remarque : vous serez redirigé vers une URL tierce (efrontier.com). Adobe utilise efrontier pour faire fonctionner le processus d’authentification OAuth pour les trois moteurs de recherche. </p> <p>Remarque : si vous utilisez Internet Explorer 11 (ou une version antérieure), vous ne parviendrez pas à récupérer le jeton OAuth pour aucun des trois moteurs de recherche. Utilisez d’autres navigateurs web en remplacement. </p> <p>Un clic sur <span class="uicontrol">Récupérer le jeton</span> lancera le processus d’authentification OAuth2. Cela signifie que vous devrez vous connecter à votre compte de recherche Google/Bing en utilisant vos identifiants. Selon le moteur de recherche utilisé, le processus sera légèrement différent : </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google AdWords : utilisez vos ID de compte Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing : utilisez vos ID de compte Bing et vos ID de client Bing. </li> 
        </ul> <p>Reportez-vous à la section <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Trouver les ID de votre compte</a> pour obtenir des informations sur ces ID. </p> <p>Une fois connecté, le champ du jeton OAuth affichera 
        <systemoutput>
          Récupéré
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Dans la section **[!UICONTROL Suivi]**, vous fournissez des informations sur la façon dont les données du moteur de recherche sont suivies par votre implémentation Adobe Analytics. Cette étape est requise pour ajouter correctement les données du moteur de recherche aux données d’Adobe Analytics.
Définissez les **[!UICONTROL Paramètres du suivi]** en procédant comme suit :

   | Paramètre | Description |
   |--- |--- |
   | Type | <ul><li>**Auto :** Permet au moteur Advertising Cloud de décider comment les paramètres de suivi sont ajoutés aux modèles de suivi/URL de destination du moteur de recherche. Il s’agit de l’approche la plus simple, même si elle ne produit pas toujours le meilleur jeu de données intégré.<br>**Important :**Pour configurer un compte de moteur de recherche en mode automatique, vous devez effectuer les actions suivantes :<br>- Le paramètre et la valeur &quot;s_kwcid&quot; seront ajoutés aux modèles de suivi de compte ou aux URL de landing page du compte ajouté. Ils seront alors insérés à la fin de l’URL. Par conséquent, vous devrez peut-être prendre une mesure supplémentaire si votre serveur web requiert une certaine paire clé=valeur à la fin de l’URL OU une mise à jour pour prendre en charge n’importe quelle nouvelle paire clé=valeur dans l’URL.** Remarque :**En savoir plus sur l’ajout de ce paramètre à votre stratégie[de sécurité du](https://docs.adobe.com/content/help/en/id-service/using/reference/csp.html)contenu.<br>- En outre, les mots-clés peuvent être insérés dans l&#39;URL de destination dans le cadre de la valeur &quot;s_kwcid&quot;. Par conséquent, s&#39;ils contiennent des caractères ou des symboles spéciaux, veuillez confirmer que votre serveur Web peut les prendre en charge (un exemple de caractères spéciaux courants est &quot;+&quot;, qui est utilisé dans les mots-clés &quot;Correspondance large modifiée&quot;).</li><li>**Manuel :** Permet de gérer la manière dont les paramètres de suivi sont ajoutés aux modèles de suivi/URL de destination du moteur de recherche. [Consultez ces exemples de suivi manuel pour chaque moteur de recherche](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Dans la section **[!UICONTROL Mappage]**, vous sélectionnerez les suites de rapport à lier à ce compte de moteur de recherche. Vous devez fournir au moins une suite de rapports pour pouvoir enregistrer votre compte Advertising. Vous pouvez mapper plusieurs comptes à plusieurs suites de rapports (1:1, 1:plusieurs, plusieurs:plusieurs). Remarque : Les données qu’AMO extrait du moteur de recherche sont simplement copiées dans toutes les suites de rapports mappées, il n’y a donc aucun partage de données.

   >[!IMPORTANT]
   >
   >Seules les suites de rapports qui ont été [mappées à une organisation Experience Cloud](https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html) pourront être sélectionnées. Si la suite de rapports ne figure pas dans la liste, consultez la [résolution des problèmes d’Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Définissez les **[!UICONTROL Paramètres du mappage]** en procédant comme suit :

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Suite de rapports Mappage </p> </td> 
      <td colname="col2"> <p>Le mappage de suites de rapports détermine la suite de rapports qui sera liée à ce compte de moteur de recherche. Autrement dit, il détermine dans quelles suites de rapports seront envoyées les données du moteur de recherche. </p> <p>Si la suite de rapports ne figure pas dans la liste, vous pouvez <a href="https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html"  >mapper votre suite de rapports à une organisation Experience Cloud</a> en utilisant cet outil. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Après l’enregistrement, une clause de non-responsabilité affiche une liste d’avertissements. Vous devez confirmer que vous avez lu et compris cet accord. Cochez la case, puis cliquez sur **[!UICONTROL OK]**.

   Vous êtes maintenant dirigé vers l’[interface utilisateur de gestion](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) des comptes Advertising, où le nouveau compte doit apparaître.

>[!NOTE] Patientez 24 heures au moins avant que les données du moteur de recherche ne commencent à apparaître dans vos rapports Analytics.

