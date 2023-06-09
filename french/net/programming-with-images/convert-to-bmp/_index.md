---
title: Convertir en BMP
linktitle: Convertir en BMP
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement des PDF en images BMP individuelles avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-images/convert-to-bmp/
---

Ce guide vous expliquera étape par étape comment convertir un fichier PDF en images BMP individuelles à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Étape 3 : Convertir chaque page en BMP

 Dans cette étape, nous allons parcourir chaque page du document PDF et les convertir en images BMP individuelles. Nous utiliserons un`for`boucle pour parcourir toutes les pages.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Créer un flux pour enregistrer l'image BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Créer un objet Résolution
         Resolution resolution = new Resolution(300);
        
         // Créer un périphérique BMP avec les attributs spécifiés
         //Largeur, Hauteur, Résolution, Taille de la page
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Convertir une page spécifique et enregistrer l'image dans le flux
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Fermer le flux
         imageStream.Close();
     }
}
```

### Exemple de code source pour convertir en BMP en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Créer un objet de résolution
		Resolution resolution = new Resolution(300);
		// Créer un périphérique BMP avec des attributs spécifiés
		// Largeur, Hauteur, Résolution, Taille de page
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Convertir une page particulière et enregistrer l'image à diffuser
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Fermer le flux
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Conclusion

Félicitation ! Vous avez réussi à convertir un fichier PDF en images BMP individuelles à l'aide d'Aspose.PDF pour .NET. Les images BMP sont enregistrées dans le répertoire spécifié. Vous pouvez maintenant utiliser ces images dans vos projets ou applications.