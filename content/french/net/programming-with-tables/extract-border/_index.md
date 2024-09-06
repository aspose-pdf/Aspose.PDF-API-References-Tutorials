---
title: Extraire la bordure dans un fichier PDF
linktitle: Extraire la bordure dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire la bordure d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-tables/extract-border/
---
Dans ce tutoriel, nous allons apprendre à extraire la bordure d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source en C# étape par étape. À la fin de ce tutoriel, vous saurez comment extraire la bordure d'un document PDF et l'enregistrer sous forme d'image. Commençons !

## Étape 1 : Configuration de l'environnement
Tout d’abord, assurez-vous d’avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Chargement du document PDF
Dans cette étape, nous chargeons le document PDF à partir du fichier spécifié.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le répertoire réel où se trouve votre fichier PDF.

## Étape 3 : Extraction des bords
Nous allons extraire la bordure du document PDF en itérant sur les opérations contenues dans le document.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Traiter toutes les opérations de contenu
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Vérifiez le type d'opération
         // ...
         // Ajoutez du code pour traiter chaque opération
     }
}
```

 Nous créons un`graphicsState` pile pour stocker les états graphiques, une image bitmap pour capturer la bordure extraite, un`GraphicsPath` objet pour stocker les chemins de dessin et d'autres variables pour suivre l'état et les couleurs.

## Étape 4 : Traitement des transactions
Dans cette étape, nous traitons chaque opération du document pour extraire la bordure.

```csharp
// Vérifiez le type d'opération
if (opSaveState != null)
{
     // Enregistrer l'état précédent et pousser l'état actuel vers le haut de la pile
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Supprimer l'état actuel et restaurer l'état précédent
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Récupérer la matrice de transformation actuelle
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Multiplier la matrice actuelle par la matrice d'état
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Mettre à jour le dernier point de dessin
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Traiter le dessin d'une ligne
     // ...
     // Ajouter du code pour gérer le dessin d'une ligne
}
// ...
// Ajouter else if blocs pour d'autres opérations
```

Nous vérifions le type d’opération à l’aide de conditions et exécutons le code approprié pour chaque opération.

## Étape 5 : Image de sauvegarde
Enfin, nous enregistrons l’image bitmap contenant la bordure extraite dans un fichier spécifié.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Assurez-vous de spécifier le répertoire et le nom de fichier corrects pour enregistrer l'image de sortie.

### Exemple de code source pour extraire la bordure à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// La valeur par défaut de la matrice CTM est 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Système. Le système de coordonnées de dessin est basé en haut à gauche, tandis que le système de coordonnées PDF est basé en bas à gauche, nous devons donc appliquer la matrice d'inversion
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Traiter toutes les commandes de contenu
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Enregistrer l'état précédent et placer l'état actuel en haut de la pile
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Jeter l'état actuel et restaurer l'état précédent
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// Multiplier la matrice actuelle par la matrice d'état
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce tutoriel, nous avons appris à extraire la bordure d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour extraire la bordure d'autres documents PDF.

### FAQ pour extraire la bordure d'un fichier PDF

#### Q : Quel est le but d’extraire la bordure d’un fichier PDF ?

R : L'extraction de la bordure d'un fichier PDF peut être utile à diverses fins. Elle permet d'isoler et d'analyser les éléments structurels du document, tels que les tableaux, les diagrammes ou les éléments graphiques. Vous pouvez utiliser la bordure extraite pour identifier la mise en page, les dimensions et le positionnement du contenu dans le document PDF.

#### Q : Puis-je extraire la bordure de pages ou de zones spécifiques du document PDF ?

 : Oui, vous pouvez modifier le code source C# fourni pour extraire la bordure de pages ou de régions spécifiques dans le document PDF. En manipulant le`doc.Pages` en collectant et en spécifiant des critères personnalisés, vous pouvez choisir d'extraire la bordure de pages ou de zones d'intérêt particulières.

#### Q : Comment puis-je personnaliser le format et la qualité de l’image de sortie ?

 R : Dans le code C# fourni, la bordure extraite est enregistrée sous forme d'image PNG. Si vous souhaitez modifier le format de l'image de sortie, vous pouvez modifier le`ImageFormat.Png` paramètre dans le`bitmap.Save` méthode vers d'autres formats d'image pris en charge, tels que JPEG, BMP ou GIF. De plus, vous pouvez ajuster la qualité de l'image ou les paramètres de compression en fonction de vos besoins.

#### Q : Quelles autres opérations puis-je effectuer sur la bordure extraite ?

: Une fois que vous avez extrait la bordure sous forme d'image, vous pouvez la traiter davantage à l'aide de bibliothèques ou d'algorithmes de traitement d'image. Vous pouvez analyser l'image, appliquer des filtres d'image, détecter des motifs ou effectuer une reconnaissance optique de caractères (OCR) pour extraire le texte de l'image si nécessaire.

#### Q : Existe-t-il des limitations ou des considérations lors de l’extraction de bordures à partir de documents PDF complexes ?

R : Le processus d'extraction peut varier en fonction de la complexité du document PDF. Les PDF complexes comportant plusieurs calques, une transparence ou des graphiques avancés peuvent nécessiter un traitement ou des ajustements supplémentaires pour extraire avec précision la bordure. Il est essentiel de tester minutieusement le processus d'extraction sur différents documents PDF pour garantir des résultats fiables.