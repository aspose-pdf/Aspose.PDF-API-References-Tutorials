---
title: Rechercher et obtenir une page de texte dans un fichier PDF
linktitle: Rechercher et obtenir une page de texte dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment rechercher et obtenir du texte à partir d'une page spécifique dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 430
url: /fr/net/programming-with-text/search-and-get-text-page/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher et obtenir du texte à partir d'une page spécifique dans un fichier PDF. Le code source C# fourni illustre le processus étape par étape.

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
```

## Étape 3 : Charger le document PDF

 Définissez le chemin d'accès à votre répertoire de documents PDF et chargez le document à l'aide du`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Rechercher et extraire du texte d'une page

 Créer un`TextFragmentAbsorber`objet pour rechercher toutes les instances de la phrase de recherche saisie sur une page spécifique :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Remplacer`"Figure"` avec le texte réel que vous souhaitez rechercher.

## Étape 5 : Rechercher sur une page spécifique

Acceptez l'absorbeur pour une page spécifique du document :

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 6 : obtenir des fragments de texte extraits

Obtenez les fragments de texte extraits en utilisant le`TextFragments` propriété du`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 7 : Parcourez les fragments et segments de texte

Parcourez les fragments de texte obtenus et leurs segments et accédez à leurs propriétés :

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
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Créez un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Acceptez l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenez les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parcourez les fragments
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

Toutes nos félicitations! Vous avez appris avec succès comment rechercher et obtenir du texte à partir d'une page spécifique d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, du chargement du document à l'accès aux segments de texte extraits. Vous pouvez désormais intégrer

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher et obtenir une page de texte » ?

: Le didacticiel « Rechercher et obtenir une page de texte » est conçu pour illustrer comment utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher et récupérer du texte à partir d'une page spécifique dans un fichier PDF. Le didacticiel fournit des instructions détaillées et un exemple de code C# pour démontrer le processus.

#### Q : Comment ce didacticiel aide-t-il à extraire le texte d'une page spécifique d'un document PDF ?

R : Ce didacticiel vous guide tout au long du processus d'extraction de texte d'une page particulière d'un document PDF à l'aide de la bibliothèque Aspose.PDF. Il décrit les étapes nécessaires et fournit du code C# pour rechercher une expression de texte spécifiée sur la page sélectionnée et récupérer les segments de texte associés.

#### Q : Quels sont les prérequis pour suivre ce tutoriel ?

R : Avant de commencer ce didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou utiliser NuGet pour l'intégrer à votre projet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'utiliser les capacités de la bibliothèque dans votre projet.

#### Q : Puis-je rechercher du texte sur une page spécifique du document PDF ?

R : Oui, ce didacticiel montre comment rechercher du texte sur une page spécifique d'un document PDF. Il s'agit d'utiliser le`TextFragmentAbsorber` classe pour localiser les instances d’une phrase de texte particulière sur la page choisie.

#### Q : Comment puis-je accéder aux segments de texte extraits d'une page spécifique ?

 R : Après avoir recherché le texte sur la page désignée, vous pouvez accéder aux segments de texte extraits à l'aide du`TextSegments` propriété du`TextFragment` objet. Cette propriété donne accès à une collection de`TextSegment` objets qui contiennent le texte extrait et les informations associées.

#### Q : Quelles informations puis-je récupérer à partir des segments de texte extraits ?

R : Vous pouvez récupérer divers détails des segments de texte extraits, notamment le contenu du texte, la position (coordonnées X et Y), les informations sur la police (nom, taille, couleur, etc.), et bien plus encore. L'exemple de code du didacticiel montre comment accéder et imprimer ces détails pour chaque segment de texte.

#### Q : Puis-je effectuer des actions personnalisées sur les segments de texte extraits ?

: Certainement. Une fois que vous disposez des segments de texte extraits, vous pouvez personnaliser le code dans la boucle pour effectuer des actions supplémentaires sur chaque segment. Cela peut inclure l'enregistrement du texte extrait, l'analyse des modèles de texte ou l'application de modifications de formatage.