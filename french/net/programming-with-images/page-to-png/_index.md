---
title: Page vers PNG
linktitle: Page vers PNG
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir une page au format PNG en utilisant Aspose.PDF pour .NET.
type: docs
weight: 220
url: /fr/net/programming-with-images/page-to-png/
---

Dans ce didacticiel, nous vous expliquerons comment convertir une page au format PNG à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Étape 1 : Chargement du document PDF

Pour commencer, utilisez le code suivant pour charger le document PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Assurez-vous de fournir le chemin d'accès correct à votre document PDF.

## Étape 2 : Convertir la page en PNG

Ensuite, nous allons convertir une page spécifique du document PDF au format PNG. Utilisez le code suivant :

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Créer un objet Résolution
Resolution resolution = new Resolution(300);
// Créer un périphérique PNG avec les attributs spécifiés (largeur, hauteur, résolution)
PngDevice pngDevice = new PngDevice(resolution);
// Convertir une page spécifique et enregistrer l'image dans le flux
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Fermer le flux
imageStream.Close();
}
```

Assurez-vous de fournir le chemin et le nom de fichier souhaités pour l'image PNG de sortie.

### Exemple de code source pour Page To PNG en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Créer un objet de résolution
	Resolution resolution = new Resolution(300);
	// Créer un périphérique PNG avec des attributs spécifiés (largeur, hauteur, résolution)
	PngDevice pngDevice = new PngDevice(resolution);
	// Convertir une page particulière et enregistrer l'image à diffuser
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Fermer le flux
	imageStream.Close();
}
```

## Conclusion

Félicitation ! Vous avez converti avec succès une page au format PNG en utilisant Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour extraire des pages spécifiques de fichiers PDF et les enregistrer en tant qu'images PNG.