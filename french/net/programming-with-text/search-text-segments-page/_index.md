---
title: Page Rechercher des segments de texte
linktitle: Page Rechercher des segments de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher des segments de texte sur une page dans un document PDF et récupérer leurs propriétés à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 470
url: /fr/net/programming-with-text/search-text-segments-page/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher des segments de texte spécifiques sur une page d'un document PDF et récupérer leurs propriétés. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 3 : Définissez le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de la`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Chargez le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Remplacer`"SearchTextSegmentsPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec la phrase de recherche souhaitée.

## Étape 6 : Accepter l'absorbeur pour une page spécifique

Acceptez l'absorbeur pour la page souhaitée du document :

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Remplacer`2` avec le numéro de page souhaité (index de base 1).

## Étape 7 : Récupérer les segments de texte extraits

 Obtenez les segments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 8 : bouclez sur les segments de texte

Parcourez les segments de texte récupérés et accédez à leurs propriétés :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Modifiez le code dans la boucle pour effectuer d'autres actions sur chaque segment de texte si nécessaire.

### Exemple de code source pour la page de recherche de segments de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès à rechercher des segments de texte spécifiques sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce tutoriel a fourni un guide étape par étape, du chargement du document à l'accès aux segments de texte extraits. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour effectuer des recherches avancées de segments de texte dans des fichiers PDF.