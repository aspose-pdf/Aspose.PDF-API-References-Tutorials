---
title: Alignement du texte pour le contenu des lignes du tableau
linktitle: Alignement du texte pour le contenu des lignes du tableau
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment aligner le contenu des lignes dans un tableau PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-tables/text-alignment-for-table-row-content/
---
Dans ce didacticiel, nous vous guiderons étape par étape pour aligner le contenu d'une ligne dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Création du document PDF
Tout d'abord, nous allons créer le document PDF :

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 2 : initialisation de la table
Ensuite, nous initialiserons la table :

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Étape 3 : Définition de la couleur de la bordure du tableau
Nous allons configurer la couleur de la bordure du tableau :

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Étape 4 : Configuration de la bordure des cellules du tableau
Nous allons configurer la bordure des cellules du tableau :

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Étape 5 : Boucle pour ajouter 10 lignes au tableau
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

## Étape 6 : Configuration de l'alignement des lignes verticales
Nous allons configurer l'alignement vertical des lignes du tableau :

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Étape 7 : ajout de contenu aux cellules de ligne
Nous allons ajouter du contenu aux cellules de la ligne :

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Étape 8 : Ajout du tableau à la page du document
Ajoutons maintenant le tableau à la page du document :

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Étape 9 : Sauvegarde du document PDF
Enfin, nous enregistrerons le document PDF :

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Exemple de code source pour l'alignement du texte pour le contenu des lignes de tableau à l'aide d'Aspose.PDF pour .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Initialise une nouvelle instance de la Table
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
// Enregistrer le document mis à jour contenant l'objet table
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusion
Félicitation ! Vous avez maintenant appris à aligner le contenu d'une ligne dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment créer un document, initialiser un tableau, configurer la bordure et l'alignement, ajouter du contenu et enregistrer le document PDF. Vous pouvez désormais appliquer ces connaissances à vos propres projets.

### FAQ

#### Q : Comment puis-je aligner le contenu des cellules du tableau horizontalement ?

 R : Vous pouvez aligner le contenu des cellules du tableau horizontalement en définissant le`HorizontalAlign` propriété de la cellule`TextState` objet. Par exemple, pour centrer le texte, utilisez`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Vous pouvez également le définir sur`HorizontalAlignment.Left` ou`HorizontalAlignment.Right` pour l'alignement à gauche et à droite, respectivement.

#### Q : Puis-je appliquer différents styles et couleurs de bordure à des cellules individuelles du tableau ?

 R : Oui, vous pouvez appliquer différents styles et couleurs de bordure à des cellules individuelles du tableau. Pour personnaliser la bordure d'une cellule spécifique, définissez le`cell.Border` propriété à un nouveau`BorderInfo`objet avec les paramètres souhaités, tels que les côtés des bordures, la largeur et la couleur.

#### Q : Comment puis-je ajuster l’alignement vertical du contenu du tableau dans les cellules ?

 R : Vous pouvez ajuster l'alignement vertical du contenu du tableau dans les cellules en définissant le`VerticalAlignment` propriété de la ligne à`VerticalAlignment.Center`, `VerticalAlignment.Top` , ou`VerticalAlignment.Bottom`. Cette propriété contrôle l'alignement vertical de toutes les cellules de cette ligne.

#### Q : Est-il possible d’ajouter dynamiquement plus de colonnes ou de lignes au tableau ?

 R : Oui, vous pouvez ajouter dynamiquement davantage de colonnes et de lignes au tableau en utilisant l'outil`table.Rows.Add()` méthode pour ajouter de nouvelles lignes et le`row.Cells.Add()` méthode pour ajouter de nouvelles cellules aux lignes. Vous pouvez le faire dans des boucles ou en fonction de vos besoins spécifiques.

#### Q : Comment puis-je définir une couleur d’arrière-plan pour des cellules spécifiques ou pour l’ensemble du tableau ?

 R : Pour définir une couleur d'arrière-plan pour des cellules spécifiques ou pour l'ensemble du tableau, utilisez l'option`BackgroundColor` propriété du`Cell` ou`Table` objet. Par exemple, pour définir la couleur d'arrière-plan d'une cellule, utilisez`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.