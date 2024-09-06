---
title: Placements d'images
linktitle: Placements d'images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour placer des images dans un document PDF.
type: docs
weight: 170
url: /fr/net/programming-with-images/image-placements/
---
Dans ce didacticiel, nous utiliserons la bibliothèque Aspose.PDF pour .NET pour travailler avec des documents PDF et effectuer des opérations sur des images. Nous chargerons un document PDF, extrairons les informations de placement de l'image et récupérerons les images avec leurs dimensions visibles.

## Étape 1 : Configuration de l'environnement
Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec les éléments suivants :
- Aspose.PDF pour .NET installé sur votre machine.
- Projet AC# prêt à être utilisé.

## Étape 2 : Chargement du document PDF
Pour commencer, nous devons charger le document PDF que nous voulons traiter. Assurez-vous d'avoir le bon chemin d'accès au répertoire contenant le document PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le document PDF source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel vers votre répertoire de documents contenant le fichier PDF.

## Étape 3 : Extraire les informations de placement des images
 Maintenant que nous avons chargé le document PDF, nous pouvons extraire les informations de placement des images. Nous utiliserons`ImagePlacementAbsorber`pour absorber les emplacements des images de la première page du document.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Charger le contenu de la première page
doc.Pages[1].Accept(abs);
```

Nous avons maintenant extrait les informations de placement de l’image de la première page du document.

## Étape 4 : Récupérer les images avec des dimensions visibles
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

     // Récupérer l'image avec les dimensions visibles
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Obtenir l'image à partir des ressources
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Créer une image avec des dimensions réelles
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

Dans cette boucle, nous récupérons les propriétés de chaque image, telles que la largeur, la hauteur, les coordonnées X et Y du coin inférieur gauche et la résolution horizontale et verticale. Nous récupérons ensuite chaque image avec ses dimensions visibles à l'aide des informations de placement.

### Exemple de code source pour les placements d'images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
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
	// Récupérer une image avec des dimensions visibles
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Récupérer l'image à partir des ressources
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Créer une image bitmap avec des dimensions réelles
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusion
Félicitations ! Vous avez maintenant appris à utiliser Aspose.PDF pour .NET pour effectuer des placements d'images dans un document PDF. Nous avons expliqué le code source C# fourni, qui vous permet de charger un document PDF, d'extraire les informations de placement des images et de récupérer les images avec leurs dimensions visibles. N'hésitez pas à expérimenter davantage avec Aspose.PDF pour explorer ses nombreuses autres fonctionnalités.

### FAQ

#### Q : Quel est le but de l’extraction des informations de placement d’image à partir d’un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : L'extraction des informations de placement d'image vous permet de récupérer le positionnement, les dimensions et la résolution des images dans un document PDF. Ces informations sont essentielles pour une manipulation et une analyse précises des images.

#### Q : Comment Aspose.PDF pour .NET facilite-t-il l’extraction des informations de placement d’image à partir d’un document PDF ?

 A : Aspose.PDF pour .NET fournit le`ImagePlacementAbsorber`classe, qui peut être utilisée pour récupérer les détails de placement d'image à partir d'un document PDF. Le code fourni montre comment utiliser cette classe pour récupérer les informations de placement d'image.

#### Q : À quoi peuvent servir les informations de placement d’image dans des scénarios réels ?

R : Les informations de placement d’image sont utiles pour des tâches telles que garantir un alignement précis de l’image, calculer les dimensions de l’image, vérifier la qualité de l’image et générer des rapports sur l’utilisation de l’image dans un document PDF.

#### Q : Comment l’exemple de code garantit-il une extraction précise des informations de placement d’image ?

 A : L'exemple de code utilise le`ImagePlacementAbsorber` classe permettant de parcourir le contenu d'une page spécifiée, d'identifier les emplacements des images et de récupérer leurs attributs, tels que la largeur, la hauteur, les coordonnées et la résolution.

#### Q : Le code peut-il être étendu pour traiter des images sur plusieurs pages ou documents ?

: Oui, le code peut être étendu en parcourant plusieurs pages ou documents pour extraire des informations de placement d’image et effectuer des tâches liées à l’image.

#### Q : Comment le code récupère-t-il les images avec leurs dimensions visibles en fonction des informations de placement ?

R : L’exemple de code extrait les données d’image des ressources, crée une image bitmap avec les dimensions réelles et fournit des propriétés telles que la largeur, la hauteur, les coordonnées et la résolution.

#### Q : Cette approche est-elle efficace pour les documents PDF volumineux contenant de nombreuses images ?

R : Oui, Aspose.PDF pour .NET est optimisé pour les performances et l'utilisation des ressources. Il extrait efficacement les informations de placement d'image, même à partir de documents PDF volumineux.

#### Q : Comment les développeurs peuvent-ils bénéficier de la compréhension et de l’utilisation des informations de placement d’image ?

: Les développeurs peuvent garantir une manipulation, un alignement et une analyse précis des images dans les documents PDF. Ces informations leur permettent de créer des applications de traitement d'images, de création de rapports et d'assurance qualité.

#### Q : Le code peut-il être personnalisé pour extraire des attributs ou des métadonnées supplémentaires liés à l’image ?

R : Absolument, le code peut être amélioré pour extraire des attributs supplémentaires, tels que le type d’image, l’espace colorimétrique, la compression, etc., en utilisant les classes et méthodes appropriées fournies par Aspose.PDF pour .NET.

#### Q : Quelle est la signification de la conclusion fournie dans ce tutoriel ?

R : La conclusion résume le contenu du didacticiel et encourage une exploration plus approfondie d'Aspose.PDF pour .NET afin d'exploiter ses capacités au-delà des placements d'images, ouvrant ainsi la porte à diverses tâches liées au PDF.