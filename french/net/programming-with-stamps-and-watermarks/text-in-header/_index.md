---
title: Texte dans l'en-tête
linktitle: Texte dans l'en-tête
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du texte dans l'en-tête d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-stamps-and-watermarks/text-in-header/
---
Dans ce didacticiel, nous allons apprendre à ajouter du texte dans l'en-tête d'un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez les étapes ci-dessous :

## Étape 1 : Préparation du projet

Assurez-vous d'avoir installé Aspose.PDF pour .NET et créé un projet C#.

## Étape 2 : Importer des espaces de noms

Ajoutez les espaces de noms suivants à votre fichier source C# :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Ouvrir le document

Ouvrez le document PDF existant en utilisant le chemin fourni :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Création d'un texte d'en-tête

Créez un nouveau tampon de texte avec le texte que vous souhaitez ajouter dans l'en-tête :

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Vous pouvez personnaliser le texte en modifiant ses propriétés telles que la marge supérieure, l'alignement horizontal et l'alignement vertical.

## Étape 5 : Ajouter un texte d'en-tête à toutes les pages

Parcourez toutes les pages du document PDF et ajoutez le tampon de texte dans l'en-tête :

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Étape 6 : Enregistrer le document PDF

Une fois le texte d'en-tête ajouté sur toutes les pages, enregistrez le document PDF mis à jour :

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF.

### Exemple de code source pour Textin Header utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Créer un en-tête
TextStamp textStamp = new TextStamp("Header Text");

// Définir les propriétés du tampon
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Ajouter un en-tête sur toutes les pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Enregistrer le document mis à jour
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Félicitation ! Vous avez appris à ajouter du texte dans l'en-tête d'un document PDF en utilisant Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos en-têtes en ajoutant du texte supplémentaire à vos documents PDF.
