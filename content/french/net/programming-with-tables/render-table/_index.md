---
title: Tableau de rendu dans un document PDF
linktitle: Tableau de rendu dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment afficher un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 170
url: /fr/net/programming-with-tables/render-table/
---
Dans ce tutoriel, nous vous guiderons étape par étape pour afficher un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Création du document
Tout d’abord, nous allons créer un nouveau document PDF :

```csharp
// Chemin vers le répertoire des documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouveau document
Document doc = new Document();
```

## Étape 2 : Configuration des marges et de l'orientation de la page
Ensuite, nous allons configurer les marges de la page et définir l’orientation en mode paysage :

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Étape 3 : Création du tableau et des colonnes
Créons maintenant un tableau et définissons la largeur des colonnes :

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Étape 4 : ajouter des lignes et des cellules au tableau
Ensuite, nous allons ajouter des lignes et des cellules au tableau à l’aide d’une boucle :

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Étape 5 : Ajout du tableau à la page
Ajoutons maintenant le tableau à la page du document :

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Étape 6 : Affichage du tableau sur une nouvelle page
Ensuite, nous allons créer une nouvelle table et définir la propriété « IsInNewPage » sur « true » pour afficher la table sur une nouvelle page :

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Étape 7 : Enregistrer le PDF
Enfin, nous sauvegardons le document PDF :

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Exemple de code source pour Render Table à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Page ajoutée.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Je veux garder le tableau 1 jusqu'à la page suivante s'il vous plaît...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusion
Félicitations ! Vous savez maintenant comment afficher un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment créer un document, configurer les marges et l'orientation des pages, ajouter un tableau et afficher un tableau sur une nouvelle page. Vous pouvez désormais appliquer ces connaissances à vos propres projets.

### FAQ sur le rendu du tableau dans un document PDF

#### Q : Comment puis-je modifier l’apparence du tableau, par exemple en changeant les couleurs des cellules ou en ajoutant des bordures ?

 : Pour modifier l'apparence du tableau, vous pouvez définir différentes propriétés du`Aspose.Pdf.Table` et ses cellules. Par exemple, vous pouvez définir le`BackgroundColor` propriété des cellules pour modifier leur couleur d'arrière-plan. Vous pouvez également définir la`Border` propriété du tableau ou des cellules individuelles pour ajouter des bordures. De plus, vous pouvez personnaliser la police, la couleur du texte et l'alignement du contenu du tableau en modifiant la`TextState` de la`TextFragment` objets ajoutés aux cellules.

#### Q : Puis-je ajouter des en-têtes ou des pieds de page au tableau ?

R : Oui, vous pouvez ajouter des en-têtes ou des pieds de page au tableau en créant des lignes supplémentaires au début ou à la fin du tableau et en définissant le contenu approprié dans les cellules. Vous pouvez personnaliser les en-têtes ou les pieds de page indépendamment du reste du contenu du tableau en ajoutant des styles ou du contenu différents à ces lignes spécifiques.

#### Q : Comment puis-je contrôler la position du tableau sur la page ?

 A : Pour contrôler la position du tableau sur la page, vous pouvez ajuster le`MarginInfo` de la`PageInfo` objet. Le`MarginInfo`vous permet de définir les marges gauche, droite, supérieure et inférieure de la page, ce qui affecte l'espace disponible pour le tableau. Vous pouvez également utiliser l'`PositioningType` propriété de la`Aspose.Pdf.Table` pour contrôler son alignement horizontal et vertical dans la zone de contenu de la page.

#### Q : Puis-je exporter le tableau vers différents formats de fichiers, tels qu'Excel ou CSV ?

R : Aspose.PDF pour .NET est principalement conçu pour travailler avec des documents PDF. Bien qu'il puisse exporter le document PDF sous forme d'image ou de XPS, il ne prend pas directement en charge l'exportation de tableaux vers des formats tels qu'Excel ou CSV. Pour exporter les données du tableau vers différents formats de fichier, vous devrez peut-être utiliser des bibliothèques ou des méthodes supplémentaires pour convertir le contenu PDF au format souhaité.

#### Q : Comment puis-je ajouter des hyperliens aux cellules du tableau ?

 A : Pour ajouter des hyperliens aux cellules du tableau, vous pouvez utiliser le`Aspose.Pdf.WebHyperlink` classe pour créer un lien hypertexte, puis l'ajouter comme ancre au`TextFragment`à l'intérieur de la cellule. Cela vous permet d'associer une URL ou une cible de lien à un texte ou à un contenu spécifique dans la cellule, créant ainsi des hyperliens cliquables.