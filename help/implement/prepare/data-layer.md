---
title: Création d’une couche de données
description: Découvrez quelle couche de données se trouve dans votre mise en œuvre Analytics et comment elle peut être utilisée pour mapper des variables dans Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---

# Création d’une couche de données

Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.

Regardez cette vidéo sur l’utilisation des couches de données :

>[!VIDEO](https://video.tv.adobe.com/v/28775/?quality=12)

## Conditions préalables

[Créer un document de conception de solution :](solution-design.md) il est important que votre entreprise s’aligne sur les exigences de suivi. Assurez-vous d’être préparé et de disposer d’un document de conception de solution avant de contacter les équipes de développement de votre organisation.

## Processus

La mise en œuvre d’Adobe Analytics à l’aide d’une couche de données suit généralement les étapes suivantes :

1. **Collaborez avec votre équipe de développement de site pour mettre en œuvre une couche de données :** votre équipe de développement de site est principalement chargée de s’assurer que l’objet de couche de données est renseigné avec les valeurs correctes. Consultez cette page avec votre équipe de développement de site pour vous assurer que les attentes sont harmonisées entre les équipes.

   >[!NOTE]
   >
   >Le respect des spécifications de couche de données recommandées par Adobe est facultatif. Si vous disposez déjà d’une couche de données ou si vous choisissez de ne pas respecter les spécifications d’Adobe, assurez-vous que votre entreprise s’aligne sur les spécifications à suivre.
1. **Validez la couche de données à l’aide d’une console de navigateur :** une fois une couche de données créée, vous pouvez vérifier qu’elle fonctionne à l’aide de la console de développement de n’importe quel navigateur. Vous pouvez ouvrir la console de développement dans la plupart des navigateurs à l’aide de la clé `F12`. Un exemple de valeur de variable serait `digitalData.page.pageInfo.pageID`.
1. **Utiliser les balises Adobe Experience Platform pour mapper les objets de couche de données aux éléments de données** : créez des éléments de données dans l’interface utilisateur de la collecte de données d’Adobe Experience Platform et mappez-les aux attributs JavaScript décrits dans votre couche de données.
1. **Utiliser l’extension de balises Adobe Analytics pour mapper les éléments de données aux variables Analytics** : en suivant le document de conception de la solution, attribuez chaque élément de données à la variable Analytics appropriée.

## Spécifications

Adobe recommande de suivre la [couche de données numériques de l’expérience client](https://www.w3.org/2013/12/ceddl-201312.pdf) décrite par le [groupe de la communauté de données numériques de l’expérience client](https://www.w3.org/community/custexpdata/). Utilisez les sections suivantes pour comprendre comment les éléments de couche de données interagissent avec Adobe Analytics.

L’objet de couche de données globale recommandé est `digitalData`. L’exemple suivant répertorie un objet JSON de couche de données assez complet avec des exemples de valeurs :

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

Utilisez le rapport [Couche de données numériques de l’expérience client](https://www.w3.org/2013/12/ceddl-201312.pdf) pour plus d’informations sur chaque objet et sous-objet. Tous les sites n’utilisent pas tous les objets. Par exemple, si vous hébergez un site d’actualités, il est peu probable que vous ayez recours au tableau d’objets `digitalData.product`.

Les couches de données sont extensibles ; si vous avez des exigences spécifiques à votre entreprise, vous pouvez inclure des objets dans la couche de données pour répondre à ces besoins.

## Définition des valeurs de couche de données

Les couches de données génèrent généralement des données côté serveur, référençant les mêmes objets que ceux utilisés pour créer le contenu du site. Définissez la couche de données du site en fonction des exigences de suivi définies dans le [document de conception de solution](solution-design.md) de votre entreprise.

## Étapes suivantes

[Mapper des objets de couche de données à des éléments de données](../launch/layer-to-elements.md) : utilisez la couche de données de votre site dans Adobe Experience Platform.
