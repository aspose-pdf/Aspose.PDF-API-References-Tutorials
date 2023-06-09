---
title: Page vers EMF
linktitle: Page vers EMF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir une page PDF au format EMF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-images/page-to-emf/
---

Dans ce tutoriel, nous verrons comment convertir une page PDF au format EMF (Enhanced Metafile) en utilisant Aspose.PDF pour .NET. EMF est un format d'image vectoriel qui prend en charge des graphiques de haute qualité et est largement utilisé dans diverses applications. En suivant ce guide étape par étape, vous pourrez convertir une page spécifique d'un document PDF en un fichier image EMF.

## Exigences
Avant de poursuivre ce didacticiel, assurez-vous que vous disposez des prérequis suivants :
- Connaissance de base du langage de programmation C#
- Bibliothèque Aspose.PDF pour .NET installée
- Visual Studio ou tout autre environnement de développement C# configuré

## Étape 1 : Configuration de l'environnement
Pour commencer, procédez comme suit pour configurer l'environnement :
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.

## Étape 2 : Importation des bibliothèques requises
Commencez par importer les bibliothèques nécessaires pour travailler avec Aspose.PDF et FileStream :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
```

## Étape 3 : Définition du répertoire de documents
Définissez le chemin du répertoire où se trouve votre document PDF. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin réel :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 4 : Ouverture du document PDF
Ouvrez le document PDF en utilisant le chemin spécifié :

```csharp
Document pdfDocument = new Document(dataDir + "PageToEMF.pdf");
```

## Étape 5 : Création du périphérique EMF
Créez un appareil EMF avec la largeur, la hauteur et la résolution souhaitées :

```csharp
Resolution resolution = new Resolution(300);
EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
```

## Étape 6 : Conversion d'une page en EMF
Spécifiez la page que vous souhaitez convertir en EMF. Dans cet exemple, nous convertissons la première page (index 1) :

```csharp
emfDevice.Process(pdfDocument.Pages[1], imageStream);
```

## Étape 7 : Enregistrement de l'image EMF
Enregistrez l'image EMF dans un flux de fichiers. Assurez-vous de fournir le chemin où vous souhaitez enregistrer l'image :

```csharp
using (FileStream imageStream = new FileStream(dataDir + "image_out.emf", FileMode.Create))
{
     emfDevice.Process(pdfDocument.Pages[1], imageStream);
     imageStream.Close();
}
```

## Étape 8 : Fermer le flux
Fermez le flux de fichiers après le processus de conversion :

```csharp
imageStream.Close();
```

### Exemple de code source pour Page To EMF utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageToEMF.pdf");
using (FileStream imageStream = new FileStream(dataDir + "image_out.emf", FileMode.Create))
{
	// Créer un objet de résolution
	Resolution resolution = new Resolution(300);
	// Créer un périphérique EMF avec des attributs spécifiés
	// Largeur, Hauteur, Résolution
	EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
	// Convertir une page particulière et enregistrer l'image à diffuser
	emfDevice.Process(pdfDocument.Pages[1], imageStream);
	// Fermer le flux
	imageStream.Close();
}
System.Console.WriteLine("PDF page is converted to EMF successfully!");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment convertir une page PDF au format EMF en utilisant Aspose.PDF pour .NET. Ce guide étape par étape a couvert le processus depuis la configuration de l'environnement jusqu'au code de conversion réel. Vous pouvez maintenant implémenter ce code dans vos propres projets pour automatiser la conversion des pages PDF en images EMF.