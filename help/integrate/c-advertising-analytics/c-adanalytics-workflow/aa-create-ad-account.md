---
seo-title: Configuration d’un compte Advertising
title: Configuration d’un compte Advertising
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Configuration d’un compte Advertising

Les administrateurs Adobe Analytics peuvent créer des comptes publicitaires et mapper plusieurs suites de rapports (1:1, 1:plusieurs, plusieurs:plusieurs).

Les administrateurs peuvent également [accorder l’accès à des non-administrateurs](../../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) pour configurer des comptes publicitaires.

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. Acceptez les conditions du contrat de licence de l’utilisateur final (uniquement lors de la première utilisation).
1. Cliquez sur **[!UICONTROL + Ajouter]**.
1. La boîte de dialogue [!UICONTROL Nouveau compte de moteur de recherche] s’affiche :

   ![](assets/aa_new_se_account.png)

1. Définissez les **[!UICONTROL Paramètres du moteur de recherche]en procédant comme suit :**

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
      <td colname="col2"> <p>Vous disposez de 2 options : Google AdWords et les publicités Microsoft Bing. </p> <p>Remarque : Yahoo Gemini a été absorbé par Microsoft Bing le 31 mars 2019. Par conséquent, l’option de compte publicitaire Yahoo Gemini n’est plus disponible.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nom du compte </p> </td> 
      <td colname="col2"> <p>Vous pouvez définir le nom que vous souhaitez donner à ce compte. C’est le nom convivial du compte qui apparaîtra dans l’interface utilisateur. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Jeton OAuth </p> </td> 
      <td colname="col2"> <p>Remarque : OAuth est un protocole libre de délégation d’accès, utilisé généralement afin d’autoriser des sites web ou des applications à accéder à leurs informations à partir d’autres sites web sans leur donner les mots de passe. </p> <p>Remarque : Vous serez redirigé vers une URL tierce (efrontier.com). Adobe utilise efrontier pour faire fonctionner le processus d’authentification OAuth pour les trois moteurs de recherche. </p> <p>Remarque : Si vous utilisez Internet Explorer 11 (ou une version antérieure), vous ne parviendrez pas à récupérer le jeton OAuth pour aucun des trois moteurs de recherche. Utilisez d’autres navigateurs web en remplacement. </p> <p>Un clic sur <span class="uicontrol">Récupérer le jeton</span> lancera le processus d’authentification OAuth2. Cela signifie que vous devrez vous connecter à votre compte de recherche Google/Bing en utilisant vos identifiants. Selon le moteur de recherche utilisé, le processus sera légèrement différent : </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google AdWords : utilisez vos ID de compte Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing : utilisez vos ID de compte Bing et vos ID de client Bing. </li> 
        </ul> <p>Reportez-vous à la section <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md#concept_F7F67448F3B44342967E0419E96F384D" format="dita" scope="local"> Trouver les ID de votre compte</a> pour obtenir des informations sur ces ID. </p> <p>Une fois la connexion établie, le champ Jeton OAuth s’affiche. 
        <systemoutput>
          Récupéré
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Dans la section **[!UICONTROL Suivi], vous fournissez des informations sur la façon dont les données du moteur de recherche sont suivies par votre implémentation Adobe Analytics.** Cette étape est requise pour ajouter correctement les données du moteur de recherche aux données d’Adobe Analytics.
Définissez les **[!UICONTROL Paramètres du suivi]en procédant comme suit :**

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Type </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Auto</span>: Permet au moteur Advertising Cloud de décider comment les paramètres de suivi sont ajoutés aux modèles de suivi/URL de destination du moteur de recherche. Il s’agit de l’approche la plus simple, même si elle ne produit pas toujours le meilleur jeu de données intégré. <p>Important : Afin de configurer un compte de moteur de recherche en "Mode Auto", vous devez effectuer les actions suivantes : 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">Le paramètre et la valeur « s_kwcid » seront ajoutés aux modèles de suivi de comptes ou aux URL de pages d’entrée dans le compte ajouté. Ils seront alors insérés à la fin de l’URL. Par conséquent, vous devrez peut-être prendre une mesure supplémentaire si votre serveur web requiert une certaine paire clé=valeur à la fin de l’URL OU une mise à jour pour prendre en charge n’importe quelle nouvelle paire clé=valeur dans l’URL. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">De plus, les mots-clés peuvent être insérés dans l’URL d’entrée avec la valeur « s_kwcid », donc s’ils contiennent des caractères spéciaux ou des symboles, veuillez vérifier que votre serveur web prend en charge ces caractères (par exemple, le « + » est un caractère spécial courant utilisé dans les mots-clés en « requête large modifiée »). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manuel</span>: Permet de gérer la manière dont les paramètres de suivi sont ajoutés aux modèles de suivi/URL de destination du moteur de recherche. <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33" format="dita" scope="local"> Consultez ces exemples de suivi manuel pour chaque moteur de recherche</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Dans la section **[!UICONTROL Mappage], vous sélectionnerez les suites de rapport à lier à ce compte de moteur de recherche.** Vous devez fournir au moins une suite de rapports pour pouvoir enregistrer votre compte Advertising. Vous pouvez mapper plusieurs comptes à plusieurs suites de rapports (1:1, 1:plusieurs, plusieurs:plusieurs). Remarque : Les données qu’AMO extrait du moteur de recherche sont simplement copiées dans toutes les suites de rapports mappées, il n’y a donc aucun partage de données.

   >[!IMPORTANT]
   >
   >Only report suites that have been [mapped to an Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) will be available for selection. If you do not see your report suite listed, refer to [Troubleshoot Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Définissez les **[!UICONTROL Paramètres du mappage]en procédant comme suit :**

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Mappage de suites de rapports </p> </td> 
      <td colname="col2"> <p>Le mappage de suites de rapports détermine la suite de rapports qui sera liée à ce compte de moteur de recherche. Autrement dit, il détermine dans quelles suites de rapports seront envoyées les données du moteur de recherche. </p> <p>Si la suite de rapports ne figure pas dans la liste, vous pouvez <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html" format="html" scope="external">mapper votre suite de rapports à une organisation Experience Cloud</a> en utilisant cet outil. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Après l’enregistrement, une clause de non-responsabilité affiche une liste d’avertissements. Vous devez confirmer que vous avez lu et compris cet accord. Cochez la case, puis cliquez sur **[!UICONTROL OK]**.

   Vous êtes maintenant dirigé vers l’[interface utilisateur de gestion](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md#concept_531B99165A4E47B4B8849376B532AFDB) des comptes Advertising, où le nouveau compte doit apparaître.

> [!NOTE] Vous devez attendre au moins 24 heures avant que les données du moteur de recherche ne commencent à renseigner vos rapports Analytics.

