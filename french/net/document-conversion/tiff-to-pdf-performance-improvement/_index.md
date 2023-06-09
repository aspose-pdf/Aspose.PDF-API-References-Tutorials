---
title: Amélioration des performances TIFF vers PDF
linktitle: Amélioration des performances TIFF vers PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour améliorer les performances de conversion TIFF en PDF avec Aspose.PDF pour .NET.
type: docs
weight: 310
url: /fr/net/document-conversion/tiff-to-pdf-performance-improvement/
---

Dans ce didacticiel, nous vous expliquerons étape par étape comment améliorer les performances de conversion des fichiers TIFF en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous détaillerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets. À la fin de ce didacticiel, vous serez en mesure d'effectuer des conversions plus rapides et plus efficaces de fichiers TIFF en PDF.

## Étape 1 : Définir le répertoire des documents
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin où vous avez enregistré vos fichiers.

## Étape 2 : Obtenir la liste des fichiers TIFF
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
Obtenir une liste des fichiers TIFF présents dans le répertoire spécifié.

## Étape 3 : instancier un objet Document
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
Créez une instance de l'objet Document.

## Étape 4 : parcourir les fichiers et les ajouter au document PDF
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 Parcourez chaque fichier TIFF, chargez-le en tant que`Bitmap` objet, puis ajoutez-le au document PDF. Des paramètres tels que les marges, la résolution et l'échelle de l'image sont également configurés.

## Étape 5 : Enregistrez le fichier PDF résultant
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
Enregistrez le document PDF résultant dans le répertoire spécifié.

### Exemple de code source pour l'amélioration des performances TIFF en PDF à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Obtenir une liste de fichiers image tiff
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// Instancier un objet Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Naviguez à travers les fichiers et eux dans le fichier pdf
foreach (string myFile in files)
{

	// Charger tous les fichiers tiff dans un tableau d'octets
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// Créer une nouvelle Page dans le document Pdf
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// Définissez les marges pour que l'image s'adapte, etc.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// Créer un objet image
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// Ajouter l'image dans la collection de paragraphes de la page
	currpage.Paragraphs.Add(image1);

	// Définissez la propriété IsBlackWhite sur true pour améliorer les performances
	image1.IsBlackWhite = true;
	// Définissez ImageStream sur un objet MemoryStream
	image1.ImageStream = mystream;
	// Définir l'échelle d'image souhaitée
	image1.ImageScale = 0.95F;
}

// Enregistrer le PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à améliorer les performances de conversion des fichiers TIFF en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant les étapes fournies, vous pourrez réaliser des conversions plus rapides et plus efficaces de fichiers TIFF en PDF. Obtenez des résultats précis et professionnels tout en optimisant les performances de votre application