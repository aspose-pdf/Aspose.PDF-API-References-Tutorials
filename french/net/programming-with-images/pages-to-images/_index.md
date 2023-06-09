---
title: Pages vers images
linktitle: Pages vers images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement les pages d'un document PDF en images avec Aspose.PDF pour .NET.
type: docs
weight: 200
url: /fr/net/programming-with-images/pages-to-images/
---

Dans ce didacticiel, nous vous guiderons pas à pas pour convertir les pages d'un document PDF en images individuelles à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni vous montre comment ouvrir un document PDF, créer des images à partir de chaque page et les enregistrer. Nous expliquerons chaque étape en détail pour vous aider à comprendre le processus en profondeur.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Connaissance de base du langage de programmation C#.
- La bibliothèque Aspose.PDF pour .NET installée dans votre projet.
- Un document PDF que vous souhaitez convertir en images.

## Étape 1 : configuration du projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF dans votre projet.

## Étape 2 : Importez les espaces de noms nécessaires
Au début de votre fichier C#, importez les espaces de noms requis pour accéder aux classes et aux méthodes d'Aspose.PDF. Voici un exemple :
```csharp
using System;
using Aspose.Pdf;
using System.IO;
```

## Étape 3 : Initialisation des variables et des chemins
Avant d'effectuer la conversion, nous devons configurer les variables et les chemins nécessaires.
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Conversion de pages en images
Pour convertir les pages d'un document PDF en images, procédez comme suit :
1.  Ouvrez le document PDF à l'aide de la`Document` classe.
```csharp
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
```
2.  Parcourez chaque page du document à l'aide d'un`for` boucle.
```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
//Code pour convertir chaque page en image
}
```
3. Dans la boucle, créez un flux de fichiers pour chaque image à enregistrer.
```csharp
using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
{
// Code pour convertir la page en image
}
```
4.  À l'intérieur de`using` bloquer, créer un`Resolution` objet pour définir la résolution de l'image.
```csharp
Resolution resolution = new Resolution(300);
```
5.  Créer un`JpegDevice` objet en utilisant la résolution et la qualité spécifiées.
```csharp
JpegDevice jpegDevice = new JpegDevice(resolution, 100);
```
6.  Utilisez le`Process` méthode de la`jpegDevice` objet pour convertir une page spécifique en image et enregistrer l'image dans le flux.
```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```
7. Fermez le flux d'images.
```csharp
imageStream.Close();
```
8. Répétez ces étapes pour chaque page du document.
9. Afficher un message de réussite à la fin du processus.
```csharp
Console.WriteLine("PDF pages converted to individual images successfully!");
```

### Exemple de code source pour Pages To Images utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
	{
		// Créer un périphérique JPEG avec des attributs spécifiés
		// Largeur, Hauteur, Résolution, Qualité
		// Qualité [0-100], 100 est maximum
		// Créer un objet de résolution
		Resolution resolution = new Resolution(300);
		// JpegDevice jpegDevice = nouveau JpegDevice(500, 700, résolution, 100);
		JpegDevice jpegDevice = new JpegDevice(resolution, 100);
		// Convertir une page particulière et enregistrer l'image à diffuser
		jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Fermer le flux
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```

## Conclusion
En suivant ce guide étape par étape, vous avez appris à convertir les pages d'un document PDF en images individuelles à l'aide de la bibliothèque Aspose.PDF pour .NET. Ce processus implique la configuration du projet, l'importation des espaces de noms nécessaires, l'initialisation des variables et des chemins et la conversion des pages en images. Vous pouvez maintenant intégrer ce code dans vos propres projets et le modifier selon vos besoins spécifiques.