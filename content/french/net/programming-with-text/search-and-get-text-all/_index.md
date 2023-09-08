---
title: Rechercher et obtenir du texte tout
linktitle: Rechercher et obtenir du texte tout
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment rechercher et obtenir du texte sur toutes les pages d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 420
url: /fr/net/programming-with-text/search-and-get-text-all/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher et obtenir du texte sur toutes les pages d'un document PDF. Le code source C# fourni illustre le processus étape par étape.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Rechercher et extraire du texte

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche saisie :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec le texte réel que vous souhaitez rechercher.

## Étape 5 : Rechercher sur toutes les pages

Acceptez l'absorbeur pour toutes les pages du document :

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 6 : obtenir des fragments de texte extraits

Obtenez les fragments de texte extraits en utilisant le`TextFragments` propriété du`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 7 : Parcourez les fragments de texte

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

### Exemple de code source pour Rechercher et obtenir du texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Créez un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Acceptez l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenez les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parcourez les fragments
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

Toutes nos félicitations! Vous avez appris avec succès comment rechercher et obtenir du texte à partir de toutes les pages d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, depuis le chargement du document jusqu'à l'accès aux fragments de texte extraits. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour analyser et traiter le contenu textuel des fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher et obtenir tout le texte » ?

R : Le didacticiel « Rechercher et obtenir tout le texte » montre comment utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher et extraire du texte de toutes les pages d'un document PDF. Le didacticiel fournit des instructions étape par étape ainsi qu'un exemple de code C# pour effectuer une recherche et une récupération de texte.

#### Q : Comment ce didacticiel aide-t-il à extraire du texte à partir de documents PDF ?

R : Ce didacticiel vous guide tout au long du processus d'extraction de texte de toutes les pages d'un document PDF. Il utilise la bibliothèque Aspose.PDF pour localiser des phrases de texte spécifiques et récupérer les informations associées, telles que la position, les propriétés de la police et les couleurs.

#### Q : Quels sont les prérequis pour suivre ce tutoriel ?

R : Avant de commencer ce didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou utiliser NuGet pour l'intégrer à votre projet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'accéder aux fonctionnalités de la bibliothèque dans votre projet.

#### Q : Comment rechercher un texte spécifique dans un document PDF ?

R : Vous pouvez utiliser le`TextFragmentAbsorber`classe pour trouver des instances d’une expression de recherche spécifique dans le document PDF. En créant une instance de cette classe et en spécifiant le texte cible, vous pouvez capturer toutes les occurrences de ce texte.

#### Q : Puis-je rechercher du texte sur toutes les pages du document PDF ?

 R : Oui, le didacticiel montre comment rechercher du texte sur toutes les pages du document PDF. Le`pdfDocument.Pages.Accept(textFragmentAbsorber)` La méthode est utilisée pour accepter l'absorbeur pour toutes les pages, vous permettant de rechercher le texte souhaité sur chaque page.

#### Q : Comment puis-je accéder aux fragments de texte extraits ?

 R : Après avoir recherché le texte, vous pouvez accéder aux fragments de texte extraits en utilisant le`TextFragments` propriété du`TextFragmentAbsorber` objet. Cette propriété donne accès à une collection de`TextFragment` objets qui contiennent le texte extrait et les informations associées.

#### Q : Quelles informations puis-je récupérer à partir des fragments de texte extraits ?

R : Vous pouvez récupérer divers détails des fragments de texte extraits, tels que le contenu réel du texte, la position (coordonnées X et Y), les informations sur la police (nom, taille, couleur, etc.), et bien plus encore. L'exemple de code du didacticiel montre comment accéder à ces détails et les imprimer.

#### Q : Puis-je effectuer d’autres actions sur les fragments de texte extraits ?

R : Absolument. Une fois que vous disposez des fragments de texte extraits, vous pouvez modifier le code dans la boucle pour effectuer des actions personnalisées sur chaque fragment. Cela peut inclure l'enregistrement du texte extrait, l'analyse des modèles de texte ou l'application de modifications de formatage.