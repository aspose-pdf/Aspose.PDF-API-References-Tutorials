---
title: Page de recherche et d'obtention de texte
linktitle: Page de recherche et d'obtention de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher et obtenir du texte à partir d'une page spécifique d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 430
url: /fr/net/programming-with-text/search-and-get-text-page/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher et obtenir du texte à partir d'une page spécifique d'un document PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 3 : Chargez le document PDF

 Définissez le chemin d'accès à votre répertoire de documents PDF et chargez le document à l'aide de la`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Rechercher et extraire du texte d'une page

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée sur une page spécifique :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Remplacer`"Figure"` avec le texte réel que vous souhaitez rechercher.

## Étape 5 : Rechercher sur une page spécifique

Accepter l'absorbeur pour une page spécifique du document :

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 6 : obtenir des fragments de texte extraits

Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 7 : bouclez sur les fragments et les segments de texte

Parcourez les fragments de texte obtenus et leurs segments, et accédez à leurs propriétés :

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

Vous pouvez modifier le code dans la boucle pour effectuer d'autres actions sur chaque segment de texte.

### Exemple de code source pour rechercher et obtenir une page de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment rechercher et obtenir du texte à partir d'une page spécifique d'un document PDF en utilisant Aspose.PDF pour .NET. Ce tutoriel a fourni un guide étape par étape, du chargement du document à l'accès aux segments de texte extraits. Vous pouvez maintenant intégrer