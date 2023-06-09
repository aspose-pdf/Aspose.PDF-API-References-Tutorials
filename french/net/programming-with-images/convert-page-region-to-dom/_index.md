---
title: Convertir la région de la page en DOM
linktitle: Convertir la région de la page en DOM
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement une région spécifique d'une page PDF en un modèle d'objet de document (DOM) avec Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-images/convert-page-region-to-dom/
---

Ce guide vous expliquera étape par étape comment convertir une région spécifique d'une page en un modèle d'objet de document (DOM) à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Étape 3 : Obtenir le rectangle de la région de la page

 Dans cette étape, nous définirons un rectangle représentant la région spécifique de la page que nous voulons convertir en DOM. Utilisez le`Aspose.Pdf.Rectangle` class pour définir les coordonnées du rectangle.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Étape 4 : Définir la zone de recadrage de la page

 Utilisez le`CropBox` propriété de la`Page` objet pour définir la zone de recadrage de la page sur le rectangle de région souhaité.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Étape 5 : Enregistrez le document PDF recadré dans un flux

 Dans cette étape, nous allons enregistrer le document PDF recadré dans un flux à l'aide de la`MemoryStream` classe.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Étape 6 : Ouvrez le document PDF recadré et convertissez-le en image

 Ouvrez le document PDF recadré à l'aide de la`Document` classe et convertissez-la en image. Nous utiliserons une résolution de 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Étape 7 : convertir la page spécifique en image

 Convertissez la page spécifique en image à l'aide de la`Process` méthode de la`pngDevice` objet. Spécifiez le chemin de sortie de l'image.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Exemple de code source pour Convertir la région de la page en DOM à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document( dataDir + "AddImage.pdf");
// Obtenir le rectangle d'une région de page particulière
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Définissez la valeur CropBox selon le rectangle de la région de page souhaitée
document.Pages[1].CropBox = pageRect;
// Enregistrer le document recadré dans le flux
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Ouvrez le document PDF recadré et convertissez-le en image
document = new Document(ms);
// Créer un objet de résolution
Resolution resolution = new Resolution(300);
// Créer un périphérique PNG avec des attributs spécifiés
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Convertir une page particulière et enregistrer l'image à diffuser
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitation ! Vous avez réussi à convertir une région spécifique d'une page en un modèle d'objet de document (DOM) à l'aide d'Aspose.PDF pour .NET. L'image résultante est enregistrée dans le répertoire spécifié. Vous pouvez maintenant utiliser cette image dans vos projets ou applications.