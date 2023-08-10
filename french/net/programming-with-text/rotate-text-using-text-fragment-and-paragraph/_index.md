---
title: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 400
url: /fr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Créer le document PDF

 Initialiser le`Document` objet pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Ajouter une page

 Obtenir une page particulière du document à l'aide de la`Pages.Add()` méthode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 5 : Créer des fragments de texte

 Créer plusieurs`TextFragment` objets, définissez leur texte et leurs propriétés, et spécifiez l'angle de rotation :

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Ajustez le texte, l'angle de rotation et d'autres propriétés comme vous le souhaitez.

## Étape 6 : Ajoutez des fragments de texte à la page

 Ajoutez les fragments de texte créés à la page en les ajoutant au`Paragraphs` collection:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Étape 7 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide de la`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated3_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe à l'aide d'Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("main text");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment2.TextState.Rotation = 315;
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusion

Toutes nos félicitations! Vous avez appris à faire pivoter du texte à l'aide de fragments de texte et de paragraphes dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la création du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.