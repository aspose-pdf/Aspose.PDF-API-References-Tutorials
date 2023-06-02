---
title: Insérer un saut de page
linktitle: Insérer un saut de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à insérer un saut de page dans un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-tables/insert-page-break/
---

Dans ce tutoriel, nous allons apprendre à insérer un saut de page dans un document PDF en utilisant Aspose.PDF pour .NET. Nous expliquerons pas à pas le code source en C#. A la fin de ce tutoriel, vous saurez comment ajouter un saut de page après un certain nombre de lignes dans un tableau d'un document PDF. Commençons!

## Étape 1 : Configurer l'environnement
Assurez-vous d'avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : création du document et du tableau
Nous créons une nouvelle instance Document et ajoutons une page à ce document. Ensuite, nous créons une instance Table pour représenter notre table dans le document PDF. Nous définissons également les styles de bordure pour le tableau.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Étape 3 : Ajouter des lignes au tableau
Nous utilisons une boucle pour ajouter 200 lignes au tableau. Pour chaque ligne, nous créons une instance de Row et ajoutons deux cellules avec du contenu textuel.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Lorsque 10 lignes sont ajoutées, nous insérons un nouveau saut de page
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Étape 4 : Ajouter le tableau au document
Nous ajoutons le tableau à la collection de paragraphes de la page du document.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Étape 5 : Enregistrez le document
Nous enregistrons le document PDF avec le saut de page inséré.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Exemple de code source pour Insérer un saut de page en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
doc.Pages.Add();
// Créer une instance de table
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Définir le style de bordure du tableau
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Définir le style de bordure par défaut pour le tableau avec une couleur de bordure rouge
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Spécifiez la largeur des colonnes du tableau
tab.ColumnWidths = "100 100";
// Créer une boucle pour ajouter 200 lignes pour le tableau
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Lorsque 10 lignes sont ajoutées, afficher la nouvelle ligne dans une nouvelle page
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Ajouter un tableau à la collection de paragraphes du fichier PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Enregistrez le document PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons appris à insérer un saut de page dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour ajouter un saut de page après un certain nombre de lignes dans un tableau dans un document PDF à l'aide de C#.