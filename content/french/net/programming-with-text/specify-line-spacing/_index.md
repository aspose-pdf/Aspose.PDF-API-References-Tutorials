---
title: Spécifier l'espacement des lignes dans un fichier PDF
linktitle: Spécifier l'espacement des lignes dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment spécifier l'espacement des lignes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 510
url: /fr/net/programming-with-text/specify-line-spacing/
---
Ce didacticiel explique comment spécifier l'espacement des lignes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre le processus étape par étape.

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
using System.IO;
```

## Étape 3 : Définir le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Chargez le fichier PDF d'entrée

 Chargez le fichier PDF d'entrée à l'aide du`Document` classe:

```csharp
Document doc = new Document();
```

## Étape 5 : Créer des options de formatage de texte

 Créer un`TextFormattingOptions` objet et définissez le mode d'espacement des lignes sur`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Étape 6 : Créer un TextFragment

 Créer un`TextFragment` objet et spécifiez le contenu du texte :

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Étape 7 : Chargez le fichier de police (facultatif)

 Si vous souhaitez utiliser une police spécifique pour le texte, chargez le fichier de police TrueType dans un`FileStream` objet:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Remplacer`"HPSimplified.TTF"` avec le nom réel du fichier de police.

## Étape 8 : Spécifiez la position du texte et l'espacement des lignes

 Définissez la position du fragment de texte et attribuez-lui le`TextFormattingOptions` au`TextState.FormattingOptions` propriété:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Étape 9 : Ajouter le texte au document

 Ajoutez le fragment de texte au document, soit en l'ajoutant à un`TextBuilder` ou directement à une page`Paragraphs` collection:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Étape 10 : Enregistrez le document PDF résultant

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Assurez-vous de remplacer`"SpecifyLineSpacing_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour spécifier l'espacement des lignes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
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
	// Charger la police TrueType dans l'objet flux
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Définir le nom de la police pour la chaîne de texte
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

Toutes nos félicitations! Vous avez appris avec succès comment spécifier l'espacement des lignes dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la configuration du projet jusqu'à l'enregistrement du document modifié. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour personnaliser l'espacement des lignes du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Spécifier l'espacement des lignes dans un fichier PDF » ?

: Le didacticiel « Spécifier l'espacement des lignes dans un fichier PDF » vise à guider les utilisateurs sur la façon d'utiliser la bibliothèque Aspose.PDF pour .NET pour personnaliser l'espacement des lignes du texte dans un document PDF. Le didacticiel fournit des instructions étape par étape et des exemples de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à spécifier l'espacement des lignes dans un document PDF ?

R : Ce didacticiel aide les utilisateurs à comprendre comment utiliser les fonctionnalités d'Aspose.PDF pour .NET pour spécifier l'espacement des lignes pour le texte dans un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent ajuster l'espacement des lignes en fonction de leurs préférences.

#### Q : Quels prérequis sont nécessaires pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permet de tirer parti des fonctionnalités de la bibliothèque pour travailler avec des documents PDF et personnaliser l'espacement des lignes.

#### Q : Puis-je utiliser ce didacticiel pour spécifier l’espacement des lignes pour n’importe quel type de texte ?

: Oui, ce didacticiel fournit des instructions sur la manière de spécifier l'espacement des lignes pour tout contenu textuel dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser les exemples de code fournis pour ajuster l'espacement des lignes du texte en fonction de vos besoins.

#### Q : Comment spécifier le mode d'espacement des lignes dans le didacticiel ?

 R : Le didacticiel montre comment créer un`TextFormattingOptions` objet et définir son`LineSpacing` propriété à`TextFormattingOptions.LineSpacingMode.FullSize`. Ce mode spécifie un interligne complet pour le contenu du texte.

#### Q : Comment puis-je charger une police spécifique pour le texte ?

 R : Si vous souhaitez utiliser une police spécifique pour le contenu du texte, le didacticiel fournit des conseils sur la façon de charger un fichier de police TrueType dans un`FileStream` objet et définissez-le comme police pour le`TextFragment`. Cela vous permet de personnaliser la police du texte ainsi que son interligne.

#### Q : Comment personnaliser la position du texte dans le document PDF ?

 R : Pour personnaliser la position du texte, créez un`TextFragment` objet et définir son`Position`propriété aux coordonnées souhaitées (X et Y). Cela vous permet de contrôler où le texte est placé dans le document PDF.

#### Q : Puis-je appliquer ces modifications d’espacement des lignes aux documents PDF existants ?

 R : Oui, vous pouvez modifier l'espacement des lignes du texte dans les documents PDF existants. Le didacticiel montre comment créer un`TextFragment` avec l'espacement et la position des lignes spécifiés, puis ajoutez-le au fichier d'une page.`Paragraphs` collection.