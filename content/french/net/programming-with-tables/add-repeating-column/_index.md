---
title: Ajouter une colonne répétitive dans un document PDF
linktitle: Ajouter une colonne répétitive dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une colonne répétitive dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-tables/add-repeating-column/
---
Dans ce tutoriel, nous allons apprendre à ajouter une colonne répétitive dans un document PDF en utilisant Aspose.PDF pour .NET. Nous expliquerons le code source en C# étape par étape. À la fin de ce tutoriel, vous saurez comment créer un tableau avec une colonne répétitive dans un document PDF. Commençons !

## Étape 1 : Configuration de l'environnement
Tout d’abord, assurez-vous d’avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Création du document PDF
Dans cette étape, nous créons un nouveau document PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Nous avons créé un document PDF vide dans lequel nous pouvons ajouter du contenu.

## Étape 3 : Création des tables
Dans cette étape, nous créons une table principale (`outerTable`) et un tableau imbriqué (`mytable`) qui sera répété dans la colonne.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Nous avons spécifié les propriétés du tableau telles que la largeur des colonnes et le mode de rupture du tableau imbriqué.

## Étape 4 : Ajout des tableaux au document
Nous ajoutons maintenant les tableaux créés au document PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Nous ajoutons d’abord la table principale (`outerTable`) au document PDF. Ensuite, nous ajoutons le tableau imbriqué (`mytable` ) comme paragraphe dans une cellule du tableau principal. Nous spécifions également le nombre de colonnes répétées pour`mytable` (dans cet exemple, 5 colonnes).

## Étape 5 : Ajout d'en-têtes et de lignes
Nous ajoutons maintenant les en-têtes et les lignes au tableau.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Ajoutez d'autres en-têtes ici

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Ajoutez les autres colonnes ici
}
```

Nous ajoutons d’abord les en-têtes à la première ligne du tableau (`headerRow`). Ensuite, nous ajoutons les lignes de données à partir d'une boucle. Dans cet exemple, nous ajoutons 6 lignes de données.

## Étape 6 : Enregistrer le document PDF
Enfin, nous enregistrons le document PDF dans le fichier spécifié.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Assurez-vous de spécifier le répertoire et le nom de fichier corrects pour enregistrer le fichier PDF de sortie.

### Exemple de code source pour ajouter une colonne répétitive à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Créer un nouveau document
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instancier une table externe qui occupe toute la page
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Instancier un objet de table qui sera imbriqué dans une table externe qui sera interrompue dans la même page
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Ajoutez le tableau externe aux paragraphes de la page
// Ajouter mytable à externalTable
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
	// Créez des lignes dans le tableau, puis des cellules dans les lignes
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
Dans ce didacticiel, nous avons appris à ajouter une colonne répétitive dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour créer des tableaux avec des colonnes répétitives dans vos propres projets C#.

### FAQ pour ajouter une colonne répétitive dans un document PDF

#### Q : Puis-je personnaliser le nombre de colonnes répétées dans le tableau imbriqué ?

 R : Oui, vous pouvez personnaliser le nombre de colonnes répétées dans le tableau imbriqué. Dans l'exemple fourni, nous avons défini`mytable.RepeatingColumnsCount = 5;`, ce qui signifie qu'il y aura 5 colonnes répétées. Vous pouvez modifier cette valeur en n'importe quel nombre souhaité.

#### Q : Est-il possible d’ajouter dynamiquement des lignes supplémentaires à la table imbriquée ?

R : Oui, vous pouvez ajouter dynamiquement des lignes supplémentaires à la table imbriquée de la même manière que celle indiquée dans le didacticiel. Vous pouvez utiliser des boucles ou toute autre logique pour ajouter des lignes en fonction de vos données.

#### Q : Puis-je appliquer des styles et une mise en forme au tableau et à ses cellules ?

R : Oui, vous pouvez appliquer des styles et des mises en forme au tableau et à ses cellules à l'aide d'Aspose.PDF pour .NET. La bibliothèque fournit diverses propriétés et méthodes pour personnaliser l'apparence du tableau et de son contenu.

#### Q : Aspose.PDF pour .NET est-il compatible avec .NET Core ?

R : Oui, Aspose.PDF pour .NET est compatible avec .NET Core. Vous pouvez l'utiliser à la fois dans les applications .NET Framework et .NET Core.

#### Q : Puis-je utiliser cette approche pour ajouter des colonnes répétitives dans un document PDF existant ?

R : Oui, vous pouvez utiliser cette approche pour ajouter des colonnes répétitives dans un document PDF existant. Chargez simplement le document existant à l'aide d'Aspose.PDF pour .NET et suivez les mêmes étapes pour créer et ajouter la colonne répétitive.