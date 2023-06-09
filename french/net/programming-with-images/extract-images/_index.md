---
title: Extraire des images
linktitle: Extraire des images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Extrayez facilement des images d'un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-images/extract-images/
---

Ce guide vous expliquera étape par étape comment extraire des images d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Étape 3 : Extraire une image spécifique

 Dans cette étape, nous allons extraire une image spécifique d'une page particulière. Utilisez le`Images` recueil de la page`s `L'objet Resources` pour accéder à l'image souhaitée. Dans l'exemple ci-dessous, nous extrayons l'image avec l'index 1 de la première page.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Étape 4 : Enregistrer l'image extraite

 Enregistrez l'image extraite dans un fichier à l'aide de la`Save` méthode de la`xImage`objet. Spécifiez le chemin de sortie et le format d'image (dans cet exemple, nous utilisons le format JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Étape 5 : Enregistrez le fichier PDF mis à jour

 Enregistrez le fichier PDF mis à jour à l'aide de`Save` méthode de la`pdfDocument` objet. Spécifiez le chemin de sortie du fichier PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour extraire des images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extraire une image particulière
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Enregistrer l'image de sortie
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Enregistrer le fichier PDF mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitation ! Vous avez réussi à extraire des images d'un PDF à l'aide d'Aspose.PDF pour .NET. L'image extraite est enregistrée dans le répertoire spécifié et le fichier PDF mis à jour est également enregistré. Vous pouvez maintenant utiliser ces fichiers pour vos besoins spécifiques.