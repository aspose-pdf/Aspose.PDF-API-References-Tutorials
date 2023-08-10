---
title: Marges ou remplissage
linktitle: Marges ou remplissage
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir des marges ou un remplissage dans un tableau à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-tables/margins-or-padding/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le processus d'utilisation d'Aspose.PDF pour .NET pour définir des marges ou un remplissage dans un tableau. Nous fournirons des explications et des extraits de code pour vous aider à comprendre et à implémenter cette fonctionnalité dans votre code source C#.

## Étape 1 : Configuration du document et de la page
Pour commencer, vous devez configurer le document et la page à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciez l'objet Document en appelant son constructeur vide
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 2 : Création d'un tableau
Ensuite, nous allons créer un objet table en utilisant la classe Aspose.Pdf.Table :

```csharp
// Instancier un objet table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Ajouter le tableau à la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(tab1);
```

## Étape 3 : Définition des largeurs de colonne et de la bordure de cellule par défaut
Pour définir les largeurs de colonne et la bordure de cellule par défaut du tableau, utilisez le code suivant :

```csharp
// Définir les largeurs de colonne du tableau
tab1. ColumnWidths = "50 50 50";
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Étape 4 : Définir la bordure du tableau et le rembourrage des cellules
Pour définir la bordure du tableau et le remplissage des cellules, créez un objet MarginInfo et définissez ses propriétés :

```csharp
// Créer un objet MarginInfo et définir ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
tab1. DefaultCellPadding = margin;

// Définir la bordure du tableau à l'aide d'un autre objet BorderInfo personnalisé
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Étape 5 : Ajouter des lignes et des cellules
Ajoutons maintenant des lignes et des cellules au tableau. Nous allons créer une nouvelle ligne et y ajouter des cellules :

```csharp
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Étape 6 : Ajouter du texte aux cellules
Pour ajouter du texte à une cellule, créez un objet TextFragment et ajoutez-le à la cellule souhaitée :

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Étape 7 : Enregistrer le PDF
Pour enregistrer le document PDF, utilisez le code suivant :

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Enregistrez le PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Margins Or Padding en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document en appelant son constructeur vide
Document doc = new Document();
Page page = doc.Pages.Add();
// Instancier un objet table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Ajouter le tableau dans la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(tab1);
// Définir avec les largeurs de colonne du tableau
tab1.ColumnWidths = "50 50 50";
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Définir la bordure du tableau à l'aide d'un autre objet BorderInfo personnalisé
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Créez un objet MarginInfo et définissez ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
tab1.DefaultCellPadding = margin;
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 avec une grande chaîne de texte à placer à l'intérieur de la cellule");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80 ;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Enregistrer le PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à définir des marges ou un remplissage dans un tableau à l'aide d'Aspose.PDF pour .NET. Ces connaissances vous aideront à améliorer vos capacités de formatage de documents et à rendre vos tableaux visuellement attrayants.

### FAQ

#### Q : Puis-je définir différentes marges ou marges intérieures pour des cellules individuelles d'un tableau ?

 : Oui, vous pouvez définir différentes marges ou remplissages pour des cellules individuelles dans un tableau à l'aide d'Aspose.PDF pour .NET. Dans l'exemple fourni, nous définissons le remplissage de cellule par défaut pour l'ensemble du tableau à l'aide de la`DefaultCellPadding` propriété. Pour définir un rembourrage différent pour des cellules spécifiques, vous pouvez accéder au`MarginInfo` de chaque cellule individuellement et modifier leurs marges.

#### Q : Comment puis-je modifier la couleur ou le style de la bordure du tableau ?

 R : Pour changer la couleur ou le style de la bordure du tableau, vous pouvez modifier le`Color` et`Width` propriétés de la`BorderInfo` objet. Dans l'exemple donné, nous définissons la couleur de la bordure sur noir et une largeur de 1F (un point) en utilisant`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Vous pouvez ajuster la couleur et la largeur selon vos besoins.

#### Q : Est-il possible d'ajouter des en-têtes ou des pieds de page au tableau ?

R : Oui, vous pouvez ajouter des en-têtes ou des pieds de page au tableau à l'aide d'Aspose.PDF pour .NET. Les en-têtes et les pieds de page sont généralement des lignes séparées qui contiennent des informations supplémentaires telles que des étiquettes de colonne, des titres de table ou des données récapitulatives. Vous pouvez créer des lignes supplémentaires, les styliser différemment et les ajouter au-dessus ou au-dessous du contenu du tableau.

#### Q : Comment ajuster l'alignement du texte dans une cellule de tableau ?

 R : Pour ajuster l'alignement du texte dans une cellule de tableau, vous pouvez utiliser le`HorizontalAlignment` et`VerticalAlignment` propriétés de la`TextFragment` objet. Par exemple, pour centrer le texte horizontalement, vous pouvez définir`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . De même, vous pouvez définir`mytext.VerticalAlignment` pour contrôler l'alignement vertical.

#### Q : Puis-je ajouter des images aux cellules du tableau au lieu de texte ?

 R : Oui, vous pouvez ajouter des images aux cellules du tableau à l'aide d'Aspose.PDF pour .NET. Au lieu de créer un`TextFragment` objet, vous pouvez créer un`Image` objet, chargez le fichier image et ajoutez-le à la cellule souhaitée à l'aide de la`cell.Paragraphs.Add(image);` méthode. Cela vous permet d'insérer des images dans le tableau à côté du contenu textuel.