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
Ensuite, nous allons créer un objet table en utilisant la classe Aspose.Pdf.Table :

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