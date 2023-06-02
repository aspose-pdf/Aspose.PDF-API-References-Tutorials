---
title: Optimiser la taille du fichier
linktitle: Optimiser la taille du fichier
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à optimiser la taille de fichier de vos documents PDF avec Aspose.PDF pour .NET à l'aide de ce guide étape par étape.
type: docs
weight: 250
url: /fr/net/programming-with-document/optimizefilesize/
---
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, modifier et manipuler des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités les plus utiles de cette bibliothèque est la possibilité d'optimiser la taille de fichier d'un document PDF. Dans cet article, nous fournirons un guide étape par étape pour optimiser la taille de fichier d'un document PDF à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : Chargez le document PDF

 La première étape de l'optimisation de la taille de fichier d'un document PDF consiste à charger le document dans votre application. Vous pouvez le faire en utilisant le`Document`classe fournie par la bibliothèque Aspose.PDF pour .NET. Voici un exemple de chargement d'un document PDF :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin d'accès au répertoire contenant votre document PDF.

## Étape 2 : Définir les options d'optimisation

 Une fois que vous avez chargé le document PDF, vous pouvez définir les options d'optimisation pour spécifier les parties du document que vous souhaitez optimiser. Le`OptimizationOptions` La classe fournie par la bibliothèque Aspose.PDF pour .NET vous permet de spécifier une variété d'options pour optimiser la taille de fichier du document PDF. Voici un exemple de définition de certaines options d'optimisation :

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

Dans cet exemple, nous définissons les options suivantes :
- `LinkDuplcateStreams`: Cette option active la suppression des flux en double dans le document PDF, ce qui peut aider à réduire la taille du fichier.
- `RemoveUnusedObjects`: Cette option permet de supprimer tous les objets inutilisés dans le document PDF, ce qui peut également aider à réduire la taille du fichier.
- `RemoveUnusedStreams`Cette option permet de supprimer tous les flux inutilisés dans le document PDF, ce qui peut réduire davantage la taille du fichier.
- `CompressImages`: Cette option active la compression des images dans le document PDF, ce qui peut réduire considérablement la taille du fichier.
- `ImageQuality`: Cette option définit la qualité des images compressées. Un paramètre de qualité inférieur entraînera une taille de fichier plus petite, mais peut également entraîner une image de qualité inférieure.

## Étape 4 : Optimisez le document PDF

 Maintenant que vous avez défini les options d'optimisation, vous pouvez optimiser le document PDF à l'aide de la`OptimizeResources` méthode proposée par le`Document` classe. Voici un exemple d'optimisation du document PDF :

```csharp
// Optimisez la taille du fichier en supprimant les objets inutilisés
pdfDocument.OptimizeResources(optimizationOptions);
```

## Étape 5 : Enregistrer le document PDF optimisé

Une fois que vous avez optimisé le document PDF, vous pouvez enregistrer la version optimisée dans un nouveau fichier. Voici un exemple d'enregistrement du document PDF optimisé :

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

### Exemple de code source pour optimiser la taille du fichier à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Optimisez la taille du fichier en supprimant les objets inutilisés
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```
