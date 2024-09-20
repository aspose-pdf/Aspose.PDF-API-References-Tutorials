---
title: Définir la taille de l'image dans le fichier PDF
linktitle: Définir la taille de l'image dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir la taille d'une image dans un PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous aidera à redimensionner les images, à ajuster les propriétés de la page et à enregistrer les PDF.
type: docs
weight: 270
url: /fr/net/programming-with-images/set-image-size/
---
## Introduction

Travailler avec des fichiers PDF est une exigence courante pour de nombreuses applications, et la capacité à manipuler des éléments dans un fichier PDF peut être cruciale. Que vous créiez un générateur de rapports ou que vous ajoutiez du contenu dynamique à votre PDF, le contrôle de la taille des images dans votre document est une fonctionnalité essentielle. Dans ce didacticiel, nous vous expliquerons comment définir la taille de l'image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette puissante bibliothèque offre un contrôle étendu sur le contenu PDF, et nous la décomposerons étape par étape pour vous montrer à quel point cela peut être simple. À la fin, vous serez en mesure de redimensionner les images en toute confiance et de comprendre comment cette fonctionnalité peut améliorer vos flux de travail PDF.


## Prérequis

Avant de plonger dans le code, vous devez mettre en place quelques éléments pour suivre ce didacticiel.

1.  Aspose.PDF pour .NET : assurez-vous que la dernière version de la bibliothèque Aspose.PDF est installée. Vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
2. .NET Framework ou .NET Core : assurez-vous que vous disposez d’un environnement de travail avec .NET Framework ou .NET Core configuré.
3. Connaissances de base de C# : nous utiliserons C# comme langage de programmation, il est donc essentiel de le connaître.
4. Exemple d'image : vous aurez besoin d'un exemple d'image à intégrer au PDF. Vous pouvez utiliser n'importe quelle image, mais assurez-vous qu'elle est accessible dans le répertoire de votre projet.

## Paquets d'importation

Pour utiliser Aspose.PDF pour .NET, vous devez d'abord importer les espaces de noms nécessaires. Voici une configuration simple :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant que nous avons couvert les bases, passons à la création et à la modification d'un document PDF.

## Étape 1 : Initialisez votre document PDF

 La première chose que nous devons faire est de créer un nouveau document PDF. Nous utiliserons le`Document` classe d'Aspose.PDF pour y parvenir.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
```
 
 Ici, nous instancions un`Document` objet, qui représentera notre fichier PDF. Nous spécifions également le répertoire où se trouvent nos fichiers à l'aide de l'`dataDir` variable. C'est le point de départ pour créer n'importe quel PDF avec Aspose.PDF.

## Étape 2 : ajouter une nouvelle page à votre PDF

Une fois notre document prêt, nous devons y ajouter une page. Chaque PDF doit avoir au moins une page, alors ajoutons-en une.

```csharp
// Ajouter une page à la collection de pages du fichier PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Nous ajoutons une nouvelle page au document en utilisant le`Pages.Add()` méthode. Cette page servira de toile sur laquelle nous placerons notre image. Chaque page d'un PDF est essentiellement une page vierge sur laquelle vous pouvez ajouter du texte, des images ou d'autres contenus.

## Étape 3 : Créer une instance d’image

 Il est maintenant temps de préparer l'image que nous voulons insérer dans le PDF. Aspose.PDF fournit un`Image` classe pour gérer les images.

```csharp
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Nous créons une nouvelle instance de la`Image` classe. Cet objet contiendra les propriétés de l'image que nous souhaitons ajouter au PDF. Nous configurerons la taille et le type de l'image dans les étapes suivantes.

## Étape 4 : Définir la taille de l’image (largeur et hauteur)

C'est ici que nous arrivons au cœur de notre tutoriel : définir la taille de l'image. Aspose.PDF vous permet de spécifier la largeur et la hauteur de l'image en points.

```csharp
// Définir la largeur et la hauteur de l'image en points
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 Le`FixWidth` et`FixHeight`Les propriétés vous permettent de définir les dimensions exactes de l'image en points. Dans cet exemple, nous redimensionnons l'image à 100x100 points. Vous pouvez ajuster ces valeurs en fonction de vos besoins.

## Étape 5 : Spécifier le type d’image

Selon le format d'image avec lequel vous travaillez, vous devrez peut-être définir le type d'image. Aspose.PDF prend en charge différents formats d'image, et nous définissons ici le type de fichier.

```csharp
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 Dans ce cas, nous laissons le type de fichier tel quel`Unknown` , qui permet à la bibliothèque de détecter automatiquement le type d'image. Si vous connaissez le type de fichier spécifique, vous pouvez le définir (par exemple,`ImageFileType.Jpeg` pour les images JPEG). Cette étape garantit qu'Aspose sait comment gérer correctement l'image.

## Étape 6 : définissez le chemin d’accès à votre fichier image

Nous devons maintenant indiquer à Aspose où trouver le fichier image. Assurez-vous que votre image est accessible dans le répertoire spécifié.

```csharp
// Chemin d'accès au fichier source
img.File = dataDir + "aspose-logo.jpg";
```
 
 Ici, nous définissons le chemin d'accès au fichier de l'image. L'image, dans ce cas, se trouve dans le`dataDir` dossier et est nommé`aspose-logo.jpg`Assurez-vous de remplacer ceci par le nom et l'emplacement réels de votre fichier image.

## Étape 7 : Ajouter l’image à la page

Avec l’image configurée et le chemin du fichier défini, nous pouvons maintenant ajouter l’image à notre page.

```csharp
// Ajoutez l'image à la collection de paragraphes
page.Paragraphs.Add(img);
```
 
 Le`Paragraphs.Add()` méthode nous permet d'ajouter l'image à la page. Pensez à la`Paragraphs` collection sous forme de liste d'éléments qui seront affichés sur la page PDF. Nous pouvons ajouter plusieurs éléments à cette collection, tels que des images, du texte et des formes.

## Étape 8 : Ajuster les propriétés de la page

Pour nous assurer que notre image s'adapte bien, nous allons ajuster la taille de la page. Cela permettra de garantir que les dimensions de la page correspondent au contenu que nous ajoutons.

```csharp
// Définir les propriétés de la page
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Ici, nous définissons la largeur et la hauteur de la page sur 800 points. Cette étape est facultative mais garantit que la page s'adapte à l'image redimensionnée. Vous pouvez ajuster ces valeurs en fonction de vos besoins spécifiques.

## Étape 9 : Enregistrez le PDF

Enfin, après avoir configuré les propriétés de l'image et de la page, nous pouvons enregistrer le PDF.

```csharp
//Enregistrez le fichier PDF obtenu
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Nous sauvegardons le document modifié sous`SetImageSize_out.pdf` dans le même répertoire. Ce fichier contiendra désormais l'image redimensionnée que vous avez ajoutée.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir la taille d'une image dans un PDF à l'aide d'Aspose.PDF pour .NET. Nous avons expliqué comment créer un document, ajouter une page, configurer une image et enregistrer le résultat. Ce guide étape par étape n'est que le début de ce que vous pouvez faire avec Aspose.PDF pour .NET. Maintenant que vous avez appris à redimensionner des images, n'hésitez pas à explorer d'autres fonctionnalités telles que la mise en forme du texte, la création de tableaux et même l'ajout d'annotations à votre PDF.

## FAQ

### Puis-je utiliser différents formats d’image avec Aspose.PDF pour .NET ?  
Oui, Aspose.PDF prend en charge divers formats d'image tels que JPEG, PNG, BMP et SVG.

### Comment conserver le rapport hauteur/largeur de l’image ?  
 Vous pouvez conserver le rapport hauteur/largeur en réglant soit le`FixWidth` ou`FixHeight` tout en laissant l’autre dimension non définie.

### Puis-je ajouter plusieurs images à une seule page PDF ?  
Absolument ! Répétez simplement le processus d'ajout d'une instance d'image et ajoutez chacune d'elles à la`Paragraphs` collection.

### Est-il possible de définir la taille de l'image dans d'autres unités que les points ?  
Aspose.PDF fonctionne principalement avec des points, mais vous pouvez convertir d'autres unités comme les pouces ou les millimètres en points (1 pouce = 72 points).

### Comment positionner une image à un endroit précis de la page ?  
 Vous pouvez définir le`Image.LowerLeftX` et`Image.LowerLeftY` propriétés pour positionner l'image sur la page.