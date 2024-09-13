---
title: Mettre en surbrillance un caractère dans un fichier PDF
linktitle: Mettre en surbrillance un caractère dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment mettre en évidence des caractères dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 240
url: /fr/net/programming-with-text/highlight-character-in-pdf/
---
Dans ce tutoriel, nous allons expliquer comment mettre en évidence des caractères dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons suivre le processus étape par étape de mise en évidence de caractères dans un fichier PDF à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous de disposer des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouve votre fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document PDF

 Ensuite, nous chargeons le document PDF d’entrée à l’aide de la`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Étape 3 : Convertir un PDF en image

 Pour mettre en évidence les caractères, nous convertissons le document PDF en image à l'aide de la`PdfConverter` classe. Nous définissons la résolution pour la conversion et récupérons l'image sous forme de`Bitmap` objet.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Étape 4 : Surligner les caractères

 Nous parcourons chaque page du document PDF et utilisons un`TextFragmentAbsorber` objet pour trouver tous les mots de la page. Nous parcourons ensuite les fragments de texte, les segments et les caractères pour les mettre en évidence à l'aide de rectangles.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Définir l'échelle et transformer
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Parcourir les pages
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Trouver tous les mots de la page
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Parcourir des fragments de texte
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Mettre en évidence les personnages
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Boucle à travers les segments
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Segment en surbrillance
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Boucle à travers les caractères
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Mettre en évidence le personnage
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

## Étape 5 : Enregistrer l’image de sortie

Enfin, nous enregistrons l’image modifiée avec les caractères en surbrillance dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Exemple de code source pour mettre en surbrillance un caractère dans un PDF à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin vers le répertoire des documents.
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à mettre en surbrillance des caractères dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez mettre en surbrillance des caractères dans un PDF et enregistrer la sortie sous forme d'image.

### FAQ

#### Q : Quel est le but du didacticiel « Mettre en surbrillance un caractère dans un fichier PDF » ?

R : Le didacticiel « Mettre en surbrillance des caractères dans un fichier PDF » explique comment utiliser la bibliothèque Aspose.PDF pour .NET pour mettre en surbrillance des caractères dans un document PDF. Le didacticiel fournit un guide étape par étape et un code source C# pour y parvenir.

#### Q : Pourquoi voudrais-je mettre en évidence des caractères dans un document PDF ?

R : La mise en évidence de caractères dans un document PDF peut être utile à diverses fins, par exemple pour mettre en valeur un contenu spécifique ou rendre certains textes plus visibles et plus distincts.

#### Q : Comment configurer le répertoire de documents ?

A : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire où se trouve votre fichier PDF d'entrée.

#### Q : Comment charger le document PDF et le convertir en image ?

 A : Dans le tutoriel, le`Aspose.Pdf.Document` La classe est utilisée pour charger le document PDF d'entrée. Ensuite, la`PdfConverter` La classe est utilisée pour convertir le document PDF en image. La résolution de l'image est définie et l'image est récupérée sous forme de fichier`Bitmap` objet.

#### Q : Comment mettre en évidence des caractères dans l’image d’un document PDF ?

 : Le didacticiel vous guide tout au long du processus de lecture de chaque page du document PDF, en recherchant des mots à l'aide d'un`TextFragmentAbsorber`et en parcourant des fragments de texte, des segments et des caractères pour les mettre en évidence à l'aide de rectangles.

#### Q : Puis-je personnaliser l’apparence des caractères et des segments mis en surbrillance ?

R : Oui, vous pouvez personnaliser l’apparence des caractères et des segments mis en surbrillance en modifiant les couleurs et les styles utilisés dans les opérations de dessin.

#### Q : Comment puis-je enregistrer l’image modifiée avec les caractères en surbrillance ?

 A : Le didacticiel montre comment enregistrer l'image modifiée avec les caractères en surbrillance dans le fichier de sortie spécifié à l'aide de`Save` méthode de la`Bitmap` classe.

#### Q : Une licence Aspose valide est-elle requise pour ce tutoriel ?

R : Oui, une licence Aspose valide est requise pour que ce tutoriel fonctionne correctement. Vous pouvez acheter une licence complète ou obtenir une licence temporaire de 30 jours sur le site Web d'Aspose.