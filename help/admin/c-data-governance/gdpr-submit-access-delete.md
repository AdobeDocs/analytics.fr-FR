---
description: valeur nulle
seo-description: valeur nulle
seo-title: Soumettre des demandes d’accès et de suppression
title: Soumettre des demandes d’accès et de suppression
uuid: d006cd5c-e3cd-4385-8683-acaf73cb681b
translation-type: tm+mt
source-git-commit: 2e78524a1ec88ace687ef293332bbee532388c7a

---


# Soumettre des demandes d’accès et de suppression


## Aperçu {#section_BD70882995894C1CA19C205C49FEC23C}

Si vos clients (consommateurs/sujets des données) veulent savoir quelles données vous détenez les concernant ou décident qu’ils veulent être supprimés de vos propriétés Analytics, vous êtes, en tant que contrôleur des données, responsable de la réponse à ces demandes. Le contrôleur des données détermine la manière dont votre organisation va interagir avec les sujets des données (par exemple, par le biais d’un portail utilisateur pour les sujets des données) et gère les interactions avec le sujet des données. Il incombe également au contrôleur de mettre fin à la collaboration avec le sujet des données lorsque la demande est satisfaite. En d’autres termes, Adobe Experience Cloud, en tant qu’entité de traitement des données, n’acceptera pas les demandes directement des sujets des données et ne leur renverra pas directement les données. Par contre, en votre qualité de contrôleur des données, Adobe recevra uniquement des demandes de votre part et ne renverra des données qu’à vous.

Vous pouvez également vous assurer que vos applications mobiles et vos sites web contiendront des messages d’avertissement pertinents et des documents à l’appui sur les droits des sujets des données en ce qui concerne leurs données directement ou indirectement identifiables et les autres données que vous collectez.

## Gérer le consentement des consommateurs {#section_3012015E7E8942519FB9279CF7057EAB}

En tant que contrôleur des données, c’est à vous qu’il revient d’obtenir le consentement explicite de vos sujets de données avant de collecter des données à leur sujet (comprenant éventuellement des données Adobe Analytics) et [d’implémenter un mécanisme d’exclusion](https://marketing.adobe.com/resources/help/en_US/dtm/opt-in.html) sur votre site web. Cela permet à vos sujets des données de ne plus participer à la future collecte de données d’Adobe Experience Cloud.

## Valider les utilisateurs et leurs données {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

En tant que contrôleur des données, vous êtes chargé de vérifier que le sujet des données est bien qui il prétend être et qu’il a le droit d’accéder aux données demandées. En outre, il vous incombe de veiller à ce que les données correctes soient renvoyées au sujet des données et à ce qu’il ne reçoive pas par inadvertance des données concernant d’autres sujets des données.

Cela inclut la révision des données renvoyées par Adobe Analytics dans le cadre d’une demande d’accès à la confidentialité des données avant de les envoyer à l’utilisateur. Une attention particulière doit être accordée si vous utilisez des ID de personne et si vous renvoyez non seulement des données là où cet identifiant est présent, mais également des données pour d’autres accès sur un appareil partagé où cet ID était parfois présent ([Extension d’ID](/help/admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913)).

Chaque fichier combine les données de toutes vos suites de rapports, supprimant automatiquement les copies supplémentaires des accès répliqués. Vous pouvez décider parmi ces fichiers lequel renvoyer au sujet des données. Ou vous pouvez extraire certaines de ces données et les combiner à des données provenant d’autres systèmes avant de les renvoyer au sujet des données.

## Soumettre des demandes {#submit-requests}

Vous pouvez soumettre des demandes d’accès à la confidentialité des données et de suppression de celles-ci par l’intermédiaire de notre portail [de confidentialité des](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) données ou de notre API de confidentialité des [données.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

>[!NOTE]
>
>L’API de confidentialité des données prend en charge les envois par lots pour plusieurs utilisateurs dans une même requête. La limite actuelle est de 1 000 utilisateurs individuels (il peut y avoir plusieurs ID par utilisateur) par fichier de demande JSON.

## Exemple de demande JSON {#section_DB9DE6492FE740918F91D413E7BAB88F}

Voici le fichier JSON qui peut être envoyé par l’intermédiaire de l’interface utilisateur ou de l’API de confidentialité des données, ce qui demande que trois utilisateurs soient traités pour la confidentialité des données.

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
                    "value": "ACME-12345678", 
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com", 
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
* La troisième demande requiert à la fois l’accès et la suppression pour les ID spécifiés. Bien que l’extension d’ID soit spécifiée pour toutes les demandes, elle concerna principalement cette troisième demande, puisque c’est la seule qui utilise des ID non liés à un cookie. En conséquence, cette demande recherchera également les ID de cookies associés à chaque appareil disposant de l’ID de gestion de la relation client spécifié ou de cette adresse électronique, et elle s’étendra afin d’inclure aussi ces ID.

Gardez à l’esprit que :

* La valeur « 5D7236525AA6D9580A495C6C@AdobeOrg » de la section « companyContexts » doit être mise à jour avec la valeur de votre organisation Experience Cloud.
* Les champs « Type » et « Espace de noms » sont décrits plus en détail à la section [Espaces de noms](/help/admin/c-data-governance/gdpr-namespaces.md#concept_26C6392D92194BC1BA3986A144AF285D).
* Les champs « Description » sont ignorés.
* Les champs « Clé » peuvent contenir la valeur de votre choix. Si vous disposez d’un ID interne que vous utilisez pour le suivi des demandes de confidentialité des données, vous pouvez placer cette valeur ici afin de faciliter la correspondance entre les demandes du système Adobe et celles de vos propres systèmes.

## Détails sur la réponse {#section_93F554F65DBB48A18B75EB5784056C96}

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

Aucune donnée n’est renvoyée pour les demandes de suppression : seul un état de l’API de confidentialité des données indiquant que la demande a été effectuée avec succès.

## Test du traitement de la confidentialité des données sur vos données {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Généralement, les clients Analytics configurent des suites de rapports de test pour vérifier ses fonctionnalités avant sa commercialisation. Les sites web ou applications de pré-production enverront des données à ces suites de rapports de test/dev/QA afin d’évaluer la façon dont les choses fonctionnent quand le code est communiqué avant que le trafic réel ne soit envoyé aux suites de rapport de production.

Toutefois, avec une configuration normale, le traitement des demandes en vertu du RGPD ne peut pas être testé sur ces suites de rapports de test avant d’appliquer les demandes aux suites de rapports de production. Cela s’explique par le fait qu’une demande de confidentialité des données est automatiquement appliquée à toutes les suites de rapports de l’organisation Experience Cloud, qui sont souvent toutes des suites de rapports pour votre entreprise.

Vous pouvez toujours tester votre traitement de confidentialité des données de plusieurs manières avant de l’appliquer à toutes vos suites de rapports :

* Vous pouvez par exemple configurer une organisation Experience Cloud séparée contenant uniquement les suites de rapports de test. Utilisez ensuite cette organisation Experience Cloud pour vos tests de confidentialité des données et votre organisation Experience Cloud normale pour le traitement réel de la confidentialité des données.
* Une autre option consiste à attribuer des espaces de noms différents aux ID dans vos suites de rapports de test par rapport à ceux qui figurent dans vos suites de rapports de production.

   Par exemple, vous pouvez ajouter le préfixe « qa- » à chaque espace de noms dans vos suites de rapports de test. Lorsque vous envoyez des requêtes de confidentialité de données avec des espaces de noms uniquement avec le préfixe qa, ces requêtes s’exécuteront uniquement par rapport à vos suites de rapports de test. Ensuite, lorsque vous soumettez vos demandes sans le préfixe qa, elles seront appliquées à vos suites de rapports de production. **C’est l’approche que nous vous recommandons, à moins que vous n’utilisiez les espaces de noms visitorId, AAID, ECID ou customVisitorId, car ils sont codés en dur et vous ne pouvez pas spécifier d’autres noms dans vos suites de rapports de test**.
