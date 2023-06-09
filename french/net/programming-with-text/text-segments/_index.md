---
title: Segments de texte
linktitle: Segments de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rechercher des segments de texte spécifiques dans un document PDF à l'aide d'expressions régulières dans Aspose.PDF pour .NET.
type: docs
weight: 540
url: /fr/net/programming-with-text/text-segments/
---

Ce didacticiel explique comment rechercher des segments de texte spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre différents scénarios utilisant des expressions régulières.

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

## Étape 3 : Utiliser TextFragmentAbsorber pour la recherche de texte

 Créer un`TextFragmentAbsorber`objet pour rechercher des segments de texte spécifiques à l'aide d'expressions régulières :

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Étape 4 : Effectuer des recherches de texte avec des expressions régulières

Effectuez des recherches de texte basées sur différents scénarios à l'aide d'expressions régulières. Voici quelques exemples:

- Pour rechercher une correspondance exacte de mot : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Pour rechercher une chaîne en majuscules ou en minuscules : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- Pour rechercher toutes les chaînes dans le document PDF : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Pour rechercher du texte après une chaîne spécifique jusqu'à un saut de ligne : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Pour rechercher du texte après une correspondance d'expression régulière : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Pour rechercher des liens hypertexte/URL dans le document PDF : 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Remplacez les expressions régulières par les modèles de recherche souhaités.

## Étape 5 : Effectuer la recherche et traiter les résultats

 Effectuez la recherche à l'aide du`TextFragmentAbsorber` objecter et traiter les résultats en fonction de vos besoins.

### Exemple de code source pour les segments de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Afin de rechercher la correspondance exacte d'un mot, vous pouvez envisager d'utiliser une expression régulière.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//Afin de rechercher une chaîne en majuscules ou en minuscules, vous pouvez envisager d'utiliser une expression régulière.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// Afin de rechercher toutes les chaînes (analyser toutes les chaînes) dans le document PDF, essayez d'utiliser l'expression régulière suivante.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Trouvez la correspondance de la chaîne de recherche et obtenez n'importe quoi après la chaîne jusqu'au saut de ligne.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Veuillez utiliser l'expression régulière suivante pour trouver le texte suivant la correspondance de regex.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Afin de rechercher un lien hypertexte/URL dans un document PDF, veuillez essayer d'utiliser l'expression régulière suivante.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment rechercher des segments de texte spécifiques dans un document PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel fournit des exemples de différents scénarios de recherche utilisant des expressions régulières. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour rechercher et traiter des segments de texte dans des fichiers PDF.