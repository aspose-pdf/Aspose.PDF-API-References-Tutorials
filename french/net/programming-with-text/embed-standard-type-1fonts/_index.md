---
title: Intégrer des polices de type 1 standard
linktitle: Intégrer des polices de type 1 standard
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à incorporer des polices de type 1 standard dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-text/embed-standard-type-1fonts/
---

Ce didacticiel vous guidera tout au long du processus d'intégration de polices standard de type 1 dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez incorporer des polices de type 1 standard, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Chargez le document PDF existant
 Chargez un document PDF existant à l'aide de la`Document` constructeur et en transmettant le chemin d'accès au fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Étape 5 : Définissez la propriété EmbedStandardFonts
 Met le`EmbedStandardFonts` propriété du document à`true` afin de permettre l'intégration des polices standard de type 1.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Étape 6 : intégrez des polices dans chaque page
 Parcourez chaque page du document PDF et vérifiez si les polices sont déjà intégrées. Si ce n'est pas le cas, réglez le`IsEmbedded` propriété à`true` pour incorporer la police.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Étape 7 : Enregistrez le document PDF mis à jour
 Enregistrez le document PDF mis à jour à l'aide de`Save` méthode de la`Document` objet, en spécifiant le chemin du fichier de sortie.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Exemple de code source pour Embed Standard Type 1Fonts en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger un document PDF existant
Document pdfDocument = new Document(dataDir + "input.pdf");
// Définir la propriété EmbedStandardFonts du document
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Vérifiez si la police est déjà intégrée
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Conclusion
Vous avez intégré avec succès des polices de type 1 standard dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF mis à jour avec les polices intégrées a été enregistré dans le chemin du fichier de sortie spécifié.