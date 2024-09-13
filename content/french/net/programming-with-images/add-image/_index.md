---
title: Ajouter une image dans un fichier PDF
linktitle: Ajouter une image dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des images à un fichier PDF par programmation à l'aide d'Aspose.PDF pour .NET. Guide étape par étape, exemple de code et FAQ inclus pour une mise en œuvre transparente.
type: docs
weight: 10
url: /fr/net/programming-with-images/add-image/
---
## Introduction

Vous êtes-vous déjà demandé comment insérer une image dans un fichier PDF par programmation ? Que vous développiez un système de génération de documents ou que vous ajoutiez des éléments de marque à vos fichiers PDF, Aspose.PDF pour .NET simplifie considérablement cette tâche. Découvrons ensemble un didacticiel étape par étape sur la façon d'ajouter une image à un PDF à l'aide d'Aspose.PDF pour .NET.

## Prérequis

Avant de passer au code, passons rapidement en revue les exigences de base dont vous avez besoin pour commencer :

- Bibliothèque Aspose.PDF pour .NET : Téléchargez et installez la dernière version à partir de[ici](https://releases.aspose.com/pdf/net/).
- Environnement de développement .NET : Visual Studio ou tout autre IDE de votre choix.
- Connaissances de base de C# : Familiarité avec la programmation C# de base et les principes orientés objet.
- Fichiers PDF et image : Un exemple de fichier PDF et une image à insérer.

## Importation des packages requis

Pour commencer à travailler avec Aspose.PDF, vous devez importer les espaces de noms nécessaires. Voici comment procéder :

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Ces importations vous aideront à interagir avec les documents PDF, à manipuler leur contenu et à gérer efficacement les flux de fichiers.

Maintenant, décomposons la tâche d’ajout d’une image dans un document PDF en étapes faciles à suivre.

## Étape 1 : Configurer le chemin du document et ouvrir le PDF

Avant d'ajouter l'image, la première chose à faire est de localiser votre fichier PDF et de l'ouvrir. Voici le code pour y parvenir :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```
 Le`Document`La classe d'Aspose.PDF est utilisée pour ouvrir et travailler avec un fichier PDF existant. Vous devrez spécifier le chemin du répertoire où se trouve votre PDF.

## Étape 2 : Définir les coordonnées de l'image

Pour positionner correctement l'image dans le PDF, vous devez définir les coordonnées de l'endroit où elle doit apparaître. Pour ce faire, vous pouvez spécifier les coins inférieur gauche et supérieur droit du rectangle de l'image.

```csharp
// Définir les coordonnées
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```
Ces coordonnées définissent l'emplacement de l'image sur la page. Les coordonnées en bas à gauche (100, 100) représentent le point de départ, tandis que les coordonnées en haut à droite (200, 200) définissent la taille et le point final de l'image.

## Étape 3 : sélectionnez la page pour insérer l'image

Ensuite, vous devez spécifier à quelle page du PDF vous souhaitez ajouter l'image. Aspose.PDF vous permet d'accéder à n'importe quelle page du document à l'aide de l'indexation de base zéro.

```csharp
// Obtenez la page où l'image doit être ajoutée
Page page = pdfDocument.Pages[1];
```
Dans cet exemple, nous ajoutons l'image à la première page du PDF (Pages[1] fait référence à la première page car il s'agit d'une indexation à base unique).

## Étape 4 : charger l’image dans un flux

Maintenant, chargez l’image de votre répertoire dans un flux afin qu’elle puisse être traitée et insérée dans le PDF.

```csharp
// Charger l'image dans le flux
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```
 Le`FileStream` La classe est utilisée pour ouvrir le fichier image. Le fichier image (`aspose-logo.jpg`) est chargé à partir du répertoire spécifié et ouvert en mode lecture (`FileMode.Open`).

## Étape 5 : Ajoutez l'image à la page PDF Ressources

Une fois l'image chargée dans un flux, vous pouvez l'ajouter aux ressources de la page PDF.

```csharp
// Ajouter une image à la collection d'images des ressources de la page
page.Resources.Images.Add(imageStream);
```
Cette étape ajoute l'image à la collection de ressources de la page. L'image sera désormais disponible pour le rendu sur la page.

## Étape 6 : Enregistrer l’état actuel des graphiques

 Avant de placer l'image sur la page, vous devez enregistrer l'état graphique actuel à l'aide de l'`GSave` opérateur. Cela garantit que les transformations appliquées à l'image n'affecteront pas le reste du document.

```csharp
//Utilisation de l'opérateur GSave : cet opérateur enregistre l'état actuel des graphiques
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```
 Le`GSave` L'opérateur enregistre les paramètres graphiques actuels, ce qui vous permettra ultérieurement de les restaurer, garantissant que le placement de l'image ne perturbe pas les autres contenus de la page.

## Étape 7 : Définir le placement de l'image avec un rectangle et une matrice

 Maintenant, créez un`Rectangle` objet qui définit où l'image sera positionnée sur la page et un`Matrix` pour contrôler le placement et la mise à l'échelle.

```csharp
// Créer des objets rectangulaires et matriciels
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```
 Le`Rectangle` définit les coordonnées de l'image sur la page PDF, et le`Matrix` assure une mise à l'échelle et un positionnement corrects.

## Étape 8 : Concaténer la matrice pour le placement de l'image

 Le`ConcatenateMatrix` L'opérateur est utilisé pour appliquer la transformation matricielle, garantissant que l'image est placée correctement.

```csharp
// Utilisation de l'opérateur ConcatenateMatrix (matrice de concaténation) : définit comment l'image doit être placée
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```
Cette transformation garantit que l'image est placée au bon endroit sur la page en utilisant les valeurs de matrice définies.

## Étape 9 : Afficher l'image sur la page PDF

 Enfin, utilisez le`Do` opérateur permettant de restituer réellement l'image sur la page PDF.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Utilisation de l'opérateur Do : cet opérateur dessine une image
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```
 Le`Do` L'opérateur dessine l'image à l'emplacement défini par la transformation matricielle précédente.

## Étape 10 : Restaurer l’état graphique

 Une fois l'image ajoutée, restaurez l'état graphique précédent à l'aide de la`GRestore` opérateur.

```csharp
// Utilisation de l'opérateur GRestore : cet opérateur restaure l'état des graphiques
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```
Cette étape garantit que toutes les modifications apportées à l’état graphique (telles que les transformations ou la mise à l’échelle) sont annulées, laissant ainsi le reste du document inchangé.

## Étape 11 : Enregistrer le document PDF mis à jour

Enfin, enregistrez le PDF avec l’image nouvellement ajoutée dans un fichier.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
```
 Le`Save` La méthode est utilisée pour enregistrer le document PDF avec l'image ajoutée, et le fichier mis à jour est enregistré sous le nom « AddImage_out.pdf ».

## Conclusion

L'insertion d'une image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET est simple lorsque vous la décomposez étape par étape. En utilisant les différents opérateurs tels que`GSave`, `ConcatenateMatrix` , et`Do`, vous pouvez facilement contrôler le placement et le rendu des images dans vos documents PDF. Cette technique est essentielle pour personnaliser et personnaliser les fichiers PDF avec des logos, des filigranes ou toute autre image.

## FAQ

### Puis-je ajouter plusieurs images sur une seule page ?  
Oui, vous pouvez ajouter plusieurs images sur la même page en répétant les étapes de chargement et de placement de chaque image.

### Comment contrôler la taille de l'image insérée ?  
La taille de l'image est contrôlée par les coordonnées du rectangle (`lowerLeftX`, `lowerLeftY`, `upperRightX`, `upperRightY`).

### Puis-je insérer d’autres types de fichiers comme PNG ou GIF ?  
Oui, Aspose.PDF prend en charge divers formats d'image, notamment PNG, GIF, BMP et JPEG.

### Est-il possible d'ajouter des images de manière dynamique ?  
Oui, vous pouvez charger et insérer dynamiquement des images en fournissant le chemin du fichier ou en utilisant des flux.

### Aspose.PDF permet-il d'ajouter des images en masse à plusieurs pages ?  
Oui, vous pouvez parcourir les pages d’un document et ajouter des images à plusieurs pages en utilisant la même approche.