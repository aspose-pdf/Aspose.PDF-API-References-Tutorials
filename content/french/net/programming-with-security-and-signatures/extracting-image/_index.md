---
title: Extraction d'une image
linktitle: Extraction d'une image
second_title: Aspose.PDF pour la référence de l'API .NET
description: Extrayez facilement des images de documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-security-and-signatures/extracting-image/
---
Extraire des images d'un document PDF peut être utile dans de nombreux cas. Avec Aspose.PDF pour .NET, vous pouvez facilement extraire des images à l'aide du code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF à partir duquel vous souhaitez extraire l'image. Remplacer`"YOUR DOCUMENTS DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Étape 3 : Extraire l'image du document PDF

Nous allons maintenant extraire l'image du document PDF en utilisant le code suivant :

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

Dans cet exemple, nous parcourons chaque champ du formulaire dans le document PDF. Si un champ de signature est trouvé, nous extrayons l'image associée et la sauvegardons dans un fichier JPEG.

### Exemple de code source pour l'extraction d'une image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
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

Félicitation ! Vous disposez désormais d'un guide étape par étape pour extraire des images d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez intégrer ce code dans vos propres projets pour extraire des images et les utiliser selon vos besoins.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur les fonctionnalités avancées d'extraction d'images et de manipulation de documents PDF.


### FAQ

#### Q : Aspose.PDF pour .NET convient-il aux débutants ?

R : Bien qu'une certaine familiarité avec la programmation C# soit utile, notre didacticiel est conçu pour être convivial pour les débutants et vous guider à travers chaque étape.

#### Q : Puis-je extraire plusieurs images à la fois ?

R : Absolument ! En implémentant des boucles et en adaptant le code fourni, vous pouvez extraire plusieurs images d'un seul document PDF.

#### Q : Aspose.PDF pour .NET est-il la seule solution pour l'extraction d'images ?

R : Bien qu'il existe d'autres outils disponibles, Aspose.PDF pour .NET est réputé pour son efficacité et ses fonctionnalités complètes.

#### Q : Puis-je utiliser les images extraites à des fins commerciales ?

R : Oui, une fois extraites, vous pouvez utiliser les images selon vos besoins, y compris pour des projets commerciaux.

#### Q : Où puis-je trouver plus de ressources sur la manipulation de PDF avec Aspose.PDF ?

R : Consultez notre documentation officielle pour découvrir une multitude de ressources et d'informations sur la manipulation avancée de PDF avec Aspose.PDF pour .NET.