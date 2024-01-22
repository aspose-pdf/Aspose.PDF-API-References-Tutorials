---
title: Rechercher du texte avec Dot Net Regex
linktitle: Rechercher du texte avec Dot Net Regex
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 480
url: /fr/net/programming-with-text/search-text-with-dot-net-regex/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 4 : Créer un objet .NET Regex

 Créer un`.NET Regex` objet pour définir le modèle de recherche :

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Charger le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Remplacer`"SearchTextRegex.pdf"` avec le nom réel de votre fichier PDF.

## Étape 6 : Obtenez une page spécifique

Obtenez la page souhaitée du document :

```csharp
Page page = document.Pages[1];
```

 Remplacer`1` avec le numéro de page souhaité (index de base 1).

## Étape 7 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour rechercher toutes les instances de l'expression régulière d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Étape 8 : Acceptez l'absorbeur pour la page

Acceptez l'absorbeur pour la page :

```csharp
page.Accept(textFragmentAbsorber);
```

## Étape 9 : Récupérer les fragments de texte extraits

Obtenez les fragments de texte extraits en utilisant le`TextFragments` propriété du`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 10 : Parcourez les fragments de texte

Parcourez les fragments de texte récupérés et effectuez les actions souhaitées :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modifiez le code dans la boucle pour effectuer d'autres actions sur chaque fragment de texte si nécessaire.

### Exemple de code source pour rechercher du texte avec Dot Net Regex à l'aide d'Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créez un objet Regex pour trouver tous les mots
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Ouvrir le document
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Obtenir une page particulière
Page page = document.Pages[1];
// Créez un objet TextAbsorber pour rechercher toutes les instances de l'expression régulière d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Acceptez l'absorbeur pour la page
page.Accept(textFragmentAbsorber);
// Obtenez les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parcourez les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, depuis la configuration du projet jusqu'à l'accès aux fragments de texte extraits. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour effectuer des recherches de texte avancées dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher du texte avec Dot Net Regex » ?

R : Le didacticiel « Rechercher du texte avec Dot Net Regex » vise à guider les utilisateurs sur l'utilisation de la bibliothèque Aspose.PDF pour .NET afin de rechercher du texte dans un document PDF à l'aide d'expressions régulières .NET. Le didacticiel fournit des instructions étape par étape et des exemples de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à rechercher du texte à l'aide d'expressions régulières .NET dans un PDF ?

R : Ce didacticiel aide les utilisateurs à comprendre comment exploiter les capacités d'Aspose.PDF for .NET pour rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent rechercher efficacement des modèles de texte correspondant aux expressions régulières spécifiées.

#### Q : Quels prérequis sont requis pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour rechercher et travailler avec des documents PDF.

#### Q : Puis-je utiliser ce didacticiel pour rechercher n'importe quel type de texte spécifique à l'aide d'expressions régulières .NET ?

 R : Oui, ce didacticiel fournit des instructions sur la façon de rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. Vous pouvez personnaliser le`.NET Regex` objet pour définir le modèle de recherche spécifique que vous souhaitez utiliser.

#### Q : Comment spécifier le modèle d'expression régulière .NET à rechercher dans ce didacticiel ?

 R : Pour spécifier le modèle d'expression régulière .NET que vous souhaitez rechercher, créez un`.NET Regex` objet et définissez son modèle en utilisant la syntaxe d'expression régulière appropriée. Remplacer la valeur par défaut`@"[\S]+"` dans le code du didacticiel avec l'expression régulière souhaitée.

#### Q : Comment récupérer les propriétés des fragments de texte extraits ?

 R : Après avoir accepté le`TextFragmentAbsorber` pour une page spécifique du PDF, vous pouvez récupérer les fragments de texte extraits à l'aide du`TextFragments` propriété de l’objet absorbeur. Cela donne accès à une collection de fragments de texte qui correspondent à l'expression régulière .NET spécifiée.

#### Q : Puis-je personnaliser le code pour effectuer des actions supplémentaires sur chaque fragment de texte extrait ?

: Certainement. L'exemple de code du didacticiel comprend une boucle permettant de parcourir les fragments de texte récupérés. Vous pouvez personnaliser le code dans cette boucle pour effectuer des actions supplémentaires sur chaque fragment de texte extrait en fonction des exigences de votre projet.

#### Q : Comment puis-je enregistrer le document PDF modifié après avoir extrait des fragments de texte ?

R : Ce didacticiel se concentre principalement sur la recherche de texte à l'aide d'expressions régulières .NET et sur la récupération de fragments de texte. Si vous avez l'intention d'apporter des modifications au PDF, vous pouvez vous référer à une autre documentation Aspose.PDF pour savoir comment manipuler et enregistrer le document en fonction de vos besoins spécifiques.