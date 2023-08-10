---
title: Rechercher et obtenir tout le texte
linktitle: Rechercher et obtenir tout le texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rechercher et à obtenir du texte de toutes les pages d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 420
url: /fr/net/programming-with-text/search-and-get-text-all/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher et obtenir du texte à partir de toutes les pages d'un document PDF. Le code source C# fourni illustre le processus étape par étape.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Rechercher et extraire du texte

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec le texte réel que vous souhaitez rechercher.

## Étape 5 : Rechercher sur toutes les pages

Acceptez l'absorbeur pour toutes les pages du document :

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 6 : obtenir des fragments de texte extraits

Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 7 : bouclez sur les fragments de texte

Parcourez les fragments de texte obtenus et accédez à leurs propriétés :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Vous pouvez modifier le code dans la boucle pour effectuer d'autres actions sur chaque fragment de texte.

### Exemple de code source pour rechercher et obtenir du texte tout en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment rechercher et obtenir du texte à partir de toutes les pages d'un document PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, du chargement du document à l'accès aux fragments de texte extraits. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour analyser et traiter le contenu textuel des fichiers PDF.