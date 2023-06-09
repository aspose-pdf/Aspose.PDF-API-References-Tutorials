---
title: Redimensionner les images
linktitle: Redimensionner les images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour redimensionner les images d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 250
url: /fr/net/programming-with-images/resize-images/
---

Dans ce didacticiel, nous vous expliquerons comment redimensionner des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Étape 1 : Chargement du document PDF

Pour commencer, utilisez le code suivant pour charger le document PDF :

```csharp
// Initialiser l'heure
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Assurez-vous de fournir le chemin d'accès correct à votre document PDF.

## Etape 2 : Initialisation des options d'optimisation

Avant de redimensionner les images, nous devons initialiser les options d'optimisation. Utilisez le code suivant :

```csharp
// Initialiser les options d'optimisation
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activez l'option Compresser les images
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Définir la qualité d'image
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Activez l'option Redimensionner les images
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Définir la résolution maximale
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Vous pouvez ajuster les paramètres d'optimisation en fonction de vos besoins.

## Etape 3 : Optimisation du document PDF

Nous allons maintenant optimiser le document PDF en utilisant les options d'optimisation que nous avons définies. Utilisez le code suivant :

```csharp
// Optimisez le document PDF à l'aide des options d'optimisation
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Assurez-vous de fournir le chemin et le nom de fichier souhaités pour le document PDF mis à jour.

### Exemple de code source pour redimensionner les images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Heure d'initialisation
var time = DateTime.Now.Ticks;
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Initialiser les options d'optimisation
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Définir l'option CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Définir l'option Qualité d'image
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Définir l'option Redimensionner l'image
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Définir l'option MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez redimensionné avec succès des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour modifier la taille des images dans les fichiers PDF.