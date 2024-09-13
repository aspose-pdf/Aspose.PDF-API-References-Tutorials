---
title: Fenêtre Obtenir le document
linktitle: Fenêtre Obtenir le document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment utiliser la fonctionnalité GetDocumentWindow d'Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.
type: docs
weight: 170
url: /fr/net/programming-with-document/getdocumentwindow/
---
# Introduction

Vous travaillez avec des fichiers PDF et souhaitez mieux contrôler leur apparence lorsqu'ils sont ouverts ? Qu'il s'agisse de masquer la barre de menu ou de redimensionner la fenêtre pour l'adapter à la première page, Aspose.PDF pour .NET vous offre tous les outils dont vous avez besoin pour personnaliser le comportement d'un PDF lorsqu'il est ouvert dans une visionneuse. Dans ce didacticiel, nous allons expliquer comment récupérer et manipuler les paramètres de la fenêtre du document dans Aspose.PDF pour .NET.


# Prérequis

Avant de plonger dans le didacticiel, assurez-vous que vous disposez des prérequis suivants :

- Aspose.PDF pour .NET installé sur votre environnement de développement.
  - [Télécharger Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/)
-  Une licence valide pour Aspose.PDF, ou vous pouvez obtenir une[essai gratuit](https://releases.aspose.com/) ou[permis temporaire](https://purchase.aspose.com/temporary-license/).
- Compréhension de base de .NET et C#.
- Visual Studio ou un autre IDE approprié.

# Paquets d'importation

Avant de commencer à écrire du code, vous devez importer les packages nécessaires. Ouvrez votre projet et, en haut de votre fichier C#, ajoutez l'espace de noms suivant :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Cela vous donnera accès à toutes les classes et méthodes nécessaires à la manipulation de documents PDF à l'aide d'Aspose.PDF pour .NET.

 Décomposons maintenant le processus de récupération des différents paramètres de la fenêtre du document. Pour cet exemple, nous utiliserons un fichier PDF nommé`GetDocumentWindow.pdf`.

## Étape 1 : définir le chemin du répertoire du document

Tout d'abord, nous devons définir le chemin d'accès à notre fichier PDF. Il est essentiel que vous ayez le bon chemin d'accès au fichier pour éviter toute erreur lors de l'exécution.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ici, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF. Il s'agit de votre répertoire de travail à partir duquel vous chargerez le document PDF.

## Étape 2 : Ouvrir le document PDF

Maintenant que le chemin d'accès au fichier est défini, l'étape suivante consiste à ouvrir le document PDF à l'aide d'Aspose.PDF. Cela chargera le document en mémoire, vous permettant de récupérer ses propriétés.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Avec cette simple ligne de code, vous avez réussi à charger votre fichier PDF dans le`pdfDocument` objet, qui vous permettra désormais d'accéder à toutes ses propriétés.

## Étape 3 : Récupérer l'état de centrage de la fenêtre

 Ensuite, vérifions si la fenêtre du document doit être centrée lors de son ouverture. La valeur par défaut est`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Si la sortie est`true`, la fenêtre du document s'ouvre au centre de l'écran. Sinon, elle s'ouvre à sa position par défaut.

## Étape 4 : Vérifiez la direction du texte

Un autre aspect crucial de l'apparence d'un PDF est la direction du texte, qui détermine si le texte est lu de gauche à droite (L2R) ou de droite à gauche (R2L). Vous pouvez récupérer ces informations à l'aide du code suivant :

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 La sortie sera`L2R` pour le texte de gauche à droite et`R2L` pour le texte de droite à gauche. Ce paramètre est particulièrement utile pour les documents dans des langues comme l'arabe ou l'hébreu.

## Étape 5 : Afficher le titre du document dans la fenêtre

La propriété suivante vous permet de contrôler si le titre du document ou le nom du fichier doit être affiché dans la barre de titre de la fenêtre. Par défaut, cette propriété est définie sur`false`, ce qui signifie que le nom du fichier sera affiché.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Si vous souhaitez que le titre du document soit affiché à la place du nom du fichier, ce paramètre doit être activé.

## Étape 6 : redimensionner la fenêtre pour l'adapter à la première page

Parfois, vous souhaiterez peut-être que la fenêtre du document se redimensionne automatiquement pour s'adapter à la première page du PDF lorsqu'elle est ouverte. Voici comment vérifier si cette fonctionnalité est activée :

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Par défaut, ce paramètre est défini sur`false`, ce qui signifie que la taille de la fenêtre restera telle quelle quelle que soit la taille de la première page.

## Étape 7 : masquer la barre de menu

Pour une expérience de lecture plus ciblée, vous pouvez masquer la barre de menu de l'application de visualisation. Vous pouvez récupérer ce paramètre à l'aide de la ligne suivante :

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Cela reviendra`true` si la barre de menu est masquée, et`false` sinon.

## Étape 8 : masquer la barre d’outils

De même, vous pouvez également masquer la barre d'outils dans la visionneuse PDF pour une interface utilisateur plus claire. Ce paramètre peut être récupéré comme suit :

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Si ce paramètre est activé, la barre d’outils sera masquée lors de l’ouverture du PDF.

## Étape 9 : masquer les barres de défilement et les éléments de l'interface utilisateur

Si vous souhaitez afficher uniquement le contenu de la page sans aucun élément d'interface utilisateur supplémentaire tel que des barres de défilement, ce paramètre contrôle ce comportement :

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Lorsqu'il est réglé sur`true`, la visionneuse PDF masquera les barres de défilement et autres éléments de l'interface utilisateur, ne laissant que le contenu du document.

## Étape 10 : Définir le mode de page non plein écran

 Vous pouvez contrôler la façon dont le document apparaît lorsque vous quittez le mode plein écran à l'aide de la`NonFullScreenPageMode` propriété. Ce paramètre est utile pour définir comment l'utilisateur doit interagir avec le document en mode non plein écran.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

La sortie peut être définie sur différents modes tels que des vignettes, des contours ou un panneau de pièces jointes.

## Étape 11 : Définir la mise en page

Ce paramètre vous permet de contrôler la disposition des pages du document. Par exemple, vous pouvez opter pour une vue d'une seule page ou une vue en colonnes continues :

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Cela donne aux utilisateurs une flexibilité dans la façon dont ils lisent ou visualisent le contenu du document.

## Étape 12 : Spécifier le mode de page

 Enfin, le`PageMode` La propriété définit la manière dont le document doit être affiché une fois ouvert. Les options incluent l'affichage des vignettes, le passage en mode plein écran ou l'affichage du panneau des pièces jointes.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

En fonction de vos besoins, vous pouvez définir ce mode sur n'importe quel mode adapté à l'objectif de votre PDF.

## Conclusion

Comme vous pouvez le constater, Aspose.PDF pour .NET fournit des outils complets pour manipuler la façon dont vos documents PDF sont affichés dans différents visualiseurs PDF. Que vous souhaitiez masquer la barre d'outils, centrer la fenêtre ou contrôler la direction du texte, Aspose.PDF offre la flexibilité nécessaire pour améliorer l'expérience de visualisation de l'utilisateur.

# FAQ

### Puis-je personnaliser le niveau de zoom initial du PDF ?
Oui, Aspose.PDF vous permet de définir le niveau de zoom lors de l'ouverture du document.

### Comment puis-je verrouiller la taille de la fenêtre d'un PDF ?
 Vous pouvez définir le`FitWindow` propriété pour empêcher le redimensionnement de la fenêtre.

### Aspose.PDF prend-il en charge différents modes de lecture ?
Oui, il prend en charge différents modes tels que le plein écran, les miniatures et les pièces jointes.

### Est-il possible de masquer les barres de défilement dans la visionneuse PDF ?
 Absolument, vous pouvez masquer les barres de défilement en définissant le`HideWindowUI` propriété à`true`.

### Puis-je centrer la fenêtre du document lorsqu'elle est ouverte ?
 Oui, vous pouvez contrôler cela en définissant le`CenterWindow` propriété.