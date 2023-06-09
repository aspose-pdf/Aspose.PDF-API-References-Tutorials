---
title: Algorithme de Bradley
linktitle: Algorithme de Bradley
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez un document PDF à l'aide de l'algorithme Bradley avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-images/bradley-algorithm/
---

Ce guide étape par étape explique comment utiliser l'algorithme Bradley avec Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Étape 3 : Définir les fichiers de sortie

 Définissez les noms de fichier de sortie pour l'image résultante et l'image binaire. Remplacer`"resultant_out.tif"` et`"37116-bin_out.tif"` avec les noms souhaités pour les fichiers de sortie.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Étape 4 : créer l'objet de résolution

 Créer un`Resolution` objet pour définir la résolution de l'image TIFF. Dans cet exemple, nous utilisons une résolution de 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Étape 5 : Créer l'objet TiffSettings

 Créer un`TiffSettings` objet pour spécifier les paramètres du fichier TIFF de sortie. Dans cet exemple, nous utilisons la compression LZW et une profondeur de couleur de 1 bit par pixel (format 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Étape 6 : Créer le périphérique TIFF

 Créez un périphérique TIFF à l'aide de`TiffDevice` objet, en spécifiant la résolution et les paramètres TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Étape 7 : Convertissez la page spécifique et enregistrez l'image

 Utilisez le`Process` méthode du périphérique TIFF pour convertir une page spécifique du document PDF et enregistrer l'image dans un fichier TIFF. Spécifiez le chemin de sortie du fichier.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Étape 8 : Binariser l'image à l'aide de l'algorithme de Bradley

 Utilisez le`BinarizeBradley`méthode du dispositif TIFF pour binariser l'image à l'aide de l'algorithme de Bradley. Cette méthode prend un flux d'entrée de l'image originale et un flux de sortie pour l'image binaire. Spécifiez le seuil de binarisation (0,1 dans cet exemple).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Exemple de code source pour l'algorithme Bradley utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Créer un objet de résolution
Resolution resolution = new Resolution(300);
// Créer un objet TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Créer un périphérique TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Convertir une page particulière et enregistrer l'image à diffuser
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusion

Félicitation ! Vous avez terminé avec succès la conversion à l'aide de l'algorithme Bradley avec Aspose.PDF pour .NET. Vous pouvez maintenant utiliser les images résultantes dans vos projets ou applications.