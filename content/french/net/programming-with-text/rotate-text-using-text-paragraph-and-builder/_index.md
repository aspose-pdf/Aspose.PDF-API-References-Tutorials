---
title: Faire pivoter le texte à l'aide d'un paragraphe de texte et du générateur dans un fichier PDF
linktitle: Faire pivoter le texte à l'aide d'un paragraphe de texte et du générateur dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment faire pivoter du texte à l'aide d'un paragraphe de texte et d'un générateur dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 410
url: /fr/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un fichier PDF. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous d'avoir les éléments suivants :

- Connaissance de base du langage de programmation C#.
- Aspose.PDF pour la bibliothèque .NET installée. Vous pouvez l'obtenir sur le site Web Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Étape 3 : Créer le document PDF

 Initialisez le`Document` objet pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Ajouter une page

 Obtenez une page particulière du document en utilisant le`Pages.Add()` méthode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 5 : Créer et faire pivoter des paragraphes de texte

 Créer un`for` boucle pour générer plusieurs paragraphes de texte avec des rotations différentes :

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

 Ajoutez les fragments de texte créés au paragraphe à l'aide du`AppendLine` méthode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Étape 8 : Créez un TextBuilder et ajoutez le paragraphe

 Créer un`TextBuilder` objet à l'aide du`pdfPage` et ajoutez le paragraphe de texte à la page PDF :

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Étape 9 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide du`Save` méthode:

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

Toutes nos félicitations! Vous avez appris avec succès comment faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la création du document jusqu'à l'enregistrement de la version modifiée. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Faire pivoter le texte à l'aide d'un paragraphe de texte et du générateur » ?

R : Le didacticiel « Faire pivoter le texte à l'aide d'un paragraphe de texte et d'un générateur » fournit un guide complet sur la façon d'utiliser la bibliothèque Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes de texte et de générateurs dans un document PDF. Le didacticiel montre des instructions étape par étape et comprend un exemple de code C# pour réaliser la rotation du texte avec des paragraphes et une mise en forme personnalisée.

#### Q : En quoi ce didacticiel est-il différent des didacticiels précédents sur la rotation de texte ?

R : Contrairement aux didacticiels précédents, ce didacticiel combine l'utilisation de paragraphes de texte, de générateurs et d'angles de rotation pour obtenir un effet de rotation de texte plus avancé. Il montre comment générer plusieurs paragraphes de texte avec différents angles de rotation et appliquer un formatage personnalisé à des fragments de texte individuels.

#### Q : Quelle est l'importance d'utiliser des paragraphes de texte et des générateurs pour la rotation du texte ?

R : L'utilisation de paragraphes de texte et de générateurs permet un contrôle amélioré sur la rotation et le formatage du texte. Les paragraphes de texte offrent un moyen structuré d'organiser des fragments de texte, tandis que les générateurs facilitent la création et la manipulation du contenu textuel dans le document PDF.

#### Q : Puis-je appliquer différents angles de rotation à chaque paragraphe de texte ?

 R : Oui, vous pouvez appliquer différents angles de rotation à chaque paragraphe de texte en définissant le`Rotation` propriété du`TextParagraph` objet. Cela vous permet de créer des effets de rotation de texte diversifiés et dynamiques dans le document PDF.

#### Q : Comment personnaliser le formatage des fragments de texte dans les paragraphes de texte ?

 R : Vous pouvez personnaliser le formatage des fragments de texte en définissant diverses propriétés du`TextState` au sein de chacun`TextFragment` objet. Les propriétés telles que la taille de la police, le type de police, les couleurs de premier plan et d’arrière-plan et le soulignement peuvent être ajustées pour obtenir l’effet visuel souhaité.

#### Q : Puis-je créer des effets de rotation de texte plus complexes en utilisant cette méthode ?

: Absolument. En créant de manière itérative plusieurs paragraphes de texte avec différents angles de rotation et options de formatage, vous pouvez obtenir des effets de rotation de texte complexes et visuellement attrayants qui peuvent améliorer la lisibilité et l'esthétique de vos documents PDF.

#### Q : Est-il possible de combiner la rotation du texte avec d’autres techniques de manipulation de texte ?

R : Oui, vous pouvez combiner la rotation du texte avec d'autres techniques de manipulation de texte fournies par la bibliothèque Aspose.PDF. Cela inclut l'ajout de tableaux, d'images, de liens hypertexte et bien plus encore pour créer des documents PDF riches et informatifs.

#### Q : Ai-je besoin d’une licence spéciale pour utiliser la bibliothèque Aspose.PDF dans mon projet ?

R : Oui, vous avez besoin d'une licence Aspose valide pour utiliser la bibliothèque Aspose.PDF dans votre projet. Vous pouvez obtenir une licence sur le site Web Aspose, qui vous fournira les informations d'identification nécessaires pour intégrer et utiliser efficacement la bibliothèque.