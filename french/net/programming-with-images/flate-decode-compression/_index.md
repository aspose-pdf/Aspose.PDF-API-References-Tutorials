---
title: Compression de décodage plat
linktitle: Compression de décodage plat
second_title: Référence de l'API Aspose.PDF pour .NET
description: Compressez efficacement les images d'un PDF à l'aide de la compression Flate Decode avec Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-images/flate-decode-compression/
---

Ce guide vous expliquera étape par étape comment compresser des images à l'aide de la compression Flate Decode dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Assurez-vous de définir le répertoire de documents correct. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Étape 3 : Initialiser les options d'optimisation

 Dans cette étape, nous allons initialiser les options d'optimisation pour la compression d'image. Créer une instance de`OptimizationOptions` et définissez les options appropriées. Dans cet exemple, nous utilisons la compression Flate Decode pour optimiser les images.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Étape 4 : Optimisez le document PDF

 Dans cette étape, nous allons optimiser le document PDF en utilisant les options d'optimisation définies précédemment. Appeler le`OptimizeResources` méthode de la`doc` objet et passez les options d'optimisation.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Étape 5 : Enregistrer le document PDF mis à jour

 Enregistrez le document PDF mis à jour à l'aide de`Save` méthode de la`doc` objet. Spécifiez le chemin de sortie du fichier PDF.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Exemple de code source pour Flate Decode Compression à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document doc = new Document(dataDir + "AddImage.pdf");
// Initialiser les options d'optimisation
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//Pour optimiser l'image à l'aide de FlateDecode Compression, définissez les options d'optimisation sur Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Définir les options d'optimisation
doc.OptimizeResources(optimizationOptions);
// Enregistrer le document
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusion

Félicitation ! Vous avez réussi à compresser des images dans un PDF en utilisant la compression Flate Decode avec Aspose.PDF pour .NET. Le fichier PDF optimisé est enregistré dans le répertoire spécifié. Vous pouvez maintenant utiliser ce fichier PDF pour des besoins de stockage ou de partage plus efficaces.