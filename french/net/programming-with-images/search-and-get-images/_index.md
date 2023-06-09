---
title: Rechercher et obtenir des images
linktitle: Rechercher et obtenir des images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour rechercher et obtenir des images dans un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/programming-with-images/search-and-get-images/
---

Dans ce didacticiel, nous vous expliquerons comment rechercher et obtenir des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Assurez-vous de fournir le chemin d'accès correct à votre document PDF.

## Étape 2 : Recherche d'emplacements d'images

Pour rechercher les emplacements des images dans le document PDF, utilisez le code suivant :

```csharp
// Créer un objet ImagePlacementAbsorber pour rechercher des emplacements d'image
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Accepter l'absorbeur pour toutes les pages du document
doc.Pages.Accept(abs);
```

Cela collectera les emplacements des images dans l'absorbeur.

## Étape 3 : Parcourir les emplacements des images et obtenir des images et leurs propriétés

Ensuite, nous allons parcourir les emplacements des images collectées et obtenir les images et leurs propriétés. Utilisez le code suivant :

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Obtenir l'image à l'aide de l'objet ImagePlacement
     XImage image = imagePlacement.Image;

     // Afficher les propriétés d'emplacement de l'image
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Cela permettra de parcourir tous les emplacements d'images, d'obtenir des images correspondantes et d'afficher leurs propriétés.

### Exemple de code source pour rechercher et obtenir des images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Créer un objet ImagePlacementAbsorber pour effectuer une recherche de placement d'image
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Accepter l'absorbeur pour toutes les pages
doc.Pages.Accept(abs);
// Parcourez tous les ImagePlacements, obtenez les propriétés de l'image et de l'ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obtenir l'image à l'aide de l'objet ImagePlacement
	XImage image = imagePlacement.Image;
	// Afficher les propriétés d'emplacement d'image pour tous les emplacements
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusion

Félicitation ! Vous avez recherché et obtenu avec succès des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour extraire des images et obtenir leurs propriétés à partir de fichiers PDF.