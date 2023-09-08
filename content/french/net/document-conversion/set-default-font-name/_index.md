---
title: Définir le nom de la police par défaut
linktitle: Définir le nom de la police par défaut
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour définir le nom de police par défaut dans le fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 270
url: /fr/net/document-conversion/set-default-font-name/
---
Dans ce didacticiel, nous allons vous montrer comment définir le nom de police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Parfois, lorsque vous extrayez des images d'un fichier PDF, vous pouvez rencontrer des problèmes de police manquante. En spécifiant un nom de police par défaut, vous pouvez vous assurer que le texte extrait s'affichera correctement. Suivez les étapes ci-dessous pour définir le nom de police par défaut dans un fichier PDF.

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

## Étape 2 : Définir le nom de la police par défaut
 Ensuite, nous définirons le nom de la police par défaut en utilisant le`DefaultFontName` option du`RenderingOptions` objet. Utilisez le code suivant :

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

## Étape 3 : Extraction d’images
Ensuite, nous extrairons l'image de la page spécifiée du document PDF. Utilisez le code suivant :

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Assurez-vous de spécifier le numéro de page correct dans`pdfDocument.Pages[1]`.

### Exemple de code source pour définir le nom de police par défaut à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
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
Dans ce didacticiel, nous avons appris à définir le nom de police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En spécifiant un nom de police par défaut, vous pouvez vous assurer que le texte extrait s'affichera correctement. Utilisez cette méthode pour résoudre les problèmes de police manquante lors de l'extraction d'images à partir de fichiers PDF.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre diverses fonctionnalités, notamment la définition du nom de police par défaut dans un fichier PDF.

#### Q : Pourquoi devrais-je définir le nom de police par défaut dans un fichier PDF ?

R : La définition du nom de police par défaut est utile lors de l'extraction de texte d'un document PDF. Si le PDF contient du texte avec des polices qui ne sont pas disponibles sur la machine d'extraction, la spécification d'un nom de police par défaut garantit un affichage correct du texte.

#### Q : Comment puis-je charger un document PDF et définir le nom de la police par défaut à l'aide d'Aspose.PDF pour .NET ?

 R : Pour charger un document PDF et définir le nom de la police par défaut, vous pouvez utiliser le`Document`classe pour charger le fichier PDF et le`RenderingOptions.DefaultFontName` propriété pour spécifier le nom de police par défaut souhaité.

#### Q : Puis-je choisir n’importe quelle police comme nom de police par défaut ?

R : Oui, vous pouvez choisir n’importe quelle police disponible sur la machine d’extraction comme nom de police par défaut. Utilisez une police qui correspond étroitement aux polices manquantes dans le PDF d'origine pour garantir un rendu précis du texte.

#### Q : La définition du nom de police par défaut constitue-t-elle une modification permanente du fichier PDF ?

R : Non, la définition du nom de police par défaut à l'aide d'Aspose.PDF pour .NET est une modification temporaire effectuée lors de l'extraction de texte. Il ne modifie pas le fichier PDF original.