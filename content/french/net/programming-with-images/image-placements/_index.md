---
title: Placements d'images
linktitle: Placements d'images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire et manipuler les emplacements d'images dans des documents PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec exemples et extraits de code.
type: docs
weight: 170
url: /fr/net/programming-with-images/image-placements/
---
## Introduction

Travailler avec des images dans des fichiers PDF peut être délicat, mais avec Aspose.PDF pour .NET, vous pouvez facilement manipuler et extraire les propriétés d'une image sans effort. Que vous cherchiez à obtenir les dimensions d'une image, à les extraire ou à récupérer d'autres propriétés comme la résolution, Aspose.PDF dispose des outils dont vous avez besoin. Ce didacticiel vous guidera étape par étape sur la façon d'extraire les emplacements d'image dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous aborderons tout, de l'importation de packages à la récupération de propriétés d'image comme la largeur, la hauteur et la résolution.

## Prérequis

Avant de commencer le tutoriel, vous devez mettre en place quelques éléments. Voici une liste de contrôle rapide :

1.  Aspose.PDF pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger[ici](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : vous aurez besoin de Visual Studio ou de tout autre IDE pris en charge par .NET installé sur votre machine.
3. Un document PDF : Préparez un exemple de document PDF contenant des images. Pour cet exemple, nous utiliserons un fichier nommé`ImagePlacement.pdf`.
4. Connaissances de base de C# : bien que ce guide soit adapté aux débutants, des connaissances de base de C# vous aideront à mieux comprendre les extraits de code.

## Paquets d'importation

Avant d'entrer dans le vif du sujet, la première chose à faire est d'importer les espaces de noms nécessaires. Ces packages sont essentiels pour travailler avec des documents PDF et manipuler des images dans Aspose.PDF pour .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Ces packages vous permettent de travailler avec des PDF (`Aspose.Pdf`), manipuler les placements d'images (`Aspose.Pdf.ImagePlacement`), et gérer les flux d'images et les graphiques (`System.Drawing` et`System.IO`).

Maintenant que nous avons mis en place les prérequis et les packages, décomposons chaque partie du didacticiel dans un guide simple et facile à suivre.

## Étape 1 : Charger le document PDF

La première étape consiste à charger le document PDF dans votre projet. Il servira de base pour travailler avec les images contenues dans le fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 Dans cette étape, nous définissons le chemin d'accès au fichier du document PDF à l'aide de`dataDir`et ensuite créer une nouvelle instance du`Aspose.Pdf.Document` classe. Cela nous permet de charger le fichier PDF dans notre programme. Simple, non ? Tout comme l'ouverture d'un livre pour commencer à lire, nous sommes maintenant prêts à explorer le contenu à l'intérieur.

## Étape 2 : Initialiser l'absorbeur de placement d'image

Pour extraire les images, nous avons besoin d'un outil appelé « Image Placement Absorber ». Considérez-le comme un outil qui absorbe toutes les informations d'image sur une page particulière.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Ici, nous créons une instance de`ImagePlacementAbsorber`. Cet objet collecte et stocke des informations sur tous les emplacements d'images sur une page PDF spécifique. Imaginez que vous scanniez une page avec une loupe et que vous identifiez toutes les images qu'elle contient !

## Étape 3 : Acceptez l'absorbeur sur la première page

Ensuite, nous devons indiquer à l'absorbeur quelle page du PDF numériser. Pour cet exemple, nous nous concentrerons sur la première page.

```csharp
doc.Pages[1].Accept(abs);
```

 Le`Accept` La méthode analyse la première page du document PDF à la recherche d'images et stocke les résultats à l'intérieur du`ImagePlacementAbsorber`C'est comme dire à la loupe où chercher les images.

## Étape 4 : Parcourez chaque placement d'image

Maintenant que nous avons scanné la page, nous devons parcourir chaque image trouvée sur la page et récupérer ses propriétés.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Cette boucle parcourt chaque image présente sur la page. Nous imprimons la largeur, la hauteur, le x en bas à gauche (LLX), le y en bas à gauche (LLY) et la résolution de l'image (horizontale et verticale). Ces détails vous aident à comprendre la taille et le positionnement de chaque image dans le PDF.

## Étape 5 : Extraire l'image avec les dimensions visibles

Après avoir collecté des informations sur les images, vous souhaiterez peut-être extraire l'image réelle avec ses dimensions. Voici comment procéder.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Cet extrait de code récupère l'image du PDF et la met à l'échelle selon ses dimensions réelles telles que définies dans le`ImagePlacement` objet. En enregistrant l'image dans un flux de mémoire et en la mettant à l'échelle, vous vous assurez que l'image que vous extrayez conserve la taille exacte à laquelle elle était affichée dans le PDF.

## Conclusion

L'extraction des emplacements d'image d'un document PDF à l'aide d'Aspose.PDF pour .NET est assez simple une fois que vous l'avez décomposée étape par étape. Nous avons tout couvert, du chargement d'un PDF à la récupération des propriétés d'image et à l'extraction des images avec leurs dimensions réelles. Aspose.PDF rend le travail avec les PDF et la manipulation du contenu incroyablement simples, vous permettant de travailler efficacement avec des images, du texte et bien plus encore.

## FAQ

### Puis-je extraire des images d'une page spécifique du PDF ?  
 Oui, en spécifiant le numéro de page lors de l'utilisation du`Accept` méthode, vous pouvez vous concentrer sur n'importe quelle page particulière.

### Quels formats d’image sont pris en charge pour l’extraction ?  
Aspose.PDF prend en charge divers formats, notamment PNG, JPEG, BMP, etc.

### Est-il possible de manipuler l'image extraite ?  
 Absolument ! Une fois extrait, vous pouvez utiliser le`System.Drawing` espace de noms pour manipuler l'image.

### Puis-je extraire des images à partir de fichiers PDF protégés par mot de passe ?  
Oui, vous pouvez, mais vous devrez déverrouiller le PDF à l'aide des informations d'identification appropriées avant d'extraire les images.

### Aspose.PDF pour .NET fonctionne-t-il sur tous les frameworks .NET ?  
Oui, il prend en charge .NET Framework, .NET Core et .NET 5 et versions ultérieures.