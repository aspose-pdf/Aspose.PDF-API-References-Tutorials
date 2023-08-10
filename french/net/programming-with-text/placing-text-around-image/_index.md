---
title: Placer du texte autour de l'image
linktitle: Placer du texte autour de l'image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à placer du texte autour d'une image dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/programming-with-text/placing-text-around-image/
---

Dans ce didacticiel, nous expliquerons comment placer du texte autour d'une image dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons suivre le processus étape par étape de création d'un tableau, d'ajout d'une image et de positionnement du texte autour de l'image à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un document et une page

 Ensuite, nous créons un`Document` objet et ajoutez-y une page à l'aide de la`Pages.Add()` méthode.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 3 : créer un tableau

 Nous créons un tableau à l'aide de`Table` class et ajoutez-le à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Étape 4 : Définir les largeurs et les marges des colonnes du tableau

 Nous définissons la largeur des colonnes du tableau et créons un`MarginInfo` objet pour définir les marges.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Étape 5 : Ajouter une image au tableau

 Nous créons un`Image` objet, spécifiez le chemin du fichier image et définissez la hauteur et la largeur fixes de l'image. Ensuite, nous ajoutons l'image à la collection de paragraphes de la cellule du tableau.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Étape 6 : Ajouter du texte autour de l'image

Nous créons des variables de chaîne contenant du texte au format HTML et créons un`HtmlFragment` objet. Ensuite, nous ajoutons le texte HTML à la cellule du tableau contenant l'image.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Étape 7 : Ajouter du texte supplémentaire

 Nous créons un autre`HtmlFragment` objet contenant du texte supplémentaire au format HTML et ajoutez-le à une cellule de tableau distincte.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Étape 8 : Enregistrer le document PDF

Enfin, nous enregistrons le document PDF dans le fichier de sortie spécifié.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Exemple de code source pour placer du texte autour de l'image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciation d'un objet document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Créer une page dans le Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Instancier un objet table
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Ajouter le tableau dans la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(table1);
// Définir avec les largeurs de colonne du tableau
table1.ColumnWidths = "120 270";
// Créez un objet MarginInfo et définissez ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
table1.DefaultCellPadding = margin;
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Créer un objet image
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Spécifiez le chemin du fichier image
logo.File = dataDir + "aspose-logo.jpg";
// Spécifiez la hauteur fixe de l'image
logo.FixHeight = 120;
// Spécifiez la largeur fixe de l'image
logo.FixWidth = 110;
row1.Cells.Add();
// Ajouter l'image à la collection de paragraphes de la cellule du tableau
row1.Cells[0].Paragraphs.Add(logo);
//Créer des variables de chaîne avec du texte contenant des balises html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Créer un objet texte à ajouter à droite de l'image
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Ajouter les paragraphes de texte contenant du texte HTML à la cellule du tableau
row1.Cells[1].Paragraphs.Add(TitleText);
// Définissez l'alignement vertical du contenu de la ligne sur Haut
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Définissez la valeur d'étendue de ligne pour la deuxième ligne sur 2
SecondRow.Cells[0].ColSpan = 2;
// Définissez l'alignement vertical de la deuxième ligne sur Haut
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Ajouter les paragraphes de texte contenant du texte HTML à la cellule du tableau
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Enregistrez le fichier Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusion

Dans ce didacticiel, vous avez appris à placer du texte autour d'une image dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez créer un tableau, ajouter une image et positionner du texte autour de l'image dans un document PDF.