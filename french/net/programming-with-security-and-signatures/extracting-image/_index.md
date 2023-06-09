---
title: Extraction d'images
linktitle: Extraction d'images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Extrayez facilement des images de documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-security-and-signatures/extracting-image/
---

Extraire des images d'un document PDF peut être utile dans de nombreux cas. Avec Aspose.PDF pour .NET, vous pouvez facilement extraire des images en utilisant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF à partir duquel vous souhaitez extraire l'image. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Étape 3 : Extraire l'image du document PDF

Nous allons maintenant extraire l'image du document PDF en utilisant le code suivant :

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

Dans cet exemple, nous parcourons chaque champ du formulaire dans le document PDF. Si un champ de signature est trouvé, nous extrayons l'image associée et l'enregistrons dans un fichier JPEG.

### Exemple de code source pour l'extraction d'images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour extraire des images d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez intégrer ce code dans vos propres projets pour extraire des images et les utiliser au besoin.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur les fonctionnalités avancées d'extraction d'images et de manipulation de documents PDF.