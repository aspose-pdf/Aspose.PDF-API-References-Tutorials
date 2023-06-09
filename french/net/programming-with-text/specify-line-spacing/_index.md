---
title: Spécifier l'espacement des lignes
linktitle: Spécifier l'espacement des lignes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à spécifier l'espacement des lignes dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 510
url: /fr/net/programming-with-text/specify-line-spacing/
---

Ce didacticiel explique comment spécifier l'interligne dans un document PDF à l'aide de Aspose.PDF pour .NET. Le code source C# fourni illustre le processus étape par étape.

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
using System.IO;
```

## Étape 3 : Définissez le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de la`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Chargez le fichier PDF d'entrée

 Chargez le fichier PDF d'entrée à l'aide du`Document` classe:

```csharp
Document doc = new Document();
```

## Étape 5 : Créer des options de formatage de texte

 Créer un`TextFormattingOptions` objet et définissez le mode d'interligne sur`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Étape 6 : créer un fragment de texte

 Créer un`TextFragment` objet et spécifiez le contenu du texte :

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Étape 7 : chargez le fichier de police (facultatif)

 Si vous souhaitez utiliser une police spécifique pour le texte, chargez le fichier de police TrueType dans un`FileStream` objet:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Remplacer`"HPSimplified.TTF"`avec le nom réel du fichier de police.

## Étape 8 : Spécifiez la position du texte et l'espacement des lignes

 Définissez la position du fragment de texte et attribuez le`TextFormattingOptions` au`TextState.FormattingOptions` propriété:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Étape 9 : Ajouter le texte au document

 Ajoutez le fragment de texte au document, soit en l'ajoutant à un`TextBuilder` ou directement sur une page`Paragraphs` collection:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Étape 10 : Enregistrez le document PDF résultant

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Assurez-vous de remplacer`"SpecifyLineSpacing_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour spécifier l'espacement des lignes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Charger le fichier PDF d'entrée
Document doc = new Document();
//Créer TextFormattingOptions avec LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Créer un objet générateur de texte pour la première page du document
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Créer un fragment de texte avec un exemple de chaîne
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Charger la police TrueType dans l'objet de flux
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Définir le nom de la police pour la chaîne de texte
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Spécifiez la position du fragment de texte
		textFragment.Position = new Position(100, 600);
		//Définissez TextFormattingOptions du fragment actuel sur prédéfini (qui pointe vers LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Ajoutez le texte à TextBuilder afin qu'il puisse être placé sur le fichier PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Enregistrer le document PDF résultant
	doc.Save(dataDir);
}
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment spécifier l'interligne dans un document PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la configuration du projet à l'enregistrement du document modifié. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour personnaliser l'interligne du texte dans les fichiers PDF.