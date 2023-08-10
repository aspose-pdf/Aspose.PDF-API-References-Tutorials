---
title: Rechercher du texte avec Dot Net Regex
linktitle: Rechercher du texte avec Dot Net Regex
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 480
url: /fr/net/programming-with-text/search-text-with-dot-net-regex/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 4 : Créer un objet Regex .NET

 Créer un`.NET Regex` objet pour définir le modèle de recherche :

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Chargez le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Remplacer`"SearchTextRegex.pdf"` avec le nom réel de votre fichier PDF.

## Étape 6 : Obtenir une page spécifique

Obtenez la page souhaitée du document :

```csharp
Page page = document.Pages[1];
```

 Remplacer`1` avec le numéro de page souhaité (index de base 1).

## Étape 7 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber`objet pour trouver toutes les instances de l'expression régulière d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Étape 8 : Acceptez l'absorbeur pour la page

Acceptez l'absorbeur pour la page :

```csharp
page.Accept(textFragmentAbsorber);
```

## Étape 9 : Récupérer les fragments de texte extraits

Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 10 : bouclez sur les fragments de texte

Parcourez les fragments de texte récupérés et effectuez les actions souhaitées :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modifiez le code dans la boucle pour effectuer d'autres actions sur chaque fragment de texte si nécessaire.

### Exemple de code source pour Search Text With Dot Net Regex en utilisant Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un objet Regex pour trouver tous les mots
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Ouvrir le document
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Obtenir une page particulière
Page page = document.Pages[1];
// Créer un objet TextAbsorber pour trouver toutes les instances de l'expression régulière d'entrée
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

Toutes nos félicitations! Vous avez appris avec succès à rechercher du texte à l'aide d'expressions régulières .NET dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la configuration du projet à l'accès aux fragments de texte extraits. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour effectuer des recherches de texte avancées dans des fichiers PDF.