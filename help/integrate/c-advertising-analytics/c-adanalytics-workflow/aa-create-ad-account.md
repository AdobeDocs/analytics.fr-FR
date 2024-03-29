---
title: Configuration d’un compte publicitaire dans Advertising Analytics
description: Vous permet de créer des comptes publicitaires et de mapper plusieurs comptes à plusieurs suites de rapports.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 100%

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

   | Paramètre | Description |
   | --- | --- |
   | Type | Vous disposez de deux options : Google AdWords et Microsoft Bing Ads.  Remarque : Yahoo Gemini a été absorbé par Microsoft Bing le 31 mars 2019. Par conséquent, l’option de compte publicitaire Yahoo Gemini n’est plus disponible. |
   | Nom du compte | Vous pouvez définir le nom que vous souhaitez donner à ce compte. C’est le nom convivial du compte qui apparaîtra dans l’interface utilisateur. |
   | Jeton OAuth | **Remarque :** OAuth est un protocole libre de délégation d’accès, utilisé généralement afin d’autoriser des sites web ou des applications à accéder à leurs informations à partir d’autres sites web sans leur donner les mots de passe. Remarque : vous serez redirigé vers une URL tierce (efrontier.com). Adobe utilise efrontier pour faire fonctionner le processus d’authentification OAuth pour les trois moteurs de recherche. Remarque : si vous utilisez Internet Explorer 11 (ou une version antérieure), vous ne parviendrez pas à récupérer le jeton OAuth pour aucun des trois moteurs de recherche. Utilisez d’autres navigateurs web en remplacement.<p>Un clic sur **[!UICONTROL Récupérer le jeton]** lancera le processus d’authentification OAuth2. Vous serez invité à vous connecter à votre compte de recherche Google/Bing en utilisant vos identifiants. Selon le moteur de recherche utilisé, le processus sera légèrement différent : <ul><li>Google AdWords : utilisez votre numéro de compte Google</li><li>Microsoft Bing : utilisez vos ID de compte Bing et vos ID de client Bing.</li></ul>Voir [Trouvez votre numéro de compte](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) pour obtenir des informations sur ces numéros. Une fois votre connexion effectuée, le champ du **[!UICONTROL jeton OAuth]** affichera **[!UICONTROL Récupéré]**. |

1. Dans la section **[!UICONTROL Suivi]**, vous fournissez des informations sur la façon dont les données du moteur de recherche sont suivies par votre implémentation Adobe Analytics. Cette étape est requise pour ajouter correctement les données du moteur de recherche aux données d’Adobe Analytics.
Définissez les **[!UICONTROL Paramètres du suivi]** en procédant comme suit :

   | Paramètre | Description |
   | --- | --- |
   | Type | <ul><li>**Automatique :** laisse le moteur Advertising Cloud décider comment les paramètres de suivi sont ajoutés aux modèles de suivi/adresses URL de destination du moteur de recherche. Il s’agit de l’approche la plus simple, même si elle ne produit pas toujours le meilleur jeu de données intégré.<br>**Important :** pour configurer un compte de moteur de recherche en mode automatique, vous devez effectuer les actions suivantes :<br>- Le paramètre et la valeur « s_kwcid » seront ajoutés aux modèles de suivi de compte ou aux adresses URL de page de destination du compte ajouté. Ils seront alors insérés à la fin de l’URL. Par conséquent, vous devrez peut-être prendre une mesure supplémentaire si votre serveur web requiert une certaine paire clé=valeur à la fin de l’URL OU une mise à jour pour prendre en charge n’importe quelle nouvelle paire clé=valeur dans l’URL. **Note :** découvrez si vous devez ajouter ou non ce paramètre à votre [politique de sécurité du contenu](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=fr).<br>- De plus, les mots-clés peuvent être insérés dans l’URL de destination avec la valeur « s_kwcid », donc s’ils contiennent des caractères spéciaux ou des symboles, veuillez vérifier que votre serveur web prend en charge ces caractères (par exemple, le « + » est un caractère spécial courant utilisé dans les mots-clés en « requête large modifiée »).</li><li>**Manuel :** permet de gérer la façon dont les paramètres de suivi sont ajoutés aux modèles de suivi/adresses URL de destination du moteur de recherche. [Consultez ces exemples de suivi manuel pour chaque moteur de recherche](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Dans la section **[!UICONTROL Mappage]**, vous sélectionnerez les suites de rapport à lier à ce compte de moteur de recherche. Vous devez fournir au moins une suite de rapports pour pouvoir enregistrer votre compte Advertising. Vous pouvez mapper plusieurs comptes à plusieurs suites de rapports (1:1, 1:plusieurs, plusieurs:plusieurs). Remarque : Les données qu’AMO extrait du moteur de recherche sont simplement copiées dans toutes les suites de rapports mappées, il n’y a donc aucun partage de données.

   >[!IMPORTANT]
   >
   >Seules les suites de rapports qui sont mappées à une organisation Experience Cloud peuvent être sélectionnées. Si la suite de rapports ne figure pas dans la liste, consultez la [résolution des problèmes d’Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Définissez les **[!UICONTROL Paramètres du mappage]** en procédant comme suit :

   | Paramètre | Description |
   | --- | --- |
   | Mappage de suites de rapports | Le mappage de suites de rapports détermine la suite de rapports qui sera liée à ce compte de moteur de recherche. Autrement dit, il détermine dans quelles suites de rapports seront envoyées les données du moteur de recherche. |


1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Après l’enregistrement, une clause de non-responsabilité affiche une liste d’avertissements. Vous devez confirmer que vous avez lu et compris cet accord. Cochez la case, puis cliquez sur **[!UICONTROL OK]**.

   Vous êtes maintenant dirigé vers l’[interface utilisateur de gestion](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) des comptes Advertising, où le nouveau compte doit apparaître.

>[!NOTE]
>
>Patientez 24 heures au moins avant que les données du moteur de recherche ne commencent à apparaître dans vos rapports Analytics.
