---
title: Faire pivoter le texte à l'aide du paragraphe de texte et du générateur
linktitle: Faire pivoter le texte à l'aide du paragraphe de texte et du générateur
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à faire pivoter du texte à l'aide d'un paragraphe de texte et d'un générateur dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 410
url: /fr/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes de texte et de générateurs. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Text.TextBuilder;
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

## Étape 5 : créer et faire pivoter des paragraphes de texte

 Créer un`for` boucle pour générer plusieurs paragraphes de texte avec différentes rotations :

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Ajustez les valeurs de position et de rotation selon vos besoins.

## Étape 6 : Créer et configurer des fragments de texte

 Créer plusieurs`TextFragment`objets, définissez leur texte et leurs propriétés :

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

Ajustez le texte et les autres propriétés comme vous le souhaitez.

## Étape 7 : Ajouter des fragments de texte au paragraphe

 Ajoutez les fragments de texte créés au paragraphe à l'aide de la`AppendLine` méthode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Étape 8 : Créer un TextBuilder et ajouter le paragraphe

 Créer un`TextBuilder` objet à l'aide de`pdfPage` et ajoutez le paragraphe de texte à la page PDF :

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Étape 9 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide de la`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated4_out.pdf"` avec le nom de fichier de sortie souhaité.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès à faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la création du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### Exemple de code source pour faire pivoter le texte à l'aide d'un paragraphe de texte et d'un générateur à l'aide d'Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Spécifier la rotation
	paragraph.Rotation = i * 90 + 45;
	// Créer un fragment de texte
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Créer un fragment de texte
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Créer un fragment de texte
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Définir les propriétés du texte
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Créer un fragment de texte
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Définir les propriétés du texte
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Créer un objet TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Ajouter le fragment de texte à la page PDF
	textBuilder.AppendParagraph(paragraph);
}
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```