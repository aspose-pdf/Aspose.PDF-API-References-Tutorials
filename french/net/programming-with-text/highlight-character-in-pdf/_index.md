---
title: Mettre en surbrillance le caractère dans le PDF
linktitle: Mettre en surbrillance le caractère dans le PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à mettre en surbrillance des caractères dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 240
url: /fr/net/programming-with-text/highlight-character-in-pdf/
---

Dans ce didacticiel, nous expliquerons comment mettre en surbrillance des caractères dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer en revue le processus étape par étape de mise en surbrillance des caractères dans un PDF à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouve votre fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir`variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document PDF

 Ensuite, nous chargeons le document PDF d'entrée à l'aide de la`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Étape 3 : convertir un PDF en image

 Pour mettre en surbrillance les caractères, nous convertissons le document PDF en image à l'aide de la`PdfConverter` classe. Nous définissons la résolution pour la conversion et récupérons l'image en tant que`Bitmap` objet.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Étape 4 : Mettez en surbrillance les caractères

 Nous parcourons chaque page du document PDF et utilisons un`TextFragmentAbsorber` objet pour trouver tous les mots de la page. Nous parcourons ensuite les fragments de texte, les segments et les caractères pour les mettre en évidence à l'aide de rectangles.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Définir l'échelle et transformer
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Parcourir les pages en boucle
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Trouver tous les mots de la page
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Boucle sur des fragments de texte
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Mettre en surbrillance les caractères
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Boucle à travers les segments
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Mettre en surbrillance le segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Boucle à travers les caractères
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Caractère de surbrillance
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Étape 5 : Enregistrer l'image de sortie

Enfin, nous enregistrons l'image modifiée avec les caractères en surbrillance dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Exemple de code source pour Highlight Character In PDF en utilisant Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Créer un objet TextAbsorber pour trouver tous les mots
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Obtenir les fragments de texte extraits
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Boucle à travers les fragments
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à mettre en surbrillance des caractères dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C # fourni, vous pouvez mettre en surbrillance des caractères dans un PDF et enregistrer la sortie sous forme d'image.