---
title: Stocker l'image dans la collection XImage
linktitle: Stocker l'image dans la collection XImage
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour stocker une image dans la collection XImage en utilisant Aspose.PDF pour .NET.
type: docs
weight: 290
url: /fr/net/programming-with-images/store-image-in-ximage-collection/
---

Dans ce didacticiel, nous vous expliquerons comment stocker une image dans la collection XImage à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Étape 1 : Initialisation du document PDF

Pour commencer, utilisez le code suivant pour initialiser un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Initialiser le document
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Étape 2 : Ajouter l'image à la collection XImage

Ensuite, nous ajouterons l'image à la collection XImage du document PDF. Utilisez le code suivant :

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Assurez-vous de fournir le chemin d'accès correct au fichier source de l'image.

## Etape 3 : Placement de l'image sur la page

Plaçons maintenant l'image sur la page du document PDF. Utilisez le code suivant :

```csharp
page. Contents. Add(new GSave());

// Définir les coordonnées
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Utilisation de l'opérateur ConcatenateMatrix : définissez comment l'image doit être placée
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Cela placera l'image aux coordonnées spécifiées sur la page.

## Étape 4 : Enregistrer le document PDF

Enfin, nous enregistrerons le document PDF mis à jour. Utilisez le code suivant :

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Assurez-vous de fournir le chemin et le nom de fichier souhaités pour le document PDF final.

### Exemple de code source pour Store Image In XImage Collection à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser le document
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Définir les coordonnées
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Utilisation de l'opérateur ConcatenateMatrix (matrice de concaténation): définit comment l'image doit être placée
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusion

Félicitation ! Vous avez stocké avec succès une image dans la collection XImage en utilisant Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour manipuler et personnaliser des images dans des fichiers PDF.