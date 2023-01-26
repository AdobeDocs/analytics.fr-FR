---
description: Comment envoyer des demandes d’accès et de suppression des données dans Adobe Analytics.
title: Soumettre des demandes d’accès et de suppression
feature: Data Governance
exl-id: bb94cedf-ac9b-4d38-9136-bd3da2acf018
source-git-commit: aa794220b464b7665e89345a116a263189dcc3fa
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 100%

---

# Soumettre des demandes d’accès et de suppression

Si vos clients (consommateurs/sujets des données) veulent savoir quelles données vous détenez les concernant ou décident qu’ils veulent être supprimés de vos propriétés Analytics, vous êtes, en tant que contrôleur des données, responsable de la réponse à ces demandes. Le contrôleur des données détermine la manière dont votre organisation va interagir avec les sujets des données (par exemple, par le biais d’un portail utilisateur pour les sujets des données) et gère les interactions avec le sujet des données. Il incombe également au contrôleur de mettre fin à la collaboration avec le sujet des données lorsque la demande est satisfaite. En d’autres termes, Adobe Experience Cloud, en tant qu’entité de traitement des données, n’acceptera pas les demandes directement des sujets des données et ne leur renverra pas directement les données. Par contre, en votre qualité de contrôleur des données, Adobe recevra uniquement des demandes de votre part et ne renverra des données qu’à vous.

Vous pouvez également vous assurer que vos applications mobiles et vos sites web contiendront des messages d’avertissement pertinents et des documents à l’appui sur les droits des sujets des données en ce qui concerne leurs données directement ou indirectement identifiables et les autres données que vous collectez.

## Gérer le consentement des consommateurs  {#section_3012015E7E8942519FB9279CF7057EAB}

En tant que contrôleur des données, c’est à vous qu’il revient d’obtenir le consentement explicite de vos sujets de données avant de collecter des données à leur sujet (comprenant éventuellement des données Adobe Analytics) et d’implémenter un [mécanisme de désinscription](https://www.adobe.com/fr/privacy/opt-out.html#customeruse) sur votre site Web. Cela permet à vos sujets des données de ne plus participer à la future collecte de données d’Adobe Experience Cloud.

## Valider les utilisateurs et leurs données  {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

En tant que contrôleur des données, vous êtes chargé de vérifier que le sujet des données est bien qui il prétend être et qu’il a le droit d’accéder aux données demandées. En outre, il vous incombe de veiller à ce que les données correctes soient renvoyées au sujet des données et à ce qu’il ne reçoive pas par inadvertance des données concernant d’autres sujets des données.

Cela inclut la vérification des données renvoyées par Adobe Analytics dans le cadre d’une demande d’accès relative à la Confidentialité des données avant de les envoyer au sujet des données. Une attention particulière doit être accordée si vous utilisez des ID de personne et si vous renvoyez non seulement des données là où cet identifiant est présent, mais également des données pour d’autres accès sur un appareil partagé où cet ID était parfois présent. Voir [Extension d’ID.](/help/admin/c-data-governance/gdpr-id-expansion.md)

Chaque fichier combine les données de toutes vos suites de rapports, supprimant automatiquement les copies supplémentaires des accès répliqués. Vous pouvez décider parmi ces fichiers lequel renvoyer au sujet des données. Ou vous pouvez extraire certaines de ces données et les combiner à des données provenant d’autres systèmes avant de les renvoyer au sujet des données.

## Soumettre des demandes   {#submit-requests}

Vous pouvez soumettre des demandes d’accès et de suppression relatives à la confidentialité des données par l’intermédiaire de notre [interface utilisateur de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html?lang=fr) ou de notre [API Privacy Service.](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr)

>[!NOTE]
>
>L’API relative à la Confidentialité des données prend en charge les soumissions par lots pour plusieurs utilisateurs dans une seule demande. La limite actuelle est de 1 000 utilisateurs individuels (il peut y avoir plusieurs ID par utilisateur) par fichier de demande JSON.

## Exemple de demande JSON   {#sample-json-request}

Voici une configuration JSON qui pourrait être soumise via l’interface utilisateur ou l’API relative à la Confidentialité des données, demandant le traitement en vertu de la Confidentialité des données pour trois utilisateurs.

```
{ 
    "companyContexts": [ 
        { 
            "namespace": "imsOrgID", 
            "value": "5D7236525AA6D9580A495C6C@AdobeOrg" 
        } 
    ], 
    "users": [ 
        { 
            "key": "Data Privacy-1234", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "AAID", 
                    "namespaceId", 10, 
                    "type": "standard", 
                    "description": "Legacy Visitor ID", 
                    "value": "2D783E5885312539-4000010360000181", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1235", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "ECID", 
                    "namespaceId": 4, 
                    "type": "standard", 
                    "description": "This is the ID generated by the Adobe ID service.", 
                    "value": "22470866493385587460528148368265592748", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678"
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com" 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Remarquez que la section relative à l’utilisateur comporte trois blocs, représentant trois demandes distinctes, probablement pour trois sujets de données différents.

* La première demande est une demande d’accès qui utilise un ID de cookie Adobe Analytics classique (AAID).
* La deuxième demande est également une demande d’accès, mais qui utilise un cookie MCID/ECID.
* La troisième demande requiert à la fois l’accès et la suppression pour les ID spécifiés. Bien que l’extension d’ID soit spécifiée pour toutes les demandes, elle concerna principalement cette troisième demande, puisque c’est la seule qui utilise des ID non liés à un cookie. En conséquence, cette demande recherchera également les ID de cookies associés à chaque appareil disposant de l’ID de gestion de la relation client spécifié ou de cette adresse e-mail, et elle s’étendra afin d’inclure aussi ces ID.

Gardez à l’esprit que :

* La valeur « 5D7236525AA6D9580A495C6C@AdobeOrg » de la section « companyContexts » doit être mise à jour avec la valeur de votre organisation Experience Cloud.
* Les champs « Type » et « Espace de noms » sont décrits plus en détail à la section [Espaces de noms](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
* Les champs « Description » sont ignorés.
* Les champs « Clé » peuvent contenir la valeur de votre choix. Si vous utilisez un ID interne pour suivre les demandes relatives à la Confidentialité des données, vous pouvez saisir cette valeur ici pour faciliter la mise en correspondance des demandes du système Adobe et celles de vos propres systèmes.

## Détails sur la réponse  {#section_93F554F65DBB48A18B75EB5784056C96}

Cette section contient des détails relatifs aux réponses d’accès et de suppression.

**Détails sur la réponse d’accès**

En tant que contrôleur des données, les données renvoyées pour une demande d’accès vous fournissent une URL que vous pouvez utiliser pour télécharger un fichier ZIP contenant un répertoire pour chaque produit Adobe que vous possédez. Dans le dossier Analytics, il peut y avoir :

* Fichiers de personne : dérivés des accès contenant une étiquette ID-PERSON correspondante

   * Un fichier CSV avec une ligne pour chaque accès correspondant et une colonne pour chaque champ avec une étiquette ACC-ALL ou ACC-PERSON, triées par horodatage.
   * Un fichier récapitulatif en HTML avec une entrée pour chaque étiquette ACC-ALL ou ACC-PERSON. Chaque entrée énumère toutes les valeurs uniques pour ce champ et le nombre de fois où chacune d’entre elles est apparue. Les champs contenant des horodatages sont arrondis afin de spécifier uniquement des jours uniques.

* Fichiers d’appareil : dérivés des accès où l’un des champs correspondait à un ID-DEVICE spécifié, mais pas à un ID-PERSON spécifié

   * Un fichier CSV avec une ligne pour chaque accès correspondant et une colonne pour chaque champ avec une étiquette ACC-ALL, triées par horodatage.
   * Fichier récapitulatif en HTML avec une entrée pour chaque étiquette ACC-ALL. Chaque entrée va énumérer toutes les valeurs uniques pour ce champ et le nombre de fois où chacune d’entre elles est apparue. Les champs contenant des horodatages sont arrondis afin de spécifier uniquement des jours uniques.

Chaque fichier combine les données de toutes vos suites de rapports, supprimant automatiquement les copies supplémentaires des accès répliqués.

Vous pouvez décider parmi celles-ci laquelle renvoyer au sujet des données. Ou vous pouvez extraire certaines de ces données et les combiner à des données provenant d’autres systèmes avant de les renvoyer au sujet des données.

**Détails sur la réponse de suppression**

Aucune donnée n’est renvoyée pour les demandes de suppression. Seul l’état de l’API relative à la Confidentialité des données indique que la demande a été satisfaite.

## Test sur vos données du traitement en vertu de la confidentialité des données {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Généralement, les clients Analytics configurent des suites de rapports de test pour vérifier ses fonctionnalités avant sa commercialisation. Les sites web ou applications de pré-production enverront des données à ces suites de rapports de test/dev/QA afin d’évaluer la façon dont les choses fonctionnent quand le code est communiqué avant que le trafic réel ne soit envoyé aux suites de rapport de production.

Toutefois, avec une configuration normale, le traitement des demandes en vertu du RGPD ne peut pas être testé sur ces suites de rapports de test avant d’appliquer les demandes aux suites de rapports de production. Cela s’explique par le fait qu’une demande relative à la Confidentialité des données est automatiquement appliquée à toutes les suites de rapports dans l’organisation Experience Cloud, qui correspond souvent à toutes les suites de rapports pour votre entreprise.

Il existe certaines façons de tester quand même votre traitement en vertu de la Confidentialité avant de l’appliquer à toutes vos suites de rapports.

* Vous pouvez par exemple configurer une organisation Experience Cloud séparée contenant uniquement les suites de rapports de test. Ensuite, utilisez cette organisation Experience Cloud pour votre test relatif à la Confidentialité des données et votre organisation Experience Cloud classique pour effectuer le véritable traitement.
* Une autre option consiste à attribuer des espaces de noms différents aux ID dans vos suites de rapports de test par rapport à ceux qui figurent dans vos suites de rapports de production.

   Par exemple, vous pouvez ajouter le préfixe « qa- » à chaque espace de noms dans vos suites de rapports de test. Lorsque vous soumettez vos demandes relatives à la Confidentialité des données avec uniquement des espaces de noms comportant le préfixe qa, ces demandes ne sont exécutées que par rapport à vos suites de rapports de test. Ensuite, lorsque vous soumettez vos demandes sans le préfixe qa, elles seront appliquées à vos suites de rapports de production. **C’est l’approche que nous vous recommandons, à moins que vous n’utilisiez les espaces de noms visitorId, AAID, ECID ou customVisitorId, car ils sont codés en dur et vous ne pouvez pas spécifier d’autres noms dans vos suites de rapports de test**.
