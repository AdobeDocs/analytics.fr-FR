---
description: Cette section contient des instructions relatives au test des règles de traitement, ainsi qu’une liste des erreurs courantes à éviter.
subtopic: Processing rules
title: Astuces et conseils concernant les règles de traitement
feature: Processing Rules
role: Admin
exl-id: e663d98b-dcfd-4420-84ac-07ddfe55a3f2
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---

# Astuces et conseils concernant les règles de traitement

Cette section contient des instructions relatives au test des règles de traitement, ainsi qu’une liste des erreurs courantes à éviter.

## Tester les règles de traitement {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Cette section contient des instructions relatives au test des règles de traitement avant leur déploiement en production.

**Test des règles qui lisent des termes de recherche**

Pour tout critère axé sur une recherche comme, par exemple, si prop1 contient« news », accédez au rapport prop 1, recherchez « news » et voyez s’il existe d’éventuelles correspondances imprévues.

**Test des règles qui lisent des variables**

Créez une page HTML vierge sur votre bureau, insérez le s_code provenant de votre site, puis définissez la variable `s.account` sur une suite de rapports de développement. Si vos règles sont basées sur un référent, un domaine de référence ou un autre élément, utilisez des exemples d’URL issus du rapport Référents actif, définissez la variable `s.referrer` avec l’une de ces valeurs et chargez la page. De même, si la règle est basée sur la valeur URL de page, vous pouvez définir `s.pageURL`. Cette même procédure peut être utilisée pour toute variable.

**Utilisation d’une suite de rapports de développement**

Il est conseillé de configurer les règles de traitement sur une suite de rapports de développement afin de vous assurer de leur bon fonctionnement. Si possible, tâchez de copier les règles dans une petite suite de rapports de production avant un déploiement plus vaste.

## Rechercher des valeurs vides {#section_EE84A5525E26415787930723B0CAAE0F}

Lors de la création d’une règle, veuillez tenir compte d’une éventuelle valeur vide. Si vous n’ajoutez pas de condition qui recherche une valeur vide, vous risquez d’écraser, par mégarde, des variables par des valeurs vides.

![](assets/tips-set-value-acquisition-code.png)

Il importe également de tenir compte de l’ordre de traitement. Dans l’exemple suivant, il s’avère que l’eVar personnalisée Nom de page précédent va être définie sur l’URL si Nom de page n’est pas présent. Cependant, l’URL est placée dans le nom de la page après l’application de règles de traitement. Dans ce cas, le nom de page est donc vide s’il n’est pas défini sur la page.

![](assets/tips-copy-page-name-to-evar.png)

## Éviter l’écrasement des valeurs {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

Dans l’exemple ci-dessous, deux variables de données contextuelles sont utilisées sur le site pour capturer des termes de recherche : search_keyword et search_term. Cependant, sur base de la configuration, la valeur search_keyword est toujours écrasée, même si search_term est vide.

Cette règle doit être reconfigurée afin de tester chaque variable de données contextuelles pour une valeur avant de renseigner le terme de recherche interne et, éventuellement, de concaténer les deux valeurs si un cas d’utilisation est prévu pour les conserver.

![](assets/tips-search-keyword.png)

## Encoder des termes de recherche au format UTF-8 ou Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

Les termes de recherche extraits d’une chaîne de requête doivent être codés correctement, sans quoi la correspondance ne sera pas établie avec les règles de traitement.

![](assets/tips-multibyte.png)

## Commence par, Contient et Se termine par {#section_80CE853244FC435B844A09EA51868D8D}

Sélectionnez la condition de correspondance correcte afin de trouver la condition la plus restrictive. Vous pouvez rechercher des valeurs dans un rapport avant de créer une règle afin de vous assurer qu’il n’existe aucune correspondance indésirable. Vous devez, par exemple, effectuer une recherche dans le rapport Prop2 afin trouver tous les emplacements applicables avant d’activer cette règle.

![](assets/tips-startswith.png)

## Méthode d’application des règles de traitement lors de la copie d’accès à l’aide de VISTA

Si une règle VISTA est configurée pour copier des accès vers une autre suite de rapports, les accès sont envoyés via toute règle de traitement définie sur l’autre suite de rapports.

Si des règles de traitement sont définies sur la suite de rapports d’origine, leur application dépend de la manière dont la règle VISTA a été configurée par les services d’ingénierie. Pour le savoir, vous pouvez demander à votre spécialiste de la mise en œuvre si la règle VISTA copie les valeurs « pré » ou « post » dans la suite de rapports supplémentaire. Si la valeur « pré » est copiée, les règles de traitement définies sur la suite de rapport d’origine ne sont pas appliquées. Si la valeur « post » est copiée, les règles de traitement sont appliquées avant la copie de l’accès.
