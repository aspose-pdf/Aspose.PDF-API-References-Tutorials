---
title: Page de recherche de segments de texte dans un fichier PDF
linktitle: Page de recherche de segments de texte dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment rechercher des segments de texte sur une page dans un fichier PDF et récupérer leurs propriétés à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 470
url: /fr/net/programming-with-text/search-text-segments-page/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher des segments de texte spécifiques sur une page d'un fichier PDF et récupérer leurs propriétés. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 3 : Définir le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Charger le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Remplacer`"SearchTextSegmentsPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche saisie :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec la phrase de recherche souhaitée.

## Étape 6 : Acceptez l'absorbeur pour une page spécifique

Acceptez l'absorbeur pour la page souhaitée du document :

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Remplacer`2` avec le numéro de page souhaité (index de base 1).

## Étape 7 : Récupérer les segments de texte extraits

 Obtenez les segments de texte extraits à l'aide du`TextFragments` propriété du`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 8 : Parcourez les segments de texte

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
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Créez un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Acceptez l'absorbeur pour toutes les pages
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtenez les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parcourez les fragments
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

Toutes nos félicitations! Vous avez appris avec succès comment rechercher des segments de texte spécifiques sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, du chargement du document à l'accès aux segments de texte extraits. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour effectuer des recherches avancées de segments de texte dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher des segments de texte dans un fichier PDF » ?

: Le didacticiel « Rechercher des segments de texte dans un fichier PDF » fournit un guide complet sur la façon d'utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher des segments de texte spécifiques sur une page particulière d'un document PDF. Il couvre le processus de configuration d'un projet, de chargement d'un document PDF, de recherche de segments de texte et de récupération de leurs propriétés à l'aide du code C#.

#### Q : Comment ce didacticiel aide-t-il à rechercher des segments de texte spécifiques dans un document PDF ?

R : Ce didacticiel montre le processus de localisation et d'extraction de segments de texte spécifiques sur une page particulière d'un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent rechercher efficacement les segments de texte souhaités et récupérer des informations sur leurs propriétés.

#### Q : Quels prérequis sont requis pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour rechercher et travailler avec des documents PDF.

#### Q : Puis-je utiliser ce didacticiel pour rechercher des segments de texte spécifiques sur n'importe quelle page d'un PDF ?

R : Oui, ce didacticiel fournit des instructions sur la façon de rechercher des segments de texte spécifiques sur une page sélectionnée d'un document PDF. Il guide les utilisateurs dans la configuration d'un projet, le chargement d'un PDF et l'utilisation de la bibliothèque Aspose.PDF pour localiser et récupérer les propriétés des segments de texte souhaités.

#### Q : Comment puis-je spécifier le texte que je souhaite rechercher dans ce didacticiel ?

 R : Pour spécifier le texte que vous souhaitez rechercher, créez un`TextFragmentAbsorber` objet et définissez son paramètre de recherche à l'aide du`Text` propriété. Remplacer la valeur par défaut`"text"` dans le code du didacticiel avec la phrase de recherche souhaitée.

#### Q : Comment récupérer les propriétés des segments de texte extraits ?

Après avoir accepté le`TextFragmentAbsorber` pour une page spécifique du PDF, vous pouvez récupérer les segments de texte extraits à l'aide du`TextFragments` propriété de l’objet absorbeur. Cela donne accès à une collection de fragments de texte, chacun contenant plusieurs segments de texte.

#### Q : Puis-je personnaliser le code pour effectuer des actions supplémentaires sur chaque segment de texte ?

R : Absolument. L'exemple de code du didacticiel fournit une boucle pour parcourir les segments de texte récupérés. Vous pouvez personnaliser le code dans cette boucle pour effectuer des actions supplémentaires sur chaque segment de texte, en fonction des exigences de votre projet.

#### Q : Comment puis-je enregistrer le document PDF modifié après avoir extrait les segments de texte ?

R : Ce didacticiel se concentre principalement sur la recherche de segments de texte et la récupération de leurs propriétés. Si vous avez l'intention d'apporter des modifications au PDF, vous pouvez vous référer à une autre documentation Aspose.PDF pour savoir comment manipuler et enregistrer le document en fonction de vos besoins spécifiques.