---
title: Emplacements d'images
linktitle: Emplacements d'images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour placer des images dans un document PDF.
type: docs
weight: 170
url: /fr/net/programming-with-images/image-placements/
---

Dans ce didacticiel, nous utiliserons la bibliothèque Aspose.PDF pour .NET pour travailler avec des documents PDF et effectuer des opérations sur les images. Nous allons charger un document PDF, extraire les informations de placement de l'image et récupérer les images avec leurs dimensions visibles.

## Étape 1 : Configurer l'environnement
Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec les éléments suivants :
- Aspose.PDF pour .NET installé sur votre machine.
- Projet AC# prêt à être utilisé.

## Étape 2 : Chargement du document PDF
Pour commencer, nous devons charger le document PDF que nous voulons traiter. Assurez-vous d'avoir le bon chemin d'accès au répertoire contenant le document PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le document PDF source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents contenant le fichier PDF.

## Étape 3 : Extraire les informations d'emplacement des images
 Maintenant que nous avons chargé le document PDF, nous pouvons extraire les informations de placement des images. Nous utiliserons`ImagePlacementAbsorber`pour absorber les emplacements d'image de la première page du document.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Charger le contenu de la première page
doc.Pages[1].Accept(abs);
```

Nous avons maintenant extrait les informations de placement d'image de la première page du document.

## Étape 4 : Récupérer des images avec des dimensions visibles
Nous allons maintenant récupérer les images avec leurs dimensions visibles à partir des informations de placement que nous avons extraites précédemment.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Obtenir les propriétés de l'image
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Récupérer l'image aux dimensions visibles
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Obtenir l'image à partir des ressources
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Créer une image aux dimensions réelles
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

Dans cette boucle, nous récupérons les propriétés de chaque image, telles que la largeur, la hauteur, les coordonnées X et Y du coin inférieur gauche et la résolution horizontale et verticale. Ensuite, nous récupérons chaque image avec ses dimensions visibles à l'aide des informations de placement.

### Exemple de code source pour les placements d'images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le document PDF source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Charger le contenu de la première page
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obtenir les propriétés de l'image
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Récupérer l'image avec des dimensions visibles
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Récupérer l'image des ressources
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Créer une image bitmap avec des dimensions réelles
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusion
Félicitation ! Vous avez maintenant appris à utiliser Aspose.PDF pour .NET pour effectuer des placements d'images dans un document PDF. Nous avons expliqué le code source C # fourni, qui vous permet de charger un document PDF, d'extraire les informations de placement des images et de récupérer les images avec leurs dimensions visibles. N'hésitez pas à expérimenter davantage avec Aspose.PDF pour explorer ses nombreuses autres fonctionnalités.