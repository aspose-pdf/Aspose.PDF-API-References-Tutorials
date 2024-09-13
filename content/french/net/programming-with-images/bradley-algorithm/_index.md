---
title: Algorithme de Bradley
linktitle: Algorithme de Bradley
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment convertir un fichier PDF en TIFF à l'aide de l'algorithme Bradley dans Aspose.PDF pour .NET. Guide étape par étape, conditions préalables et FAQ pour une conversion transparente.
type: docs
weight: 30
url: /fr/net/programming-with-images/bradley-algorithm/
---
## Introduction

Travailler avec des fichiers PDF peut parfois nécessiter plus que de les lire ou de les modifier : vous devrez peut-être les convertir en images. Une méthode efficace pour convertir des fichiers PDF en images TIFF consiste à utiliser l'algorithme Bradley via la bibliothèque Aspose.PDF pour .NET. Cette méthode garantit des images binaires de haute qualité, parfaites pour l'archivage de documents et d'autres cas d'utilisation spécialisés.

Ce didacticiel vous guidera à travers un processus détaillé et facile à suivre pour convertir une page PDF en image TIFF avec l'algorithme de binarisation Bradley. Aspose.PDF pour .NET simplifie cette tâche, vous offrant la possibilité d'automatiser et de rationaliser vos flux de travail de documents.

## Prérequis

Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre :

-  Aspose.PDF pour .NET : vous aurez besoin de la bibliothèque. Téléchargez-la à partir de[ici](https://releases.aspose.com/pdf/net/).
- Visual Studio (ou tout autre IDE C#).
- Connaissances de base de C#.
-  Un permis valide ou un[permis temporaire](https://purchase.aspose.com/temporary-license/) de Aspose.

## Paquets d'importation

Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires dans votre projet. Ces bibliothèques vous fourniront les outils nécessaires pour manipuler les documents PDF, les convertir au format TIFF et appliquer l’algorithme de binarisation Bradley.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Décomposons le processus en étapes simples pour vous assurer de pouvoir le suivre sans problème. À la fin de ce guide, vous aurez réussi à convertir une page PDF en une image TIFF binaire à l'aide de l'algorithme Bradley.

## Étape 1 : définir le répertoire du document

La première étape consiste à spécifier le chemin d'accès au répertoire où se trouve votre document PDF. Vous définirez également les chemins de sortie des images TIFF qui seront générées.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Chemin vers votre fichier PDF
```

C'est ici que vous stockez à la fois le PDF source et les fichiers TIFF convertis. Assurez-vous que le répertoire est correctement défini pour que le code puisse lire et écrire des fichiers sans erreur.

## Étape 2 : Ouvrir le document PDF

Maintenant que le chemin est défini, il est temps d'ouvrir le document PDF que vous souhaitez convertir. Aspose.PDF pour .NET simplifie le chargement d'un document pour un traitement ultérieur.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Ici,`PageToTIFF.pdf` est le fichier d'exemple. Vous pouvez le remplacer par n'importe quel fichier PDF de votre choix. L'objet document contient désormais le PDF pour une manipulation ultérieure.

## Étape 3 : Définir les chemins de sortie pour les images

Ensuite, vous spécifierez les chemins de sortie pour les fichiers TIFF générés, y compris le TIFF standard et la version binarisée.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

En séparant ces chemins, vous aurez un fichier pour la conversion TIFF standard et un autre pour l'image binarisée après l'application de l'algorithme Bradley.

## Étape 4 : Créer un objet de résolution

Lors de la conversion de fichiers PDF en TIFF, la résolution joue un rôle important dans la détermination de la qualité de l'image. Pour nos besoins, nous la définirons sur 300 DPI pour garantir une sortie de haute qualité.

```csharp
Resolution resolution = new Resolution(300);
```

Un DPI plus élevé signifie une meilleure clarté d’image, en particulier lorsqu’il s’agit de documents qui seront imprimés ou archivés.

## Étape 5 : Configurer les paramètres TIFF

Ensuite, vous devrez configurer les paramètres de l'image TIFF. Ici, nous utiliserons la compression LZW et définirons la profondeur de couleur sur 1 bpp (1 bit par pixel) pour obtenir une image binaire.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

En définissant la profondeur à 1 bpp, nous préparons l'image pour la sortie binaire. La compression LZW est choisie pour son efficacité à réduire la taille du fichier sans perte de qualité.

## Étape 6 : Créer le périphérique TIFF

Vous devez maintenant créer un périphérique TIFF qui gérera la conversion. Ce périphérique utilise la résolution et les paramètres TIFF définis précédemment.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Le périphérique TIFF est au cœur de cette opération. Il prend le document PDF et convertit chaque page en une image TIFF, en fonction de vos paramètres prédéfinis.

## Étape 7 : Convertir la page PDF en TIFF

 Il est temps de traiter le PDF et de convertir la première page en image TIFF.`Process` La méthode vous permet de convertir des pages spécifiques ou le document entier. Dans cet exemple, nous convertissons la première page.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Une fois la méthode terminée, vous aurez une image TIFF enregistrée à l'emplacement défini précédemment.

## Étape 8 : Appliquer l’algorithme de binarisation de Bradley

C'est là que la magie opère : l'algorithme Bradley ! Cet algorithme convertit l'image TIFF en niveaux de gris en image binaire, l'optimisant ainsi pour les systèmes de reconnaissance de documents.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 La méthode BinarizeBradley prend deux flux de fichiers (entrée et sortie), ainsi qu'une valeur de seuil (ici,`0.1`) qui détermine le niveau de binarisation. Après l'exécution, vous aurez une image parfaitement binarisée prête à l'emploi.

## Étape 9 : Confirmer la conversion réussie

Enfin, il est recommandé d'informer l'utilisateur que le processus a réussi. Vous pouvez le faire avec une simple sortie de console.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Une fois cela imprimé, vous savez que votre page PDF a été convertie avec succès en une image TIFF binaire !

## Conclusion

Et voilà ! Vous venez d'apprendre à convertir une page PDF en image TIFF et à appliquer l'algorithme de binarisation Bradley à l'aide d'Aspose.PDF pour .NET. Ce processus est essentiel pour l'archivage de documents, la reconnaissance optique de caractères (OCR) et d'autres applications professionnelles. Grâce à une résolution de haute qualité et à une compression efficace, vous pouvez vous assurer que les images de vos documents sont à la fois claires et gérables en termes de taille.

## FAQ

### Qu'est-ce que l'algorithme de Bradley ?
L'algorithme de Bradley est une technique de binarisation qui convertit les images en niveaux de gris en images binaires (noir et blanc) en déterminant un seuil adaptatif pour chaque pixel en fonction de son environnement.

### Puis-je convertir plusieurs pages PDF en TIFF en utilisant cette méthode ?
 Oui, vous pouvez modifier le`Process` méthode pour convertir toutes les pages en parcourant les pages du document.

### Quelle est la résolution optimale pour convertir des PDF en TIFF ?
Pour des images de haute qualité, 300 DPI sont généralement recommandés. Cependant, vous pouvez ajuster cette valeur en fonction de vos besoins.

### Que signifie 1bpp en profondeur de couleur ?
1bpp (1 bit par pixel) signifie que l'image sera en noir et blanc, chaque pixel étant soit entièrement noir, soit entièrement blanc.

### L'algorithme Bradley est-il adapté à l'OCR ?
Oui, l’algorithme Bradley est souvent utilisé dans le prétraitement OCR car il améliore le contraste du texte dans les documents numérisés.