---
description: 'Les ID que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au sujet des données. Analytics peut créer un ensemble étendu d’ID pour inclure ces données associées aux demandes relatives à la Confidentialité des données. Vous pouvez utiliser cette option avec un paramètre facultatif pour chaque demande que vous soumettez en vertu de la Confidentialité des données, ajoutée à la demande JSON. '
title: Extension d’ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Extension d’ID

Les ID que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au sujet des données. Analytics peut créer un ensemble étendu d’ID pour inclure ces données associées aux demandes relatives à la Confidentialité des données. Vous pouvez utiliser cette option avec un paramètre facultatif pour chaque demande que vous soumettez en vertu de la Confidentialité des données, ajoutée à la demande JSON :

```
"expandIds": true
```

Voir [Exemple de demande JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request) pour savoir comment inclure cette option à la demande. Pour plus de détails, consultez la [documentation de l’API relative aux Services de confidentialité](https://www.adobe.io/apis/experienceplatform/gdpr.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Considérations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Extension de l’ID de cookie </p> </td> 
   <td colname="col2"> <p>De nombreux clients Analytics utilisaient auparavant le <a href="https://marketing.adobe.com/resources/help/fr_FR/whitepapers/cookies/cookies_analytics.html">cookie Analytics</a> hérité, mais utilisent désormais le <a href="https://marketing.adobe.com/resources/help/fr_FR/mcvid/">service Identity (ECID)</a>, précédemment connu sous le nom de service Marketing Cloud ID (MCID). Pour les visiteurs qui ont consulté leur site web pour la première fois après la transition, seul l’ECID existe. Cependant, pour ceux qui ont consulté le site pour la première fois alors que seul le cookie hérité était disponible, mais qui l’ont reconsulté depuis : certaines de leurs données contiennent les deux cookies, bien que les anciennes ne disposent que du cookie Analytics et que, dans de rares cas, les données récentes ne peuvent avoir qu’un ECID. </p> <p>Vous souhaitez vous assurer de trouver toutes les données pour un visiteur identifié via un cookie ou un ECID Analytics (ID visiteur). Par conséquent, si vous utilisez l’ECID et avez utilisé le cookie Analytics par le passé, vous devez inclure les deux ID dans chaque requête que vous soumettez à l’aide de l’un des deux ID, ou spécifier les options expandIDs. Lorsque vous spécifiez expandIDs, Adobe vérifie les autres cookies ECID ou Analytics correspondant à l’un des ID de cookies que vous fournissez. La demande est automatiquement étendue pour inclure ces ID de cookies nouvellement identifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID personnalisé pour l’extension de l’ID de cookie </p> </td> 
   <td colname="col2"> <p>Sur les sites web d’e-commerce, il n’est pas rare qu’un visiteur navigue, ajoute des articles à son panier, puis commence le processus de paiement avant de se connecter au site. Si l’ID utilisé pour identifier les utilisateurs dans le cas d’une demande relative à la Confidentialité des données est stocké dans une variable personnalisée uniquement lorsque l’utilisateur se connecte, cette activité de pré-connexion ne sera pas associée à l’ID. Avec l’ID de cookie Analytics, les clients peuvent choisir d’associer leur consultation du site avant la connexion à l’achat effectué après la connexion, puisque l’ID de cookie est conservé lors de la connexion. </p> <p>Supposons que votre implémentation stocke un ID de connexion (ID CRM, nom d’utilisateur, numéro de fidélité, adresse électronique, etc., ou un hachage de l’une de ces valeurs) dans une variable personnalisée (prop ou eVar) ou un identifiant visiteur personnalisé, puis utilise cet ID dans le cas d’une demande d’accès relative à la Confidentialité des données. Le sujet des données pourrait s’étonner que les informations relatives à sa navigation ne soient pas renvoyées dans le cadre d’une demande d’accès, surtout si vous lui avez présenté des articles consultés, mais pas encore achetés. </p> <p>Le traitement en vertu de la Confidentialité des données d’Analytics prend donc en charge l’extension d’ID, où Analytics trouve tous les ID de cookie qui apparaissent dans le même accès que tout ID personnalisé, puis étend la demande de manière à inclure également ces ID. </p> <p>Lorsque la valeur expandIDs est spécifiée avec un espace de noms autre qu’un espace de noms de cookie, la demande est étendue pour inclure tout ID de cookie (cookie ECID ou Analytics) trouvé dans les accès contenant l’un des ID spécifiés. L’extension d’ID de cookie, comme indiqué ci-dessus, est ensuite effectuée sur tout nouvel ID de cookie trouvé. </p> <p>Quand l’option expandIDs est utilisée pour une demande d’accès et que l’ID spécifié comporte une étiquette ID-PERSON, deux ensembles de fichiers seront alors renvoyés. Le premier ensemble (l’ensemble « person ») ne contient que des données provenant des accès dans lesquels l’ID spécifié a été trouvé. Le second ensemble (l’ensemble « device ») ne contient que des données provenant des accès des ID étendus, dans lesquels l’ID spécifié était absent. </p> </td> 
  </tr> 
 </tbody> 
</table>

Au cours des premiers mois qui suivent l’entrée en vigueur de la Confidentialité des données, la grande majorité des demandes d’Analytics relatives à la Confidentialité des données ne demandaient pas d’extension d’ID, mais il vous appartient de déterminer la valeur appropriée pour votre organisation. Consultez votre équipe juridique pour savoir si l’extension d’ID est requise pour vos données avec les ID que vous utilisez et les données que vous collectez dans Adobe Analytics. Vous devez principalement prendre en compte le fait que sur un appareil partagé, depuis lequel plusieurs utilisateurs ont consulté votre site, l’utilisation d’extension d’ID inclura des données provenant d’autres utilisateurs de l’appareil dans les données renvoyées par les demandes d’accès (dans le fichier de l’appareil). Même si vous avez suivi les bonnes pratiques en matière d’étiquetage en excluant les données personnelles du fichier de l’appareil, telles que les pages visitées, ce dernier contiendra le nombre de pages visitées et l’heure liée à chacune de ces visites. Est-ce acceptable de partager ces informations avec une personne qui n’est peut-être pas votre visiteur ?

Pour une demande de suppression dans laquelle l’extension d’ID n’est pas utilisée, si vous utilisez un ID non lié à un cookie (n’importe quel ID autre que celui lié à l’ECID ou Analytics) pour identifier les accès à supprimer, et que cet ID possède une étiquette ID-DEVICE, alors les chiffres du visiteur unique seront modifiés, car seules certaines instances des ID de cookie seront anonymisées. Les autres ne seront pas modifiées. Si vous ne spécifiez aucune extension d’ID, il est recommandé d’utiliser soit un ID de cookie pour les requêtes, soit des ID possédant une étiquette ID-PERSON.

Lorsqu’Adobe effectue une extension d’ID, celle-ci peut nécessiter une nouvelle analyse complète des données, ce qui augmente la durée requise par Adobe pour terminer la requête, souvent de l’ordre d’une semaine.

## Autres indicateurs de demandes relatives à la confidentialité des données

En plus de l’indicateur « expandIDs », Analytics prend en charge deux autres indicateurs qui peuvent être transmis dans le cadre d’une demande relative à la Confidentialité des données. Ces indicateurs avec leurs valeurs par défaut sont :

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

À l’avenir, la « analyticsDeleteMethod » pourra prendre en charge une valeur « purge » en plus de la valeur par défaut « anonymize ». Lorsqu’elle est prise en charge, elle entraîne la suppression de l’accès complet plutôt que la simple mise à jour des valeurs des champs d’accès qui ont des étiquettes DEL.

En plus de sa valeur par défaut, le champ Priorité prend également en charge une valeur « low ». Vous devez spécifier cette valeur pour les demandes qui ne font pas suite à une demande du sujet des données et qui ne sont donc pas soumises à une obligation légale de traitement dans les 30 jours. Notez qu’Adobe déconseille l’utilisation de l’API relative aux Services de confidentialité pour des raisons autres que les demandes initiées par le sujet des données. L’API relative aux Services de confidentialité n’est pas un outil approprié pour le nettoyage ou la réparation des données et aura des conséquences imprévues.

> [!NOTE] L’[API relative aux Services de confidentialité](https://www.adobe.io/apis/experienceplatform/gdpr.html) a été fournie pour vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des demandes relatives à la Confidentialité des données pour d’autres clients Adobe. Nous vous demandons de ne pas utiliser l’API aux Services de confidentialité à d’autres fins, par exemple pour effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs.

Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Cet inconvénient n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API relative aux Services de confidentialité ne convient pas à cet usage.

Veuillez contacter votre gestionnaire de compte (CSM) afin qu’il vous mette en relation avec notre équipe de conseillers en architecture et ingénierie de données dans le but d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour pallier tout problème de PII ou de données.

