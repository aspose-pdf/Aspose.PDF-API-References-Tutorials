---
title: Rechercher une expression régulière dans un fichier PDF
linktitle: Rechercher une expression régulière dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher et récupérer du texte à l'aide d'expressions régulières dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 440
url: /fr/net/programming-with-text/search-regular-expression/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher et récupérer du texte correspondant à une expression régulière dans un fichier PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 3 : Charger le document PDF

 Définissez le chemin d'accès à votre répertoire de documents PDF et chargez le document à l'aide de l'`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Recherche avec une expression régulière

 Créer un`TextFragmentAbsorber` objet et définissez le modèle d'expression régulière pour trouver toutes les phrases qui correspondent au modèle :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Comme en 1999-2000
```

 Remplacer`"\\d{4}-\\d{4}"` avec le modèle d'expression régulière souhaité.

## Étape 5 : définir les options de recherche de texte

 Créer un`TextSearchOptions` objet et le définir sur le`TextSearchOptions` propriété de la`TextFragmentAbsorber` objet pour permettre l’utilisation d’expressions régulières :

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Étape 6 : Rechercher sur toutes les pages

Accepter l'absorbeur pour toutes les pages du document :

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 7 : Récupérer les fragments de texte extraits

Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 8 : Parcourir les fragments de texte

Parcourez les fragments de texte récupérés et accédez à leurs propriétés :

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

### Exemple de code source pour la recherche d'expressions régulières à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Comme en 1999-2000
// Définir l’option de recherche de texte pour spécifier l’utilisation des expressions régulières
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Félicitations ! Vous avez appris avec succès à rechercher et à récupérer du texte correspondant à une expression régulière dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, du chargement du document à l'accès aux fragments de texte extraits. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour effectuer des recherches de texte avancées dans des fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Rechercher une expression régulière dans un fichier PDF » ?

R : Le didacticiel « Rechercher une expression régulière dans un fichier PDF » vise à montrer comment utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher et extraire du texte correspondant à un modèle d'expression régulière spécifié dans un fichier PDF. Le didacticiel fournit des conseils complets et un exemple de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à rechercher du texte à l’aide d’expressions régulières dans un document PDF ?

R : Ce didacticiel fournit une approche étape par étape de l'utilisation de la bibliothèque Aspose.PDF pour effectuer des recherches de texte dans un document PDF en fonction d'un modèle d'expression régulière. Il détaille comment configurer le projet, charger le document PDF, définir un modèle d'expression régulière et récupérer les fragments de texte correspondants.

#### Q : Quels sont les prérequis pour suivre ce tutoriel ?

R : Avant de commencer ce didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'intégrer à votre projet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'exploiter les fonctionnalités de la bibliothèque au sein de votre projet.

#### Q : Puis-je utiliser des expressions régulières pour rechercher du texte dans un document PDF ?

 R : Oui, ce didacticiel montre comment utiliser des expressions régulières pour rechercher et extraire du texte à partir d'un document PDF. Il s'agit d'utiliser les`TextFragmentAbsorber` classe et spécification d'un modèle d'expression régulière pour trouver des phrases qui correspondent au modèle fourni.

#### Q : Comment définir le modèle d’expression régulière pour la recherche de texte ?

 A : Pour définir un modèle d’expression régulière pour la recherche de texte, créez un`TextFragmentAbsorber` objet et définir son modèle à l'aide de la`Text` paramètre. Remplacez le modèle par défaut`"\\d{4}-\\d{4}"` dans le code du didacticiel avec le modèle d'expression régulière souhaité.

#### Q : Comment puis-je activer l’utilisation d’expressions régulières pour la recherche de texte ?

 A : L'utilisation d'expressions régulières est activée en créant une`TextSearchOptions` objet et définir sa valeur sur`true` . Affectez cet objet à la`TextSearchOptions` propriété de la`TextFragmentAbsorber` exemple. Cela garantit que le modèle d'expression régulière est appliqué pendant la recherche de texte.

#### Q : Puis-je récupérer des fragments de texte qui correspondent au modèle d’expression régulière ?

 R : Absolument. Après avoir appliqué la recherche par expression régulière sur le document PDF, vous pouvez récupérer les fragments de texte extraits à l'aide de la fonction`TextFragments` propriété de la`TextFragmentAbsorber` objet. Ces fragments de texte contiennent les segments de texte qui correspondent au modèle d'expression régulière spécifié.

#### Q : À quoi puis-je accéder à partir des fragments de texte récupérés ?

R : À partir des fragments de texte récupérés, vous pouvez accéder à diverses propriétés telles que le contenu du texte correspondant, la position (coordonnées X et Y), les informations sur la police (nom, taille, couleur), etc. L'exemple de code dans la boucle du didacticiel montre comment accéder à ces propriétés et les afficher.

#### Q : Comment puis-je personnaliser les actions sur les fragments de texte extraits ?

R : Une fois que vous avez extrait les fragments de texte, vous pouvez personnaliser le code dans la boucle pour effectuer des actions supplémentaires sur chaque fragment de texte. Cela peut inclure l'enregistrement du texte extrait, l'analyse des modèles ou l'implémentation de modifications de formatage en fonction de vos besoins.