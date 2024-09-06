---
title: Rechercher et obtenir des images dans un fichier PDF
linktitle: Rechercher et obtenir des images dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour rechercher et obtenir des images dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/programming-with-images/search-and-get-images/
---
Dans ce tutoriel, nous vous expliquerons comment rechercher et obtenir des images dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez la télécharger depuis le site officiel d'Aspose.

## Étape 1 : Chargement du document PDF

Pour commencer, utilisez le code suivant pour charger le document PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Assurez-vous de fournir le chemin correct vers votre document PDF.

## Étape 2 : Recherche des emplacements d'images

Pour rechercher les emplacements des images dans le document PDF, utilisez le code suivant :

```csharp
// Créez un objet ImagePlacementAbsorber pour rechercher des emplacements d'images
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Accepter l'absorbeur pour toutes les pages du document
doc.Pages.Accept(abs);
```

Cela collectera les emplacements des images dans l'absorbeur.

## Étape 3 : Parcourir les emplacements des images et obtenir les images et leurs propriétés

Ensuite, nous allons parcourir les emplacements des images collectées et obtenir les images et leurs propriétés. Utilisez le code suivant :

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Récupérer l'image à l'aide de l'objet ImagePlacement
     XImage image = imagePlacement.Image;

     // Afficher les propriétés de l'emplacement de l'image
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Cela parcourra tous les emplacements d'images, obtiendra les images correspondantes et affichera leurs propriétés.

### Exemple de code source pour rechercher et obtenir des images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Créez un objet ImagePlacementAbsorber pour effectuer une recherche de placement d'image
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Accepter l'absorbeur pour toutes les pages
doc.Pages.Accept(abs);
// Parcourez tous les ImagePlacements, obtenez les propriétés de l'image et de l'ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Récupérer l'image à l'aide de l'objet ImagePlacement
	XImage image = imagePlacement.Image;
	// Afficher les propriétés de placement d'image pour tous les emplacements
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusion

Félicitations ! Vous avez réussi à rechercher et à obtenir des images dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant appliquer cette méthode à vos propres projets pour extraire des images et obtenir leurs propriétés à partir de fichiers PDF.

### FAQ pour rechercher et obtenir des images dans un fichier PDF

#### Q : Quel est le but de rechercher et d’obtenir des images dans un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : La recherche et l'obtention d'images dans un document PDF vous permettent de localiser et d'extraire des images dans le fichier PDF. Cela peut être utile à diverses fins, telles que l'analyse du contenu, la vérification des propriétés de l'image ou le traitement ultérieur des images.

#### Q : Comment fonctionne le processus de recherche d’images dans un document PDF ?

 A : Le processus consiste à utiliser le`ImagePlacementAbsorber` objet permettant d'effectuer une recherche d'emplacements d'images sur toutes les pages du document PDF. L'absorbeur collecte des informations sur l'emplacement, la taille et la résolution de chaque image dans le document.

####  Q : Quel est le but de la`ImagePlacement` object in the code?

 A : Le`ImagePlacement`L'objet représente l'emplacement d'une image dans le document PDF. Il fournit des propriétés qui vous permettent d'accéder à des détails tels que les dimensions, les coordonnées et la résolution de l'image.

#### Q : Puis-je filtrer les images recherchées et obtenues en fonction de critères spécifiques ?

R : Le code fourni collecte des informations sur toutes les images du document PDF. Si vous souhaitez filtrer les images en fonction de critères spécifiques (par exemple, le type d'image, les dimensions, la résolution), vous devrez peut-être modifier le code pour inclure les conditions de filtrage appropriées.

#### Q : Comment puis-je accéder au contenu réel de l’image après avoir obtenu ses informations de placement ?

 A : Le`XImage` objet obtenu à partir du`ImagePlacement` L'objet représente le contenu réel de l'image. Vous pouvez traiter cet objet plus en détail`XImage` objet, comme l'enregistrer dans un fichier ou l'afficher dans votre application.

#### Q : Que puis-je faire avec les propriétés d’image obtenues ?

: Les propriétés d'image obtenues, telles que la largeur, la hauteur, les coordonnées et la résolution, peuvent être utilisées à diverses fins. Vous pouvez analyser les propriétés, les afficher à l'utilisateur ou les utiliser comme entrée pour un traitement ultérieur.

#### Q : Puis-je modifier ou éditer les images dans le document PDF en utilisant cette méthode ?

R : Le code fourni se concentre sur la recherche et l'obtention d'informations sur le placement des images. Pour modifier ou éditer des images, vous devrez peut-être intégrer des fonctionnalités supplémentaires, telles que la manipulation d'images, à l'aide de la bibliothèque Aspose.PDF.

#### Q : Comment puis-je intégrer cette méthode dans mes propres projets ?

R : Pour intégrer cette méthode dans vos projets, suivez les étapes décrites et modifiez le code selon vos besoins. Vous pouvez utiliser les informations et propriétés de placement d'image obtenues en fonction des exigences de votre application.

#### Q : Aspose.PDF pour .NET offre-t-il d’autres fonctionnalités liées à la manipulation d’images dans les documents PDF ?

: Oui, Aspose.PDF pour .NET propose une gamme de fonctionnalités permettant de travailler avec des images dans des documents PDF, notamment l'insertion, le redimensionnement, la rotation, l'extraction d'images, etc. Vous pouvez explorer la documentation et les exemples de la bibliothèque pour découvrir toutes ses fonctionnalités.