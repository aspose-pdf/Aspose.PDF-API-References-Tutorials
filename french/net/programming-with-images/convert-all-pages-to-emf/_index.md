---
title: Convertir toutes les pages en EMF
linktitle: Convertir toutes les pages en EMF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement toutes les pages d'un document PDF en fichiers EMF avec Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-images/convert-all-pages-to-emf/
---

Ce guide vous expliquera étape par étape comment convertir toutes les pages d'un document PDF en fichiers EMF (Enhanced Metafile) à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## Étape 3 : Convertir chaque page en EMF

 Dans cette étape, nous allons parcourir chaque page du document PDF et les convertir en fichiers EMF individuels. Nous utiliserons un`for`boucle pour parcourir toutes les pages.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Créer un flux pour enregistrer l'image EMF
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // Créer un objet Résolution
         Resolution resolution = new Resolution(300);
        
         // Créer un périphérique EMF avec les attributs spécifiés
         // Largeur, Hauteur, Résolution
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // Convertir une page spécifique et enregistrer l'image dans le flux
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Fermer le flux
         imageStream.Close();
     }
}
```

### Exemple de code source pour convertir toutes les pages en EMF à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// Créer un objet de résolution
		Resolution resolution = new Resolution(300);
		// Créer un périphérique PNG avec des attributs spécifiés
		// Largeur, Hauteur, Résolution
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// Convertir une page particulière et enregistrer l'image à diffuser
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Fermer le flux
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## Conclusion

Félicitation ! Vous avez réussi à convertir toutes les pages d'un document PDF en fichiers EMF à l'aide d'Aspose.PDF pour .NET. Les fichiers EMF individuels sont enregistrés dans le répertoire spécifié. Vous pouvez maintenant utiliser ces fichiers EMF dans vos projets ou applications.