---
title: Ajouter une colonne extensible
linktitle: Ajouter une colonne extensible
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une colonne extensible dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-tables/add-repeating-column/
---

Dans ce didacticiel, nous allons apprendre à ajouter une colonne extensible dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons pas à pas le code source en C#. A la fin de ce tutoriel, vous saurez comment créer un tableau avec une colonne extensible dans un document PDF. Commençons!

## Étape 1 : Configurer l'environnement
Tout d'abord, assurez-vous d'avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Création du document PDF
Dans cette étape, nous créons un nouveau document PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Nous avons créé un document PDF vide où nous pouvons ajouter du contenu.

## Etape 3 : Création des tableaux
Dans cette étape, nous créons une table principale (`outerTable`) et une table imbriquée (`mytable`) qui sera répété dans la colonne.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Nous avons spécifié des propriétés de table telles que la largeur de colonne et le mode de saut de table imbriqué.

## Étape 4 : Ajouter les tableaux au document
Nous ajoutons maintenant les tableaux créés au document PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Nous ajoutons d'abord la table principale (`outerTable`au document PDF. Ensuite, nous ajoutons la table imbriquée (`mytable` ) sous forme de paragraphe dans une cellule du tableau principal. Nous spécifions également le nombre de colonnes répétées pour`mytable` (dans cet exemple, 5 colonnes).

## Étape 5 : Ajouter des en-têtes et des lignes
Nous ajoutons maintenant les en-têtes et les lignes au tableau.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Ajouter d'autres en-têtes ici

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Ajouter les autres colonnes ici
}
```

Nous ajoutons d'abord les en-têtes à la première ligne du tableau (`headerRow`). Ensuite, nous ajoutons les lignes de données d'une boucle. Dans cet exemple, nous ajoutons 6 lignes de données.

## Étape 6 : Enregistrer le document PDF
Enfin, nous enregistrons le document PDF dans le fichier spécifié.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Assurez-vous de spécifier le répertoire et le nom de fichier corrects pour enregistrer le fichier PDF de sortie.

### Exemple de code source pour ajouter une colonne répétitive à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Créer un nouveau document
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instancier une table externe qui occupe toute la page
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Instanciez un objet table qui sera imbriqué dans outerTable qui se cassera à l'intérieur de la même page
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Ajouter l'outerTable aux paragraphes de la page
//Ajouter mytable à outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Ajouter une ligne d'en-tête
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Créer des lignes dans le tableau, puis des cellules dans les lignes
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Conclusion
Dans ce didacticiel, nous avons appris à ajouter une colonne extensible dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour créer des tables avec des colonnes répétitives dans vos propres projets C#.