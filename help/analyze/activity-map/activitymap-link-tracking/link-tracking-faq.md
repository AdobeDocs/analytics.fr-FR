---
description: Questions fréquentes sur le suivi des liens dans Activity Map.
title: Questions fréquentes sur le suivi des liens
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: a0b8f61c3728c5867640ce20768614c8d79ca657
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 100%

---

# Questions fréquentes sur le suivi des liens

Questions fréquentes sur le suivi des liens dans Activity Map.

>[!CAUTION]
>
>En activant le suivi Activity Map, **vous pouvez collecter des données d’informations d’identification personnelle (PII).** Ces données peuvent être utilisées seules ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier une personne dans son contexte.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* Liens `Mailto`. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* Liens `User ID` qui peuvent s’afficher dans l’en-tête ou le pied de page d’un site web une fois l’utilisateur connecté.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.

## Quand le suivi des liens se produit-il ?

L’identification des liens et des régions dʼActivity Map se produit lorsque les utilisateurs cliquent sur une page.

## Quels éléments sont suivis par défaut ?

Si un événement de clic se produit sur un élément, certaines vérifications doivent être effectuées afin de déterminer si AppMeasurement le considérera comme un lien. Ces vérifications sont les suivantes :

* S’agit-il d’une balise `A` ou `AREA` avec une propriété `href` ?
* Un attribut `onclick` définit-il une variable `s_objectID` ?
* S’agit-il d’une balise `INPUT` ou d’un bouton `SUBMIT` avec une valeur ou du texte enfant ?
* S’agit-il d’une balise `INPUT` de type `IMAGE` avec une propriété `src` ?
* Sʼagit-il dʼun `BUTTON` ?

Si la réponse à l’une des questions ci-dessus est Oui, l’élément est considéré comme un lien et sera suivi.

>[!IMPORTANT]
>
>Les balises de bouton avec l’attribut type=&quot;button&quot; ne sont pas considérées comme des liens par AppMeasurement. Envisagez de supprimer type=&quot;button&quot; sur les balises de bouton et d’ajouter à la place role=&quot;button&quot; ou submit=&quot;button&quot;.

>[!IMPORTANT]
>
>Une balise d’ancrage avec une balise « href » commençant par « # » est considérée comme un emplacement cible interne par AppMeasurement, et non comme un lien (puisque vous ne quittez pas la page). Par défaut, Activity Map ne suit pas ces emplacements cibles internes. Il effectue uniquement le suivi des liens qui permettent à l’utilisateur d’accéder à une nouvelle page.

## Comment Activity Map suit-il d’autres éléments HTML visuels ?

a. Par le biais de la fonction `s.tl()`.

Si le clic s’est produit par le biais d’un appel `s.tl()`, Activity Map recevra également cet événement de clic et déterminera si une variable de chaîne `linkName` a été trouvée. Lors de l’exécution de `s.tl()`, ce linkName sera défini comme l’ID de lien dʼActivity Map. L’élément sur lequel l’utilisateur a cliqué et qui est à l’origine de l’appel `s.tl()` sera utilisé pour déterminer la région. Exemple :

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Par le biais de la variable `s_objectID`. Exemple :

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    Texte du lien ici
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>Un point-virgule (;) de fin est requis lorsque la variable `s_objectID` est utilisée dans Activity Map.

## Pouvez-vous me donner des exemples de liens qui seront suivis ?

### Exemple 1

```
  <a href="/home>Home</a>
```

### Exemple 2

```
 <input type="submit" value="Submit"/>
```

### Exemple 3

```
  <input type="image" src="submit-button.png"/>
```

### Exemple 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Exemple 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Pouvez-vous me donner des exemples de liens qui ne seront PAS suivis ?

1. Raison : la balise d’ancrage ne possède pas de `href` valide :
   `<a name="innerAnchor">Section header</a>`

1. Raison : absence de `s_ObjectID` et `s.tl()` :

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Raison : absence de `s_ObjectID` et `s.tl()` :

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Raison : la propriété « src » présente un élément d’entrée de formulaire manquant :

   `<input type="image"/>`

