---
title: Rechercher du texte avec Dot Net Regex
linktitle: Rechercher du texte avec Dot Net Regex
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher du texte à l’aide d’expressions régulières .NET dans un document PDF à l’aide d’Aspose.PDF pour .NET.
type: docs
weight: 480
url: /fr/net/programming-with-text/search-text-with-dot-net-regex/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 4 : créer un objet .NET Regex

 Créer un`.NET Regex` objet pour définir le modèle de recherche :

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Charger le document PDF

 Chargez le document PDF à l'aide de la`Document` classe:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Remplacer`"SearchTextRegex.pdf"` avec le nom réel de votre fichier PDF.

## Étape 6 : Obtenir une page spécifique

Obtenez la page souhaitée du document :

```csharp
Page page = document.Pages[1];
```

 Remplacer`1` avec le numéro de page souhaité (index basé sur 1).

## Étape 7 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de l'expression régulière d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Étape 8 : Accepter l'absorbeur pour la page

Accepter l'absorbeur pour la page :

```csharp
page.Accept(textFragmentAbsorber);
```

## Étape 9 : Récupérer les fragments de texte extraits

 Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 10 : Parcourir les fragments de texte

Parcourez les fragments de texte récupérés et effectuez les actions souhaitées :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modifiez le code dans la boucle pour effectuer d’autres actions sur chaque fragment de texte si nécessaire.

### Exemple de code source pour la recherche de texte avec Dot Net Regex à l'aide d'Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un objet Regex pour trouver tous les mots
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Ouvrir le document
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Obtenir une page particulière
Page page = document.Pages[1];
// Créez un objet TextAbsorber pour rechercher toutes les instances de l'expression régulière d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Accepter l'absorbeur pour la page
page.Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusion

Félicitations ! Vous avez appris avec succès à rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la configuration du projet à l'accès aux fragments de texte extraits. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour effectuer des recherches de texte avancées dans des fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Rechercher du texte avec Dot Net Regex » ?

R : Le didacticiel « Rechercher du texte avec Dot Net Regex » vise à guider les utilisateurs dans l'utilisation de la bibliothèque Aspose.PDF pour .NET pour rechercher du texte dans un document PDF à l'aide d'expressions régulières .NET. Le didacticiel fournit des instructions étape par étape et des exemples de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à rechercher du texte à l’aide d’expressions régulières .NET dans un PDF ?

R : Ce didacticiel aide les utilisateurs à comprendre comment exploiter les fonctionnalités d'Aspose.PDF pour .NET pour rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent rechercher efficacement des modèles de texte qui correspondent à leurs expressions régulières spécifiées.

#### Q : Quels sont les prérequis nécessaires pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web d'Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour rechercher et travailler avec des documents PDF.

#### Q : Puis-je utiliser ce didacticiel pour rechercher n’importe quel type de texte spécifique à l’aide d’expressions régulières .NET ?

 R : Oui, ce didacticiel fournit des instructions sur la manière de rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. Vous pouvez personnaliser le`.NET Regex` objet pour définir le modèle de recherche spécifique que vous souhaitez utiliser.

#### Q : Comment spécifier le modèle d’expression régulière .NET à rechercher dans ce didacticiel ?

 A : Pour spécifier le modèle d’expression régulière .NET que vous souhaitez rechercher, créez un`.NET Regex` objet et définissez son modèle à l'aide de la syntaxe d'expression régulière appropriée. Remplacez la valeur par défaut`@"[\S]+"` dans le code du didacticiel avec l'expression régulière souhaitée.

#### Q : Comment récupérer les propriétés des fragments de texte extraits ?

 A : Après avoir accepté le`TextFragmentAbsorber` pour une page spécifique du PDF, vous pouvez récupérer les fragments de texte extraits à l'aide de la`TextFragments` propriété de l'objet absorbeur. Cela permet d'accéder à une collection de fragments de texte qui correspondent à l'expression régulière .NET spécifiée.

#### Q : Puis-je personnaliser le code pour effectuer des actions supplémentaires sur chaque fragment de texte extrait ?

: Certainement. L'exemple de code du didacticiel comprend une boucle permettant d'effectuer une itération sur les fragments de texte récupérés. Vous pouvez personnaliser le code dans cette boucle pour effectuer des actions supplémentaires sur chaque fragment de texte extrait en fonction des exigences de votre projet.

#### Q : Comment enregistrer le document PDF modifié après avoir extrait des fragments de texte ?

R : Ce didacticiel se concentre principalement sur la recherche de texte à l'aide d'expressions régulières .NET et sur la récupération de fragments de texte. Si vous avez l'intention d'apporter des modifications au PDF, vous pouvez vous référer à d'autres documents Aspose.PDF pour apprendre à manipuler et enregistrer le document en fonction de vos besoins spécifiques.