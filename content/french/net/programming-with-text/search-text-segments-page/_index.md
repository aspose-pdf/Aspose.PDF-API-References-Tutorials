---
title: Rechercher des segments de texte dans une page d'un fichier PDF
linktitle: Rechercher des segments de texte dans une page d'un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher des segments de texte sur une page dans un fichier PDF et récupérer leurs propriétés à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 470
url: /fr/net/programming-with-text/search-text-segments-page/
---
Ce tutoriel explique comment utiliser Aspose.PDF pour .NET pour rechercher des segments de texte spécifiques sur une page d'un fichier PDF et récupérer leurs propriétés. Le code source C# fourni illustre le processus étape par étape.

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
```

## Étape 3 : définir le chemin d’accès au répertoire du document

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de l'`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Charger le document PDF

 Chargez le document PDF à l'aide de la`Document` classe:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Remplacer`"SearchTextSegmentsPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec la phrase de recherche souhaitée.

## Étape 6 : Accepter l'absorbeur pour une page spécifique

Accepter l'absorbeur pour la page souhaitée du document :

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Remplacer`2` avec le numéro de page souhaité (index basé sur 1).

## Étape 7 : Récupérer les segments de texte extraits

 Obtenez les segments de texte extraits à l'aide de`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 8 : Parcourir les segments de texte

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

Modifiez le code dans la boucle pour effectuer d’autres actions sur chaque segment de texte si nécessaire.

### Exemple de code source pour la page de recherche de segments de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Créez un objet TextAbsorber pour rechercher toutes les instances de la phrase de recherche d'entrée
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

Félicitations ! Vous avez appris avec succès à rechercher des segments de texte spécifiques sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, du chargement du document à l'accès aux segments de texte extraits. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour effectuer des recherches avancées de segments de texte dans des fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Rechercher des segments de texte dans un fichier PDF » ?

R : Le didacticiel « Rechercher des segments de texte dans une page d'un fichier PDF » fournit un guide complet sur la façon d'utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher des segments de texte spécifiques sur une page particulière d'un document PDF. Il couvre le processus de configuration d'un projet, de chargement d'un document PDF, de recherche de segments de texte et de récupération de leurs propriétés à l'aide du code C#.

#### Q : Comment ce didacticiel aide-t-il à rechercher des segments de texte spécifiques dans un document PDF ?

R : Ce didacticiel illustre le processus de localisation et d'extraction de segments de texte spécifiques sur une page particulière d'un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent rechercher efficacement les segments de texte souhaités et récupérer des informations sur leurs propriétés.

#### Q : Quels sont les prérequis nécessaires pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web d'Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour rechercher et travailler avec des documents PDF.

#### Q : Puis-je utiliser ce didacticiel pour rechercher des segments de texte spécifiques sur n’importe quelle page d’un PDF ?

R : Oui, ce didacticiel fournit des instructions sur la manière de rechercher des segments de texte spécifiques sur une page sélectionnée d'un document PDF. Il guide les utilisateurs dans la configuration d'un projet, le chargement d'un PDF et l'utilisation de la bibliothèque Aspose.PDF pour localiser et récupérer les propriétés des segments de texte souhaités.

#### Q : Comment puis-je spécifier le texte que je souhaite rechercher dans ce tutoriel ?

 A : Pour spécifier le texte que vous souhaitez rechercher, créez un`TextFragmentAbsorber` objet et définir son paramètre de recherche à l'aide de la`Text` propriété. Remplacez la valeur par défaut`"text"` dans le code du didacticiel avec la phrase de recherche souhaitée.

#### Q : Comment récupérer les propriétés des segments de texte extraits ?

Après avoir accepté le`TextFragmentAbsorber` pour une page spécifique du PDF, vous pouvez récupérer les segments de texte extraits à l'aide de la`TextFragments` propriété de l'objet absorbeur. Cela permet d'accéder à une collection de fragments de texte, chacun contenant plusieurs segments de texte.

#### Q : Puis-je personnaliser le code pour effectuer des actions supplémentaires sur chaque segment de texte ?

R : Absolument. L'exemple de code du didacticiel fournit une boucle permettant d'effectuer une itération sur les segments de texte récupérés. Vous pouvez personnaliser le code dans cette boucle pour effectuer des actions supplémentaires sur chaque segment de texte, en fonction des exigences de votre projet.

#### Q : Comment enregistrer le document PDF modifié après avoir extrait des segments de texte ?

R : Ce didacticiel se concentre principalement sur la recherche de segments de texte et la récupération de leurs propriétés. Si vous avez l'intention d'apporter des modifications au PDF, vous pouvez vous référer à d'autres documents Aspose.PDF pour apprendre à manipuler et enregistrer le document en fonction de vos besoins spécifiques.