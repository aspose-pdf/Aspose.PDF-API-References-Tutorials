---
title: Alignement du texte pour le contenu des lignes du tableau
linktitle: Alignement du texte pour le contenu des lignes du tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à aligner le contenu des lignes dans un tableau PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-tables/text-alignment-for-table-row-content/
---

Dans ce didacticiel, nous vous guiderons pas à pas pour aligner le contenu d'une ligne dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Création du document PDF
Tout d'abord, nous allons créer le document PDF :

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 2 : Initialisation de la table
Ensuite, nous allons initialiser la table :

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Étape 3 : Définir la couleur de la bordure du tableau
Nous allons configurer la couleur de la bordure du tableau :

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Étape 4 : Configurer la bordure des cellules du tableau
Nous allons configurer la bordure de cellule du tableau :

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Étape 5 : boucler pour ajouter 10 lignes au tableau
Nous allons maintenant utiliser une boucle pour ajouter 10 lignes au tableau :

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Étape 6 : configuration de l'alignement de la ligne verticale
Nous allons configurer l'alignement vertical des lignes du tableau :

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Étape 7 : Ajouter du contenu aux cellules de ligne
Nous allons ajouter du contenu aux cellules de ligne :

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Étape 8 : Ajouter le tableau à la page du document
Ajoutons maintenant le tableau à la page du document :

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Étape 9 : Enregistrer le document PDF
Enfin, nous enregistrerons le document PDF :

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Exemple de code source pour l'alignement du texte pour le contenu des lignes de tableau à l'aide de Aspose.Words pour .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Initialise une nouvelle instance de la table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définissez la couleur de la bordure du tableau sur LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// définir la bordure des cellules du tableau
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// créer une boucle pour ajouter 10 lignes
for (int row_count = 0; row_count < 10; row_count++)
{
	// ajouter une ligne au tableau
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Ajouter un objet tableau à la première page du document d'entrée
tocPage.Paragraphs.Add(table);
// Enregistrer le document mis à jour contenant l'objet tableau
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusion
Félicitation ! Vous avez maintenant appris à aligner le contenu d'une ligne dans un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment créer un document, initialiser un tableau, configurer la bordure et l'alignement, ajouter du contenu et enregistrer le document PDF. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.