---
title: Rechercher du texte et dessiner un rectangle
linktitle: Rechercher du texte et dessiner un rectangle
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rechercher du texte dans un PDF, dessinez des rectangles autour du texte trouvé et enregistrez le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 460
url: /fr/net/programming-with-text/search-text-and-draw-rectangle/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, dessiner un rectangle autour du texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Étape 3 : Définissez le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de la`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Chargez le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Remplacer`"SearchAndGetTextFromAll.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 6 : Activer la recherche d'expressions régulières

Activez la recherche d'expressions régulières en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Étape 7 : Rechercher sur toutes les pages

Acceptez l'absorbeur pour toutes les pages du document :

```csharp
document.Pages.Accept(textAbsorber);
```

## Étape 8 : Dessinez un rectangle autour du texte trouvé

 Créer un`PdfContentEditor` objet et parcourez les fragments de texte récupérés, en dessinant un rectangle autour de chaque segment de texte :

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Étape 9 : Enregistrez le document modifié

Enregistrez le document modifié :

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Assurez-vous de remplacer`"SearchTextAndDrawRectangle_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour rechercher du texte et dessiner un rectangle à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusion

Toutes nos félicitations! Vous avez appris à rechercher un texte spécifique dans un document PDF, à dessiner un rectangle autour du texte trouvé et à enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la configuration du projet à l'exécution des actions requises. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler du texte et dessiner des rectangles dans des fichiers PDF.