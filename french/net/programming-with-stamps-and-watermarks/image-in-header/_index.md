---
title: Image dans l'en-tête
linktitle: Image dans l'en-tête
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une image dans la section d'en-tête d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-stamps-and-watermarks/image-in-header/
---
Dans ce didacticiel, nous vous guiderons étape par étape sur la façon d'ajouter une image dans la section d'en-tête d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour ouvrir un document PDF existant, créer un tampon d'image, définir ses propriétés et l'ajouter à toutes les pages du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Charger le document PDF existant

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF existant
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Création et ajout de l'image dans la section d'en-tête

Maintenant que le document PDF est chargé, nous pouvons créer un tampon d'image et l'ajouter à toutes les pages du document en tant que section d'en-tête. Voici comment:

```csharp
// Créer le tampon de trame
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Définir les propriétés du tampon d'image
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Ajouter un tampon d'image à toutes les pages
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Le code ci-dessus crée un tampon d'image à partir du fichier "aspose-logo.jpg" et définit ses propriétés, telles que la marge supérieure, l'alignement horizontal et vertical. Ensuite, le tampon d'image est ajouté à toutes les pages du document PDF en tant que section d'en-tête.

## Étape 4 : Enregistrer le document PDF modifié

Une fois l'image ajoutée dans la section d'en-tête, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Imagein Header utilisant Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Créer un en-tête
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Définir les propriétés du tampon
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Ajouter un en-tête sur toutes les pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Conclusion

Félicitation ! Vous avez appris à ajouter une image dans la section d'en-tête d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant personnaliser les en-têtes de vos documents PDF en ajoutant des images.
