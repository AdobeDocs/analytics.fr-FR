---
description: Questions fréquentes sur le suivi des liens dans Activity Map.
title: Questions fréquentes sur le suivi des liens
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
translation-type: tm+mt
source-git-commit: 7ba73d75dde80571125c83efb3265441b8d3278a
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 44%

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

## Quand le suivi des liens a-t-il lieu ?

L’identification des liens et des régions du Activity Map se produit lorsque les utilisateurs cliquent sur une page.

## Qu’est-ce qui est suivi par défaut ?

Si un événement de clics survient sur un élément, l’élément doit passer certaines vérifications pour déterminer si AppMeasurement le traitera comme un lien. Ces vérifications sont les suivantes :

* S’agit-il d’une balise `A` ou `AREA` avec une propriété `href` ?
* Existe-t-il un attribut `onclick` qui définit une variable `s_objectID` ?
* S’agit-il d’une balise `INPUT` ou d’un bouton `SUBMIT` avec une valeur ou un texte enfant ?
* S’agit-il d’une balise `INPUT` de type `IMAGE` et d’une propriété `src` ?
* Est-ce un `BUTTON` ?

Si la réponse à l’une des questions ci-dessus est Oui, l’élément est considéré comme un lien et sera suivi.

>[!IMPORTANT]
>
>Les balises de bouton avec l’attribut type=&quot;button&quot; ne sont pas considérées comme des liens par AppMeasurement. Envisagez de supprimer type=&quot;button&quot; sur les balises de bouton et d’ajouter role=&quot;button&quot; ou submit=&quot;button&quot; à la place.

>[!IMPORTANT]
>
>Une balise d&#39;ancrage avec un &quot;href&quot; qui début avec &quot;#&quot; est considérée comme un emplacement de cible interne par AppMeasurement, et non comme un lien (puisque vous ne quittez pas la page). Par défaut, Activity Map ne suit pas ces emplacements cibles internes. Il effectue uniquement le suivi des liens qui permettent à l’utilisateur d’accéder à une nouvelle page.

## Comment le Activity Map suit-il les autres éléments HTML visuels ?

a. Par le biais de la fonction `s.tl()`.

Si le clic s&#39;est produit via un appel `s.tl()`, le Activity Map recevra également ce événement de clic et déterminera si une variable de chaîne `linkName` a été trouvée. Au cours de l&#39;exécution de `s.tl()`, linkName sera défini en tant qu&#39;ID de lien du Activity Map. L&#39;élément sur lequel l&#39;utilisateur a cliqué à l&#39;origine de l&#39;appel `s.tl()` sera utilisé pour déterminer la région. Exemple :

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Par le biais de la variable `s_objectID`. Exemple :

    &quot;
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>Lier le texte ici&lt;/a>
    
    
    &quot;

>[!IMPORTANT]
>
>Un point-virgule de fin (;) est requis lors de l’utilisation de `s_objectID` en Activity Map.

## Pouvez-vous me donner quelques exemples de liens qui seront suivis ?

### Exemple 1

```
  <a hef="/home?lang=en>Home</a>
```

### Exemple 2

```
 <input type="submit" value="Submit"/>
```

### Exemple 3

```
  <input type="image" src="submit-button.png"/>
```

### Exemple 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Exemple 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Pouvez-vous me donner quelques exemples de liens qui ne seront PAS suivis ?

1. Raison : la balise d’ancrage ne possède pas de valide `href`:
   `<a name="innerAnchor">Section header</a>`

1. Raison : Ni `s_ObjectID` ni `s.tl()` présent :

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Raison : Ni `s_ObjectID` ni `s.tl()` présent :

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Raison : Il manque un élément d’entrée de formulaire à la propriété &quot;src&quot; :

   `<input type="image"/>`
