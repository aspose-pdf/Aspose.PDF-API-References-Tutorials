---
title: Créer des images miniatures
linktitle: Créer des images miniatures
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des vignettes d'images à partir de fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-images/create-thumbnail-images/
---

Ce guide vous expliquera étape par étape comment créer des vignettes d'images à partir de fichiers PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin du répertoire contenant vos fichiers PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Obtenir les noms de tous les fichiers PDF dans un répertoire

 Dans cette étape, nous allons récupérer les noms de tous les fichiers PDF présents dans le répertoire spécifié à l'aide de C#`Directory`classe. Les fichiers seront stockés dans un tableau de chaînes.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Étape 3 : Parcourir tous les fichiers PDF et leurs pages

 Dans cette étape, nous allons parcourir tous les fichiers PDF et leurs pages pour créer des vignettes d'images. Nous utiliserons un`for` loop pour parcourir tous les fichiers.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Ouvrir le document PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Parcourir toutes les pages du document
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Créer un flux pour enregistrer l'image miniature
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Créer un objet Résolution
             Resolution resolution = new Resolution(300);
            
             // Créer un périphérique JPEG avec les attributs spécifiés
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Convertir une page spécifique et enregistrer l'image dans le flux
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Fermer le flux
             imageStream.Close();
         }
     }
}
```

### Exemple de code source pour créer des images miniatures à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Récupérer les noms de tous les fichiers PDF dans un répertoire particulier
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Itérer à travers toutes les entrées de fichiers dans le tableau
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Ouvrir le document
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Créer un objet de résolution
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = nouveau JpegDevice(500, 700, résolution, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Convertir une page particulière et enregistrer l'image à diffuser
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Fermer le flux
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusion

Félicitation ! Vous avez créé avec succès des vignettes d'images à partir de fichiers PDF à l'aide d'Aspose.PDF pour .NET. Les vignettes des images sont enregistrées dans le répertoire spécifié. Vous pouvez maintenant utiliser ces vignettes pour afficher un aperçu visuel de vos fichiers PDF.