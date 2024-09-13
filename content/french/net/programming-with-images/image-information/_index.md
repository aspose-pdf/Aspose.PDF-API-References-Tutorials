---
title: Informations sur l'image dans le fichier PDF
linktitle: Informations sur l'image dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire des informations d'image à partir de fichiers PDF à l'aide d'Aspose.PDF pour .NET avec notre guide complet étape par étape.
type: docs
weight: 160
url: /fr/net/programming-with-images/image-information/
---
## Introduction

Les fichiers PDF sont désormais omniprésents : pratiquement tous les documents professionnels et personnels se retrouvent à un moment ou à un autre dans ce format. Qu'il s'agisse d'un rapport, d'une brochure ou d'un livre électronique, comprendre comment interagir avec ces fichiers par programmation offre une myriade de possibilités. L'une des exigences courantes est d'extraire des informations sur les images des fichiers PDF. Dans ce guide, nous allons découvrir comment utiliser la bibliothèque Aspose.PDF pour .NET pour extraire des détails cruciaux sur les images intégrées dans un document PDF.

## Prérequis

Avant de passer aux choses sérieuses du codage, vous devez respecter quelques conditions préalables :

1. Environnement de développement : vous aurez besoin d'un environnement de développement .NET configuré. Il peut s'agir de Visual Studio ou de tout autre IDE compatible .NET.
2.  Bibliothèque Aspose.PDF : Assurez-vous d'avoir accès à la bibliothèque Aspose.PDF. Vous pouvez la télécharger à partir du[Site Web d'Aspose](https://releases.aspose.com/pdf/net/). 
3. Connaissances de base en C# : la familiarité avec C# et les concepts de programmation orientée objet vous aidera à suivre le didacticiel sans effort.
4. Document PDF : Ayez à portée de main un exemple de document PDF contenant des images pour tester votre code. 

## Importation de paquets

Pour commencer à utiliser la bibliothèque Aspose.PDF, vous devez importer les espaces de noms nécessaires dans votre fichier C#. Voici un bref aperçu :

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Ces espaces de noms vous donneront accès aux classes et méthodes requises pour manipuler les fichiers PDF et extraire les données d'image.

Maintenant que vous avez tout mis en place, il est temps de décomposer le tout en étapes faciles à gérer. Nous allons écrire un programme C# qui charge un document PDF, parcourt chaque page et extrait les dimensions et la résolution de chaque image du document.

## Étape 1 : Initialiser le document

 Dans cette étape, nous allons initialiser le document PDF en utilisant le chemin d'accès à votre fichier PDF. Vous devez remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve votre fichier PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF source
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Nous créons un`Document` objet qui charge le PDF à partir du répertoire spécifié. Cela nous permettra de travailler avec le contenu du fichier.

## Étape 2 : définir la résolution par défaut et initialiser les structures de données

Ensuite, nous définissons une résolution par défaut pour les images, ce qui est utile pour les calculs. Nous préparerons également un tableau pour contenir les noms des images et une pile pour gérer les états graphiques.

```csharp
// Définir la résolution par défaut de l'image
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Définir un objet de liste de tableaux qui contiendra les noms d'images
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 Le`defaultResolution` variable nous aide à calculer correctement la résolution des images.`graphicsState`La pile sert à stocker l'état graphique actuel du document lorsque nous rencontrons des opérateurs de transformation.

## Étape 3 : Traitez chaque opérateur sur la page

Nous parcourons maintenant tous les opérateurs de la première page du document. C'est là que le gros du travail se déroule. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Opérateurs de procédés...
}
```
Chaque opérateur dans un fichier PDF est une commande qui indique au moteur de rendu comment gérer les éléments graphiques, y compris les images.

## Étape 4 : gérer les opérateurs GSave/GRestore

À l'intérieur de la boucle, nous gérerons les commandes de sauvegarde et de restauration des graphiques pour suivre les modifications apportées à l'état graphique.

```csharp
if (opSaveState != null) 
{
    // Enregistrer l'état précédent
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Restaurer l'état précédent
    graphicsState.Pop();
}
```
`GSave` enregistre l'état graphique actuel, tandis que`GRestore` restaure le dernier état enregistré, nous permettant d'annuler toutes les transformations lors du traitement des images.

## Étape 5 : Gérer les matrices de transformation

Ensuite, nous gérons la concaténation des matrices de transformation lors de l’application de transformations aux images.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Lorsqu'une matrice de transformation est appliquée, nous la multiplions par la matrice actuelle stockée dans l'état graphique afin de pouvoir suivre toute mise à l'échelle ou translation appliquée à l'image.

## Étape 6 : Extraire les informations de l’image

Enfin, nous traitons l’opérateur de dessin pour les images et extrayons les informations nécessaires, comme les dimensions et les résolutions.

```csharp
else if (opDo != null) 
{
    // Opérateur Handle Do qui dessine des objets
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Afficher les informations
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Ici, nous vérifions si l'opérateur est responsable du dessin d'une image. Si c'est le cas, nous obtenons l'objet XImage correspondant, calculons ses dimensions à l'échelle et sa résolution, et imprimons les informations nécessaires.

## Conclusion

Félicitations ! Vous venez de créer un exemple fonctionnel d'extraction d'informations d'image à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité peut être extrêmement utile pour les développeurs qui doivent analyser ou manipuler des documents PDF pour diverses applications, telles que la création de rapports, l'extraction de données ou même des visionneuses PDF personnalisées. 


## FAQ

### Qu'est-ce que la bibliothèque Aspose.PDF ?
La bibliothèque Aspose.PDF est un outil puissant pour créer, manipuler et convertir des fichiers PDF dans des applications .NET.

### Puis-je utiliser la bibliothèque gratuitement ?
 Oui, Aspose propose un essai gratuit. Vous pouvez le télécharger[ici](https://releases.aspose.com/).

### Quels types de formats d’image peuvent être extraits ?
La bibliothèque prend en charge différents formats d'image, notamment JPEG, PNG et TIFF, à condition qu'ils soient intégrés au PDF.

### L'Aspose est-il utilisé à des fins commerciales ?
 Oui, vous pouvez utiliser les produits Aspose à des fins commerciales. Pour obtenir une licence, visitez le site[page d'achat](https://purchase.aspose.com/buy).

### Comment obtenir de l'aide pour Aspose ?
 Vous pouvez accéder au forum d'assistance[ici](https://forum.aspose.com/c/pdf/10).