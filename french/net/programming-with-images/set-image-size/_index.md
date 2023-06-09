---
title: Définir la taille de l'image
linktitle: Définir la taille de l'image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour définir la taille d'une image dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 270
url: /fr/net/programming-with-images/set-image-size/
---

Dans ce didacticiel, nous vous expliquerons comment définir la taille d'une image dans un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Etape 1 : Création du document PDF

Pour commencer, utilisez le code suivant pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instancier un objet Document
Document doc = new Document();

// Ajouter une page à la collection de pages du fichier PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 2 : Image ajoutée

Ensuite, nous ajouterons une image à la page du document PDF. Utilisez le code suivant :

```csharp
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Définir la largeur et la hauteur de l'image en points
img. FixWidth = 100;
img. FixHeight = 100;

// Définir le type d'image sur inconnu (Inconnu)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Chemin d'accès au fichier source de l'image
img.File = dataDir + "aspose-logo.jpg";

// Ajouter l'image à la collection de paragraphes de la page
page.Paragraphs.Add(img);
```

Assurez-vous de fournir le chemin d'accès correct au fichier source de l'image.

## Étape 3 : Définir les propriétés de la page

Enfin, nous définirons les propriétés de la page, notamment sa largeur et sa hauteur. Utilisez le code suivant :

```csharp
// Définir les propriétés de la page
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Exemple de code source pour définir la taille de l'image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
//ajouter une page à la collection de pages du fichier PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Définir la largeur et la hauteur de l'image en points
img.FixWidth = 100;
img.FixHeight = 100;
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Chemin du fichier source
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Définir les propriétés de la page
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// enregistrer le fichier PDF résultant
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez défini avec succès la taille d'une image dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour ajuster la taille des images dans les fichiers PDF.