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

Avant de commencer, assurez-vous de définir le bon répertoire pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin vers le répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrir le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe d'Aspose.PDF. Utilisez le`Document` constructeur et passez le chemin vers le document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Étape 3 : Définir les fichiers de sortie

 Définissez les noms de fichiers de sortie pour l'image résultante et l'image binaire. Remplacer`"resultant_out.tif"` et`"37116-bin_out.tif"` avec les noms souhaités pour les fichiers de sortie.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Étape 4 : Créer l’objet Résolution

 Créer un`Resolution` objet pour définir la résolution de l'image TIFF. Dans cet exemple, nous utilisons une résolution de 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Étape 5 : créer l’objet TiffSettings

 Créer un`TiffSettings` objet permettant de spécifier les paramètres du fichier TIFF de sortie. Dans cet exemple, nous utilisons la compression LZW et une profondeur de couleur de 1 bit par pixel (format 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Étape 6 : Créer le périphérique TIFF

 Créez un périphérique TIFF à l'aide de`TiffDevice` objet, spécifiant la résolution et les paramètres TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Étape 7 : Convertissez la page spécifique et enregistrez l'image

 Utilisez le`Process` méthode du périphérique TIFF pour convertir une page spécifique du document PDF et enregistrer l'image dans un fichier TIFF. Spécifiez le chemin de sortie du fichier.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Étape 8 : Binariser l'image à l'aide de l'algorithme Bradley

 Utilisez le`BinarizeBradley`méthode du périphérique TIFF pour binariser l'image à l'aide de l'algorithme Bradley. Cette méthode prend un flux d'entrée de l'image d'origine et un flux de sortie pour l'image binaire. Spécifiez le seuil de binarisation (0,1 dans cet exemple).

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
// Le chemin vers le répertoire des documents.
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
// Convertissez une page particulière et enregistrez l'image dans le flux
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

Félicitations ! Vous avez terminé avec succès la conversion à l'aide de l'algorithme Bradley avec Aspose.PDF pour .NET. Vous pouvez désormais utiliser les images obtenues dans vos projets ou applications.

### FAQ

#### Q : Qu'est-ce que l'algorithme Bradley et quel est son rapport avec Aspose.PDF pour .NET ?

R : L'algorithme Bradley est une technique de traitement d'image utilisée pour améliorer la qualité et la clarté des images. Aspose.PDF pour .NET offre un moyen pratique d'appliquer l'algorithme Bradley aux documents PDF, ce qui permet d'obtenir des images de meilleure qualité.

#### Q : Comment configurer mon environnement pour utiliser l'algorithme Bradley avec Aspose.PDF pour .NET ?

R : Avant de commencer, assurez-vous qu’Aspose.PDF pour .NET est correctement installé et que votre environnement de développement est configuré.

#### Q : Quelle est l’importance de définir le répertoire de documents dans le processus de l’algorithme Bradley ?

R : Il est essentiel de spécifier le répertoire de document correct pour garantir que le document PDF se trouve dans le bon chemin pour le traitement.

#### Q : Comment ouvrir un document PDF à l’aide d’Aspose.PDF pour .NET dans l’algorithme Bradley ?

 A : Utilisez le`Document` classe pour ouvrir le document PDF, qui sert d'entrée pour le processus de l'algorithme Bradley.

#### Q : Quel est le but de la définition des noms de fichiers de sortie pour l'image et l'image binaire dans le processus de l'algorithme Bradley ?

R : La définition des noms de fichiers de sortie vous permet de spécifier où l’image résultante et l’image binaire seront enregistrées après l’application de l’algorithme Bradley.

#### Q : Comment le paramètre de résolution affecte-t-il la qualité de l'image TIFF dans le processus de l'algorithme Bradley ?

R : Le paramètre de résolution détermine le niveau de détail et de clarté de l’image TIFF résultante après l’application de l’algorithme Bradley.

#### Q : Quels paramètres puis-je personnaliser pour l’image TIFF de sortie dans le processus de l’algorithme Bradley ?
R : Vous pouvez personnaliser des paramètres tels que le type de compression et la profondeur de couleur pour obtenir la sortie souhaitée pour l'image TIFF.

#### Q : Comment le périphérique TIFF contribue-t-il au processus de l'algorithme Bradley ?

R : Le périphérique TIFF agit comme un outil de traitement d’images et d’application de l’algorithme Bradley, ce qui permet d’améliorer la qualité d’image.

#### Q : Comment convertir une page spécifique d'un document PDF en une image TIFF dans le processus de l'algorithme Bradley ?

 A : Utilisez le`Process` méthode du périphérique TIFF pour convertir une page spécifique du document PDF en une image TIFF, qui peut ensuite être traitée ultérieurement à l'aide de l'algorithme Bradley.