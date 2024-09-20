---
title: Rechercher des segments de texte dans une page d'un fichier PDF
linktitle: Rechercher des segments de texte dans une page d'un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher des segments de texte dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET grâce à ce guide détaillé étape par étape. Extrayez du texte, analysez des segments et bien plus encore.
type: docs
weight: 470
url: /fr/net/programming-with-text/search-text-segments-page/
---
## Introduction

Vous êtes-vous déjà demandé comment localiser des segments de texte spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET ? Eh bien, vous avez de la chance ! Dans ce guide, nous allons vous guider tout au long du processus dans un format simple, étape par étape. Que vous essayiez d'extraire des informations, d'analyser du texte ou simplement de naviguer dans les subtilités de la manipulation de PDF, Aspose.PDF pour .NET est là pour vous. Plongeons-nous dans le vif du sujet !

## Prérequis

Avant de commencer, assurons-nous que vous avez tout ce dont vous avez besoin :

-  Aspose.PDF pour .NET : assurez-vous que la bibliothèque est installée. Vous pouvez la récupérer à partir de[ici](https://releases.aspose.com/pdf/net/).
- .NET Framework : assurez-vous que .NET est installé sur votre ordinateur.
- Environnement de développement : Visual Studio ou tout autre IDE pris en charge par .NET est recommandé.
- Document PDF : un fichier PDF dans lequel vous rechercherez des segments de texte.

 Si vous n'avez pas encore Aspose.PDF pour .NET, ne vous inquiétez pas ! Vous pouvez obtenir un essai gratuit à partir de[ici](https://releases.aspose.com/) ou l'acheter[ici](https://purchase.aspose.com/buy).

## Paquets d'importation

Avant de commencer à coder, il est essentiel d'importer les packages nécessaires dans votre projet. Cela permet de garantir que toutes les classes et méthodes requises sont disponibles pour vos tâches de manipulation de PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Maintenant que les éléments essentiels sont en place, passons directement au guide étape par étape.


## Étape 1 : Charger le document PDF

La première étape du processus consiste à charger votre fichier PDF dans le programme. Sans document chargé, il n'y a rien à rechercher, n'est-ce pas ? Voici comment procéder.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` : Cette variable contient le chemin d'accès à votre fichier PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le répertoire réel où votre fichier est stocké.
- `pdfDocument` : En utilisant le`Document` classe, nous chargeons le PDF en mémoire.

## Étape 2 : Configurer la recherche de texte

 Maintenant que votre document est chargé, l'étape suivante consiste à créer un`TextFragmentAbsorber` objet, qui nous permet de rechercher un texte spécifique dans le document.

```csharp
// Créez un objet TextAbsorber pour rechercher toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` : Cet objet est utilisé pour capturer toutes les occurrences du texte que vous recherchez. Remplacer`"text"` avec le texte réel que vous souhaitez rechercher.

## Étape 3 : Accepter l'absorbeur pour des pages spécifiques

Il n'est pas toujours souhaitable de rechercher l'intégralité du document PDF. Dans cet exemple, nous limitons la recherche à une page spécifique.

```csharp
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: Cela indique que nous recherchons uniquement la deuxième page du document. Vous pouvez modifier l'index pour cibler d'autres pages.
- `Accept()` :Cette méthode permet à`TextFragmentAbsorber` pour traiter le texte dans la page spécifiée.

## Étape 4 : Extraire les fragments de texte

Après avoir recherché la page, nous extrayons les fragments de texte trouvés dans une collection.

```csharp
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`:Cette collection contient toutes les instances des fragments de texte trouvés pendant le processus de recherche.

## Étape 5 : Parcourir les fragments de texte et extraire les données

Maintenant, parcourons chaque fragment de texte et extrayons ses détails, tels que la position, la police et la couleur.

```csharp
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` :Nous parcourons chaque`TextFragment` dans la collection.
- `foreach (TextSegment textSegment in textFragment.Segments)`:À l'intérieur de chaque fragment, il y a plusieurs segments. Nous les parcourons pour recueillir toutes les informations pertinentes.
-  Diverses propriétés de`textSegment`:Celles-ci nous donnent des informations détaillées sur le texte, telles que sa position (X et Y), les détails de la police, la taille et la couleur.

## Étape 6 : Afficher les résultats

Enfin, après avoir extrait toutes les informations, les résultats sont imprimés dans la console. Cela vous permet de voir exactement où se trouve le texte et ses détails de formatage.

Voici un exemple de sortie pour plus de clarté :

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- Cette sortie vous donne l'emplacement exact et les informations de formatage du texte « texte » sur la page spécifiée.

## Conclusion

Et voilà ! Vous venez d'apprendre à rechercher des segments de texte spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce processus est très pratique pour traiter des fichiers PDF volumineux, car il vous permet d'identifier et d'extraire efficacement le texte clé. Qu'il s'agisse d'analyser des données, d'extraire des informations ou simplement de parcourir un document, Aspose.PDF vous fournit des outils puissants pour accomplir votre travail.

## FAQ

### Puis-je rechercher plusieurs mots ou expressions ?
 Oui, vous pouvez modifier le`TextFragmentAbsorber`pour rechercher un texte différent en modifiant la chaîne de saisie.

### Est-il possible d’effectuer une recherche sur plusieurs pages ?
 Absolument ! Vous pouvez parcourir toutes les pages du PDF en effectuant une itération sur`pdfDocument.Pages`.

### Comment rechercher du texte insensible à la casse ?
 Vous pouvez utiliser`TextSearchOptions` pour permettre une recherche insensible à la casse.

### Puis-je modifier le texte après l'avoir trouvé ?
 Oui, une fois que vous avez localisé un`TextFragment`, vous pouvez modifier ses propriétés de texte.

### Cette méthode est-elle applicable aux PDF cryptés ?
Oui, à condition de déverrouiller le PDF à l'aide du mot de passe correct.