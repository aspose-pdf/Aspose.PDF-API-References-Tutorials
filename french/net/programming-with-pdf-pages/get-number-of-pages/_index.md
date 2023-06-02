---
title: Obtenir le nombre de pages
linktitle: Obtenir le nombre de pages
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour obtenir le nombre de pages d'un PDF en utilisant Aspose.PDF pour .NET. Simple à mettre en oeuvre, idéal pour vos projets.
type: docs
weight: 70
url: /fr/net/programming-with-pdf-pages/get-number-of-pages/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus permettant d'obtenir le nombre de pages d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment obtenir le nombre de pages d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement de votre fichier PDF pour lequel vous souhaitez obtenir le nombre de pages. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous pouvez ouvrir le fichier PDF en utilisant le`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct au fichier PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
```

## Étape 3 : Obtenir le nombre de pages
 Vous pouvez maintenant obtenir le nombre de pages du document à l'aide de la`Count`propriété du document`s `Collection de pages. Cela vous donnera le nombre total de pages dans le fichier PDF.

```csharp
System.Console.WriteLine("Number of pages: {0}", pdfDocument.Pages.Count);
```

### Exemple de code source pour obtenir le nombre de pages à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
// Obtenir le nombre de pages
System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);

```

## Conclusion
Dans ce didacticiel, nous avons appris à obtenir le nombre de pages d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez facilement implémenter cette fonctionnalité dans vos propres projets. N'hésitez pas à explorer davantage la documentation Aspose.PDF pour découvrir d'autres fonctionnalités utiles pour travailler avec des fichiers PDF.
