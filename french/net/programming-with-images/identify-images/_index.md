---
title: Identifier les images
linktitle: Identifier les images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Identifiez facilement les images dans un fichier PDF et déterminez leur type de couleur avec Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-images/identify-images/
---

Ce guide vous expliquera étape par étape comment identifier les images dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Assurez-vous de définir le répertoire de documents correct. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etape 2 : Initialiser les compteurs

Dans cette étape, nous allons initialiser les compteurs pour les images en niveaux de gris et les images RVB.

```csharp
int grayscaled = 0; // Compteur pour les images en niveaux de gris
int rdg = 0; // Compteur pour les images RVB
```

## Étape 3 : Ouvrez le document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Étape 4 : parcourir les pages du document

Dans cette étape, nous allons parcourir toutes les pages du document PDF et identifier les images sur chaque page.

```csharp
foreach(Page page in document.Pages)
{
```

## Étape 5 : Récupérer les emplacements d'image

 Dans cette étape, nous utiliserons`ImagePlacementAbsorber` pour récupérer les emplacements d'image sur chaque page.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Étape 6 : Comptez les images et identifiez leur type de couleur

Dans cette étape, nous allons compter le nombre d'images sur chaque page et identifier leur type de couleur (niveaux de gris ou RVB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Exemple de code source pour identifier les images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Compteur pour les images en niveaux de gris
int grayscaled = 0;
// Compteur pour les images RVB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Obtenir le nombre d'images sur une page spécifique
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].Accepter(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Conclusion

Félicitation ! Vous avez identifié avec succès des images dans un PDF à l'aide d'Aspose.PDF pour .NET. Les images ont été comptées et leur type de couleur (niveaux de gris ou RVB) a été identifié. Vous pouvez maintenant utiliser ces informations pour vos besoins spécifiques.