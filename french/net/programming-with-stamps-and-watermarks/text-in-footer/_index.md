---
title: Texte dans le pied de page
linktitle: Texte dans le pied de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du texte dans le pied de page d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 180
url: /fr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Dans ce didacticiel, nous allons apprendre à ajouter du texte dans le pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez les étapes ci-dessous :

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Créer un texte de pied de page

Créez un nouveau tampon de texte avec le texte que vous souhaitez ajouter dans le pied de page :

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Vous pouvez personnaliser le texte en modifiant ses propriétés telles que la marge inférieure, l'alignement horizontal et l'alignement vertical.

## Étape 5 : Ajouter du texte de pied de page à toutes les pages

Parcourez toutes les pages du document PDF et ajoutez le tampon de texte dans le pied de page :

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Étape 6 : Enregistrer le document PDF

Une fois le texte du pied de page ajouté sur toutes les pages, enregistrez le document PDF mis à jour :

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF.

### Exemple de code source pour Textin Footer utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Créer un pied de page
TextStamp textStamp = new TextStamp("Footer Text");

// Définir les propriétés du tampon
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Ajouter un pied de page sur toutes les pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Enregistrer le fichier PDF mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Félicitation ! Vous avez appris à ajouter du texte dans le pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos pieds de page en ajoutant du texte supplémentaire à vos documents PDF.
