---
title: Obtenir une annotation particulière
linktitle: Obtenir une annotation particulière
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir une annotation particulière dans un document PDF avec ce guide étape par étape.
type: docs
weight: 80
url: /fr/net/annotations/getparticularannotation/
---
Si vous travaillez avec des fichiers PDF dans .NET, vous aurez peut-être besoin d'obtenir une annotation particulière à partir d'un document PDF. Dans ce guide, nous allons vous montrer comment utiliser Aspose.PDF pour .NET pour obtenir une annotation particulière à partir d'un document PDF à l'aide de C#.

Suivez ces étapes simples pour obtenir une annotation particulière à partir d'un document PDF :

## Étape 1 : Obtenir une annotation particulière à partir d'un document PDF

Tout d'abord, assurez-vous que la bibliothèque Aspose.PDF pour .NET est installée et référencée dans votre projet.

Ensuite, créez une nouvelle instance de la classe Document et chargez votre document PDF en utilisant le chemin d'accès au répertoire du document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Étape 2 : Vous pouvez obtenir une annotation particulière à l'aide du code suivant :

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Ce code récupère la deuxième annotation sur la deuxième page du document PDF.

## Étape 3 : Enfin, vous pouvez obtenir les propriétés de l'annotation à l'aide du code suivant :

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Ce code affiche le titre, le sujet et le contenu de l'annotation dans la console.


### Exemple de code source pour obtenir une annotation particulière à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

// Obtenir une annotation particulière
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

// Obtenir les propriétés d'annotation
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

