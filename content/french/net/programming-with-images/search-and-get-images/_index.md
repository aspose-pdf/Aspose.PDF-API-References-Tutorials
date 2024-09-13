---
title: Rechercher et obtenir des images dans un fichier PDF
linktitle: Rechercher et obtenir des images dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire sans effort des images de fichiers PDF avec Aspose.PDF pour .NET. Suivez ce guide étape par étape pour améliorer vos compétences en matière de traitement PDF.
type: docs
weight: 260
url: /fr/net/programming-with-images/search-and-get-images/
---
## Introduction

Vous recherchez un moyen simple d'extraire des images de fichiers PDF à l'aide d'Aspose.PDF pour .NET ? Vous êtes au bon endroit ! Dans cet article, nous allons examiner en détail comment rechercher et récupérer efficacement des images intégrées dans un document PDF. Que vous soyez un développeur chevronné ou que vous débutiez dans le monde de la manipulation de PDF, ce guide vous guidera tout au long du processus, étape par étape.

## Prérequis

Avant de passer au vif du sujet du code, vous devez vérifier quelques conditions préalables sur votre liste. 

### Cadre .NET

Assurez-vous que .NET Framework est installé sur votre ordinateur. Aspose.PDF pour .NET est compatible avec différentes versions, mais il est préférable d'utiliser la dernière version stable pour profiter de toutes les dernières fonctionnalités et améliorations.

### Bibliothèque Aspose.PDF

 Vous aurez besoin d'accéder à la bibliothèque Aspose.PDF. Si vous ne l'avez pas encore fait, vous pouvez la télécharger à partir de ce lien :[Télécharger Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/) . De plus, vous pouvez explorer leur[essai gratuit d'un mois](https://releases.aspose.com/) pour démarrer vos projets sans aucun frais.

### Environnement de développement

Un environnement de développement approprié comme Visual Studio ou tout autre IDE de votre choix doit être configuré pour écrire et exécuter le code de manière transparente.

## Paquets d'importation

Pour travailler avec Aspose.PDF pour .NET, vous devez d'abord importer les espaces de noms appropriés dans votre projet. Voici ce que vous devez faire :

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

 Chacun de ces packages répond à des objectifs spécifiques lors de la manipulation de documents PDF.`Aspose.Pdf` L'espace de noms est la pierre angulaire de vos opérations, tandis que les deux autres aident à gérer les images et le texte dans le PDF.

## Étape 1 : définissez le chemin d’accès à votre document

Avant toute chose, vous devez définir le chemin où se trouve votre fichier PDF. Ce morceau de code permet de le configurer :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel vers le répertoire contenant votre fichier PDF, par exemple,`C:\Documents\`.

## Étape 2 : Ouvrir le document PDF

 Ensuite, vous devrez charger le document PDF dans votre application. Pour cela, créez un nouveau`Document` instance avec le chemin de fichier que vous venez de spécifier :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

## Étape 3 : Créer l'ImagePlacementAbsorber

 Pour rechercher des images dans un PDF, vous avez besoin d'un`ImagePlacementAbsorber` objet. Cette classe permet d'absorber les images du PDF pendant le processus d'extraction :

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

## Étape 4 : Accepter l'absorbeur pour toutes les pages

 Cette étape est cruciale car elle indique à l'`Document` pour appliquer l'absorbeur d'images sur toutes les pages. Il garantit que toutes les images placées n'importe où dans le document seront identifiées :

```csharp
doc.Pages.Accept(abs);
```

## Étape 5 : Parcourir les placements d'images

Maintenant que vous avez assimilé les images, il est temps de les approfondir. Vous allez parcourir chaque placement d'image extrait du PDF :

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    // Étapes supplémentaires pour obtenir les propriétés de l'image
}
```

## Étape 6 : Extraire les propriétés de l’image

 À l'intérieur de la boucle, vous pouvez commencer à récupérer des propriétés précieuses sur chaque image. En utilisant le`imagePlacement` objet, vous pouvez accéder aux dimensions et à la résolution :

```csharp
XImage image = imagePlacement.Image; // Obtenir l'image

Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
```

## Conclusion

Et voilà ! En suivant ces étapes, vous pouvez rechercher et récupérer efficacement des images à partir de fichiers PDF à l'aide d'Aspose.PDF pour .NET. Avec seulement quelques lignes de code, vous pouvez extraire des images précieuses et leurs propriétés, ouvrant ainsi la voie à de nombreuses possibilités dans votre application.

## FAQ

### La bibliothèque Aspose.PDF est-elle gratuite ?  
Aspose.PDF pour .NET est une bibliothèque payante, mais vous pouvez télécharger un essai gratuit pendant un mois.

### Puis-je extraire des images de fichiers PDF protégés par mot de passe ?  
Oui, mais vous devez fournir le mot de passe lors de l'ouverture du document.

### Quels types d’images peuvent être extraits d’un PDF ?  
Toutes les images intégrées, quel que soit leur format (JPEG, PNG, etc.), peuvent être extraites.

### Y a-t-il une limite au nombre d'images que je peux extraire ?  
Il n'y a pas de limite stricte ; cela dépend du fichier PDF lui-même.

### Puis-je enregistrer les images extraites sur le disque ?  
 Oui, vous pouvez enregistrer les images sur le disque à l'aide de l'`XImage` objet dans votre code.