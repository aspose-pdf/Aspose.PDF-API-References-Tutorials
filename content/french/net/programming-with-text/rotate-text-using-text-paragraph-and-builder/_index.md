---
title: Faire pivoter le texte à l'aide du paragraphe de texte et du générateur dans un fichier PDF
linktitle: Faire pivoter le texte à l'aide du paragraphe de texte et du générateur dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment faire pivoter du texte à l'aide d'un paragraphe de texte et d'un générateur dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 410
url: /fr/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
Ce tutoriel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un fichier PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 5 : Créer et faire pivoter des paragraphes de texte

 Créer un`for` boucle pour générer plusieurs paragraphes de texte avec différentes rotations :

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Ajustez les valeurs de position et de rotation selon vos besoins.

## Étape 6 : Créer et configurer des fragments de texte

 Créer plusieurs`TextFragment` objets, définissez leur texte et leurs propriétés :

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

## Étape 7 : Ajouter des fragments de texte au paragraphe

 Ajoutez les fragments de texte créés au paragraphe à l'aide de la`AppendLine` méthode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Étape 8 : Créez un TextBuilder et ajoutez le paragraphe

 Créer un`TextBuilder` objet utilisant le`pdfPage` et ajoutez le paragraphe de texte à la page PDF :

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Étape 9 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide de la commande`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated4_out.pdf"` avec le nom du fichier de sortie souhaité.

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

## Conclusion

Félicitations ! Vous avez appris avec succès à faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la création du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Faire pivoter le texte à l'aide du paragraphe de texte et du générateur » ?

R : Le didacticiel « Faire pivoter du texte à l'aide d'un paragraphe de texte et d'un générateur » fournit un guide complet sur la façon d'utiliser la bibliothèque Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un document PDF. Le didacticiel présente des instructions étape par étape et inclut un exemple de code C# pour réaliser une rotation de texte avec des paragraphes et une mise en forme personnalisée.

#### Q : En quoi ce tutoriel est-il différent des tutoriels précédents sur la rotation de texte ?

R : Contrairement aux didacticiels précédents, ce didacticiel combine l'utilisation de paragraphes de texte, de générateurs et d'angles de rotation pour obtenir un effet de rotation de texte plus avancé. Il montre comment générer plusieurs paragraphes de texte avec différents angles de rotation et appliquer une mise en forme personnalisée à des fragments de texte individuels.

#### Q : Quelle est l’importance d’utiliser des paragraphes de texte et des générateurs pour la rotation du texte ?

: L'utilisation de paragraphes de texte et de générateurs permet un meilleur contrôle de la rotation et de la mise en forme du texte. Les paragraphes de texte offrent une manière structurée d'organiser les fragments de texte, tandis que les générateurs facilitent la création et la manipulation du contenu textuel dans le document PDF.

#### Q : Puis-je appliquer des angles de rotation différents à chaque paragraphe de texte ?

 R : Oui, vous pouvez appliquer différents angles de rotation à chaque paragraphe de texte en définissant le`Rotation` propriété de la`TextParagraph` objet. Cela vous permet de créer des effets de rotation de texte divers et dynamiques dans le document PDF.

#### Q : Comment personnaliser la mise en forme des fragments de texte dans les paragraphes de texte ?

 R : Vous pouvez personnaliser la mise en forme des fragments de texte en définissant diverses propriétés du`TextState` dans chaque`TextFragment` objet. Les propriétés telles que la taille de la police, le type de police, les couleurs de premier plan et d'arrière-plan et le soulignement peuvent être ajustées pour obtenir l'effet visuel souhaité.

#### Q : Puis-je créer des effets de rotation de texte plus complexes en utilisant cette méthode ?

: Absolument. En créant de manière itérative plusieurs paragraphes de texte avec différents angles de rotation et options de formatage, vous pouvez obtenir des effets de rotation de texte complexes et visuellement attrayants qui peuvent améliorer la lisibilité et l'esthétique de vos documents PDF.

#### Q : Est-il possible de combiner la rotation de texte avec d’autres techniques de manipulation de texte ?

R : Oui, vous pouvez combiner la rotation de texte avec d'autres techniques de manipulation de texte fournies par la bibliothèque Aspose.PDF. Cela inclut l'ajout de tableaux, d'images, d'hyperliens et bien plus encore pour créer des documents PDF riches et informatifs.

#### Q : Ai-je besoin d'une licence spéciale pour utiliser la bibliothèque Aspose.PDF dans mon projet ?

R : Oui, vous avez besoin d'une licence Aspose valide pour utiliser la bibliothèque Aspose.PDF dans votre projet. Vous pouvez obtenir une licence sur le site Web d'Aspose, qui vous fournira les informations d'identification nécessaires pour intégrer et utiliser efficacement la bibliothèque.