---
title: Réduire les images
linktitle: Réduire les images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour réduire la taille des images dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 280
url: /fr/net/programming-with-images/shrink-images/
---

Dans ce didacticiel, nous vous expliquerons comment réduire la taille des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Étape 1 : Chargement du document PDF

Pour commencer, utilisez le code suivant pour charger le document PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Assurez-vous de fournir le chemin d'accès correct à votre document PDF.

## Etape 2 : Initialisation des options d'optimisation

Ensuite, nous allons initialiser les options d'optimisation pour réduire la taille des images. Utilisez le code suivant :

```csharp
// Initialiser les options d'optimisation
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activez l'option Compresser les images
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Définir la qualité d'image
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Vous pouvez ajuster les paramètres d'optimisation en fonction de vos besoins.

## Etape 3 : Optimisation du document PDF

Nous allons maintenant optimiser le document PDF en réduisant la taille des images. Utilisez le code suivant :

```csharp
// Optimisez le document PDF à l'aide des options d'optimisation
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Assurez-vous de fournir le chemin et le nom de fichier souhaités pour le document PDF mis à jour.

### Exemple de code source pour Shrink Images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initialiser les options d'optimisation
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Définir l'option CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Définir l'option Qualité d'image
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez réussi à réduire la taille des images dans un document PDF en utilisant Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour optimiser la taille des images dans les fichiers PDF.