---
title: Toutes les pages au format TIFF
linktitle: Toutes les pages au format TIFF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez toutes les pages d'un document PDF en fichier TIFF avec Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-images/all-pages-to-tiff/
---

Ce guide vous expliquera étape par étape comment convertir toutes les pages d'un document PDF en un fichier TIFF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

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

## Étape 3 : Créer l'objet de résolution

 Créer un`Resolution` objet pour définir la résolution de l'image TIFF. Dans cet exemple, nous utilisons une résolution de 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Étape 4 : Créer l'objet TiffSettings

 Créer un`TiffSettings` objet pour spécifier les paramètres du fichier TIFF de sortie. Dans cet exemple, nous désactivons la compression, utilisons une profondeur de couleur par défaut et définissons la forme en mode paysage.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## Étape 5 : créer le périphérique TIFF

 Créez un périphérique TIFF à l'aide de`TiffDevice` objet, en spécifiant la résolution et les paramètres TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Étape 6 : Convertissez toutes les pages et enregistrez l'image

 Utilisez le`Process` méthode du périphérique TIFF pour convertir toutes les pages du document PDF et enregistrer l'image dans un fichier TIFF. Spécifiez le chemin de sortie du fichier.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### Exemple de code source pour toutes les pages en TIFF à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// Créer un objet de résolution
Resolution resolution = new Resolution(300);
// Créer un objet TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// Créer un périphérique TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Convertir une page particulière et enregistrer l'image à diffuser
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## Conclusion

Félicitation ! Vous avez converti avec succès toutes les pages d'un document PDF en un fichier TIFF à l'aide de Aspose.PDF pour .NET. Vous pouvez maintenant utiliser le fichier TIFF généré dans vos projets ou applications.