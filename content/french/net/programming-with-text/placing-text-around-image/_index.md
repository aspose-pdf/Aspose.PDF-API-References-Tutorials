---
title: Placer du texte autour d'une image dans un fichier PDF
linktitle: Placer du texte autour d'une image dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment placer du texte autour d'une image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/programming-with-text/placing-text-around-image/
---
Dans ce tutoriel, nous allons expliquer comment placer du texte autour d'une image dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons suivre le processus étape par étape de création d'un tableau, d'ajout d'une image et de positionnement du texte autour de l'image à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous de disposer des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers votre répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et une page

 Ensuite, nous créons un`Document` objet et ajoutez-lui une page en utilisant le`Pages.Add()` méthode.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 3 : Créer un tableau

 Nous créons une table en utilisant le`Table` classe et l'ajouter à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Étape 4 : définir les largeurs et les marges des colonnes du tableau

 Nous définissons les largeurs des colonnes du tableau et créons un`MarginInfo` objet pour définir les marges.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Étape 5 : Ajouter une image au tableau

 Nous créons un`Image` objet, spécifiez le chemin du fichier image et définissez la hauteur et la largeur fixes de l'image. Ensuite, nous ajoutons l'image à la collection de paragraphes de la cellule du tableau.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Étape 6 : ajouter du texte autour de l’image

 Nous créons des variables de chaîne contenant du texte au format HTML et créons un`HtmlFragment`objet. Ensuite, nous ajoutons le texte HTML à la cellule du tableau contenant l'image.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Étape 7 : ajouter du texte supplémentaire

 Nous créons un autre`HtmlFragment` objet contenant du texte au format HTML supplémentaire et l'ajouter à une cellule de tableau distincte.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Étape 8 : Enregistrez le document PDF

Enfin, nous enregistrons le document PDF dans le fichier de sortie spécifié.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Exemple de code source pour le placement de texte autour d'une image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier un objet document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Créer une page dans le PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Instancier un objet de table
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Ajoutez le tableau dans la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(table1);
// Définir avec les largeurs de colonnes du tableau
table1.ColumnWidths = "120 270";
// Créez un objet MarginInfo et définissez ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
table1.DefaultCellPadding = margin;
// Créez des lignes dans le tableau, puis des cellules dans les lignes
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
// Ajoutez l'image à la collection de paragraphes de la cellule du tableau
row1.Cells[0].Paragraphs.Add(logo);
// Créer des variables de chaîne avec du texte contenant des balises HTML
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Créer un objet texte à ajouter à droite de l'image
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Ajoutez les paragraphes de texte contenant du texte HTML à la cellule du tableau
row1.Cells[1].Paragraphs.Add(TitleText);
// Définir l'alignement vertical du contenu de la ligne sur Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Créez des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Définissez la valeur de l'étendue de ligne pour la deuxième ligne sur 2
SecondRow.Cells[0].ColSpan = 2;
// Définir l'alignement vertical de la deuxième ligne comme Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Ajoutez les paragraphes de texte contenant du texte HTML à la cellule du tableau
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Enregistrer le fichier PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusion

Dans ce didacticiel, vous avez appris à placer du texte autour d'une image dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez créer un tableau, ajouter une image et positionner du texte autour de l'image dans un document PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Placer du texte autour d'une image dans un fichier PDF » ?

R : Le didacticiel « Placer du texte autour d'une image dans un fichier PDF » montre comment utiliser la bibliothèque Aspose.PDF pour .NET pour placer du texte autour d'une image dans un document PDF. Le didacticiel fournit un guide étape par étape et un code source C# pour vous aider à créer un tableau, ajouter une image et positionner du texte autour de l'image.

#### Q : Pourquoi voudrais-je placer du texte autour d’une image dans un document PDF ?

R : Placer du texte autour d'une image améliore la présentation visuelle de vos documents PDF, les rendant plus attrayants et informatifs. Cette technique est souvent utilisée dans les documents, brochures, rapports et autres supports où vous souhaitez combiner des images et du texte de manière esthétique.

#### Q : Comment configurer le répertoire de documents ?

A : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers le répertoire où vous souhaitez enregistrer le fichier PDF généré.

#### Q : Comment créer un tableau et y ajouter une image ?

 R : Le didacticiel vous guide tout au long du processus de création d'un tableau à l'aide de`Table` classe et ajout d'une image au tableau à l'aide de la`Image` classe. Vous spécifierez le chemin d'accès, la hauteur et la largeur du fichier image avant de l'ajouter à une cellule du tableau.

#### Q : Comment positionner le texte autour de l’image ?

 A : Pour positionner le texte autour de l'image, vous allez créer un texte au format HTML à l'aide de`HtmlFragment` classe. Ce texte contiendra à la fois un titre et un corps de texte. Vous ajouterez ensuite ce texte HTML à une cellule de tableau adjacente à la cellule d'image.

#### Q : Puis-je personnaliser l’apparence du texte et de l’image ?

: Oui, vous pouvez personnaliser l'apparence du texte et de l'image à l'aide de balises et de propriétés HTML. Par exemple, vous pouvez définir les tailles de police, les couleurs, les styles et l'alignement du texte. De plus, vous pouvez ajuster la taille et les dimensions de l'image.

#### Q : Comment enregistrer le document PDF ?

 R : Après avoir ajouté l'image et le texte au tableau, vous pouvez enregistrer le document PDF à l'aide de l'`Save` méthode de la`Document` classe. Fournissez le chemin du fichier de sortie souhaité comme argument à la`Save` méthode.

#### Q : Quel est le résultat attendu de ce tutoriel ?

R : En suivant le didacticiel et en exécutant le code C# fourni, vous générerez un document PDF qui montre comment placer du texte autour d'une image. Le document de sortie contiendra un tableau avec une image et du texte positionné autour.

#### Q : Puis-je utiliser d’autres formats d’image que JPG ?

 R : Oui, vous pouvez utiliser différents formats d'image pris en charge par la bibliothèque Aspose.PDF, tels que PNG, BMP, GIF, etc. Lors de la création du`Image` objet, spécifiez le chemin du fichier du format d'image souhaité.

#### Q : Une licence Aspose valide est-elle requise pour ce tutoriel ?

R : Oui, une licence Aspose valide est requise pour que ce tutoriel fonctionne correctement. Vous pouvez acheter une licence complète ou obtenir une licence temporaire de 30 jours sur le site Web d'Aspose.