---
title: Exporter les données de la feuille de calcul Excel vers le tableau
linktitle: Exporter les données de la feuille de calcul Excel vers le tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Exportez les données d'une feuille Excel vers un tableau PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

Dans ce didacticiel, nous allons apprendre à exporter des données à partir d'une feuille de calcul Excel et à créer un tableau dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons parcourir le code source étape par étape et expliquer chaque section en détail. À la fin de ce didacticiel, vous serez en mesure de générer des fichiers PDF avec des tableaux contenant des données à partir de feuilles de calcul Excel. Commençons!

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#
- Visual Studio installé sur votre machine
- Bibliothèque Aspose.PDF pour .NET ajoutée à votre projet

## Étape 1 : Configuration de l'environnement
Pour commencer, créez un nouveau projet C# dans Visual Studio. Ajoutez la référence à la bibliothèque Aspose.PDF pour .NET en cliquant avec le bouton droit sur votre projet dans l'explorateur de solutions, en sélectionnant « Gérer les packages NuGet » et en recherchant « Aspose.PDF ». Installez le package et vous êtes prêt à partir.

## Étape 2 : Chargement de la feuille de calcul Excel
Dans la première étape de notre code, nous définissons le chemin vers le répertoire contenant le document Excel. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre fichier Excel.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Ici, nous utilisons la bibliothèque Aspose.Cells pour charger le classeur Excel. Assurez-vous de remplacer "newBook1.xlsx" par le nom de votre fichier Excel.

## Étape 3 : Accéder à la feuille de calcul
 Ensuite, nous devons accéder à la première feuille de calcul du fichier Excel. Nous le faisons en utilisant le`Worksheets` collecte de la`Workbook` objet.

```csharp
// Accéder à la première feuille de calcul du fichier Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Si votre fichier Excel contient plusieurs feuilles de calcul, vous pouvez modifier la valeur d'index`[0]` pour accéder à une autre feuille de calcul.

## Étape 4 : Exporter des données vers DataTable
 Maintenant, nous allons exporter le contenu de la feuille de calcul Excel vers un`DataTable` objet. Nous spécifions la plage de cellules à exporter à l'aide de la`ExportDataTable` méthode.

```csharp
// Exportation du contenu de 7 lignes et 2 colonnes à partir de la 1ère cellule vers DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Dans cet exemple, nous exportons toutes les lignes et colonnes à partir de la première cellule (0, 0) vers la dernière cellule de la feuille de calcul. Définissez la plage appropriée en fonction de vos besoins.

## Étape 5 : Création d'un document PDF
Maintenant, nous allons créer un nouveau document PDF en utilisant la bibliothèque Aspose.PDF.

```csharp
//Instancier une instance Document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Cela crée un document PDF vide où nous pouvons ajouter du contenu.

## Étape 6 : Ajouter une page et un tableau
Pour afficher les données sous forme de tableau, nous devons ajouter une page et un tableau au document PDF.

```csharp
// Créer une page dans l'instance de document
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Créer un objet Tableau
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter l'objet Table dans la collection de paragraphes de la section
sec1.Paragraphs.Add(tab1);
```

Ici, nous créons une nouvelle page et un objet table. Nous ajoutons ensuite le tableau à la collection de paragraphes de la page.

## Étape 7 : Définir les propriétés du tableau
Avant d'importer les données, nous devons définir certaines propriétés du tableau, telles que la largeur des colonnes et les bordures de cellule par défaut.

```csharp
// Définir la largeur des colonnes du tableau
tab1.ColumnWidths = "40 100 100";

// Définir la bordure de cellule par défaut du tableau à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Dans cet exemple, nous avons défini les largeurs de colonne sur 40, 100 et 100 unités. Ajustez les valeurs en fonction de vos données. Nous définissons également la bordure de cellule par défaut pour afficher les bordures sur tous les côtés de chaque cellule.

## Étape 8 : Importer des données dans la table
Maintenant, nous allons importer les données du`DataTable` objet dans le tableau à l'aide de la`ImportDataTable` méthode.

```csharp
// Importer des données dans l'objet Table à partir du DataTable créé ci-dessus
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Ici, nous spécifions la plage de lignes et de colonnes à importer. Dans cet exemple, nous importons toutes les lignes et colonnes du`dataTable` objet.

## Étape 9 : Formater le tableau
Pour améliorer l'apparence du tableau, nous pouvons appliquer une mise en forme à des cellules ou des lignes spécifiques. Dans cette étape, nous allons formater la première ligne et les autres lignes du tableau.

```csharp
// Obtenir la 1ère ligne du tableau
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formater la première ligne
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Définir la couleur d'arrière-plan des cellules de la première ligne
     curCell.BackgroundColor = Color.Blue;// Définir le visage des cellules de la première rangée
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Définir la couleur de la police des cellules de la première ligne
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Définir l'alignement du texte pour les cellules de la première ligne
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Format de ligne alternatif
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Définir la couleur d'arrière-plan des cellules dans des rangées alternées
         curCell.BackgroundColor = Color.Gray;
        
         // Définir la couleur du texte des cellules dans des rangées alternées
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Ici, nous parcourons les cellules de la première ligne et définissons leur couleur d'arrière-plan, leur police, leur couleur de police et l'alignement du texte. Ensuite, nous parcourons toutes les cellules des lignes alternées et définissons leur couleur d'arrière-plan et de texte.

## Étape 10 : Enregistrer le document PDF
Enfin, nous enregistrons le document PDF à l'emplacement spécifié.

```csharp
// Enregistrez le PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès au répertoire et le nom de fichier souhaités pour le fichier PDF de sortie.

### Exemple de code source pour exporter des données de feuille de calcul Excel vers une table à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Accéder à la première feuille de calcul du fichier Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportation du contenu de 7 lignes et 2 colonnes à partir de la 1ère cellule vers DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instancier une instance de document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Créer une page dans l'instance de document
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Créer un objet Tableau
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter l'objet Table dans la collection de paragraphes de la section
sec1.Paragraphs.Add(tab1);

// Définissez les largeurs de colonne du tableau. Nous devons spécifier le ColumnCount manuellement.
// Comme la feuille de calcul Excel actuelle a trois colonnes, nous spécifions donc le même nombre
tab1.ColumnWidths = "40 100 100";

// Définir la bordure de cellule par défaut du tableau à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importer des données dans l'objet Table à partir du DataTable créé ci-dessus
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Obtenir la 1ère ligne du tableau
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Parcourez toutes les cellules de la 1ère ligne et définissez leur couleur d'arrière-plan sur bleu
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Définissez l'arrière-plan de toutes les cellules de la 1ère ligne du tableau.
	curCell.BackgroundColor = Color.Blue;
	// Définissez la police pour les cellules de la 1ère ligne du tableau.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//Définissez la couleur de police de toutes les cellules de la 1ère ligne du tableau.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Définissez l'alignement du texte pour les cellules de la 1ère ligne sur Centre.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Parcourez toutes les cellules de la 1ère ligne et définissez leur couleur d'arrière-plan sur bleu
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Définissez la couleur d'arrière-plan de toutes les cellules à l'exception de la 1ère ligne.
		curCell.BackgroundColor = Color.Gray;
		// Définissez la couleur du texte de toutes les cellules sauf la 1ère ligne.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Enregistrer le PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à exporter des données d'une feuille de calcul Excel vers un tableau PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons couvert le processus étape par étape de chargement de la feuille de calcul Excel, de création d'un document PDF, d'ajout d'un tableau, d'importation de données et de formatage du tableau. Vous pouvez désormais générer des fichiers PDF avec des tableaux contenant des données Excel par programmation.