---
title: Faire pivoter le texte à l'aide d'un fragment de texte dans un fichier PDF
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment faire pivoter du texte à l'aide de fragments de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 390
url: /fr/net/programming-with-text/rotate-text-using-text-fragment/
---
Ce tutoriel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de fragments de texte dans un fichier PDF. Le code source C# fourni illustre le processus étape par étape.

## Prérequis

Avant de poursuivre le didacticiel, assurez-vous de disposer des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Étape 3 : Créer le document PDF

 Initialiser le`Document` objet pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Ajouter une page

 Obtenir une page particulière du document à l'aide de la`Pages.Add()` méthode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 5 : Créer des fragments de texte

 Créer plusieurs`TextFragment` objets, définissez leur texte et leurs propriétés et spécifiez leurs positions sur la page :

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Ajustez le texte, les positions et les autres propriétés comme vous le souhaitez.

## Étape 6 : créer un TextBuilder et ajouter des fragments de texte

 Créer un`TextBuilder` objet utilisant le`pdfPage` et ajoutez les fragments de texte à la page PDF :

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Étape 7 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide de la commande`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated1_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour faire pivoter le texte à l'aide d'un fragment de texte avec Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte pivoté
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Créer un fragment de texte pivoté
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Ajouter le fragment de texte à la page PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusion

Félicitations ! Vous avez appris avec succès à faire pivoter du texte à l'aide de fragments de texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la création du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Faire pivoter le texte à l’aide d’un fragment de texte » ?

R : Le didacticiel « Faire pivoter du texte à l'aide d'un fragment de texte » vise à vous guider dans le processus d'utilisation de la bibliothèque Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de fragments de texte dans un document PDF. Le didacticiel fournit des instructions étape par étape et un exemple de code pour réaliser cette fonctionnalité.

#### Q : Que signifie « faire pivoter du texte à l’aide de fragments de texte » ?

R : La rotation de texte à l'aide de fragments de texte fait référence à la possibilité d'appliquer une rotation à des fragments de texte individuels dans un document PDF à l'aide de la bibliothèque Aspose.PDF. Cette technique vous permet de contrôler l'orientation du texte à différents angles ou positions dans le contenu PDF.

#### Q : Pourquoi voudrais-je faire pivoter des fragments de texte dans un document PDF ?

R : La rotation de fragments de texte dans un document PDF peut être utile à diverses fins, telles que mettre en valeur un contenu spécifique, créer des conceptions artistiques ou améliorer la mise en page et la lisibilité.

#### Q : Comment configurer le projet pour le tutoriel ?

A : Pour configurer le projet :

1. Créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.
3. Ajoutez les directives d’utilisation nécessaires à votre fichier C#.

#### Q : Comment puis-je créer un nouveau document PDF ?

 A : Pour créer un nouveau document PDF, initialisez un`Document`objet de la bibliothèque Aspose.PDF. Vous pouvez utiliser cet objet pour ajouter des pages et du contenu au PDF.

#### Q : Comment faire pivoter des fragments de texte à l’aide de fragments de texte ?

A : Pour faire pivoter des fragments de texte à l’aide de fragments de texte :

1.  Créer`TextFragment` objets.
2. Définissez le texte et les propriétés des fragments de texte.
3. Spécifiez les positions des fragments de texte sur la page.
4.  Réglez l'angle de rotation à l'aide de la`TextState.Rotation` propriété des fragments de texte.
5.  Créer un`TextBuilder`objet et ajouter les fragments de texte à la page PDF.

#### Q : Puis-je appliquer différents angles de rotation à différents fragments de texte ?

 R : Oui, vous pouvez appliquer différents angles de rotation à différents`TextFragment` objets. Chaque fragment de texte peut avoir son propre angle de rotation spécifié à l'aide de la`TextState.Rotation` propriété.

#### Q : Comment enregistrer le document PDF avec des fragments de texte pivotés ?

 A : Pour enregistrer le document PDF avec des fragments de texte pivotés, utilisez le`Save` méthode de la`Document` objet et fournissez le chemin et le nom du fichier de sortie souhaité.