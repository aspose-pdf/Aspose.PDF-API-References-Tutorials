---
title: Définir le nom de la police par défaut
linktitle: Définir le nom de la police par défaut
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour définir le nom de police par défaut dans le fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 270
url: /fr/net/document-conversion/set-default-font-name/
---

Dans ce didacticiel, nous allons vous montrer comment définir le nom de police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Parfois, lorsque vous extrayez des images d'un fichier PDF, vous pouvez rencontrer des problèmes de polices manquantes. En spécifiant un nom de police par défaut, vous pouvez vous assurer que le texte extrait s'affichera correctement. Suivez les étapes ci-dessous pour définir le nom de police par défaut dans un fichier PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDF
 La première étape consiste à charger le document PDF dans un`Document` objet. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Code à ajouter
}
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Définir le nom de la police par défaut
 Ensuite, nous définirons le nom de la police par défaut à l'aide de la`DefaultFontName` option de la`RenderingOptions` objet. Utilisez le code suivant :

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Code à ajouter
     }
}
```

 Assurez-vous de remplacer`"Arial"` avec le nom de police souhaité.

## Étape 3 : Extraction d'images
Ensuite, nous allons extraire l'image de la page spécifiée du document PDF. Utilisez le code suivant :

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Assurez-vous de spécifier le bon numéro de page dans`pdfDocument.Pages[1]`.

### Exemple de code source pour définir le nom de police par défaut à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir le nom de police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En spécifiant un nom de police par défaut, vous pouvez vous assurer que le texte extrait s'affichera correctement. Utilisez cette méthode pour résoudre les problèmes de polices manquantes lors de l'extraction d'images à partir de fichiers PDF.