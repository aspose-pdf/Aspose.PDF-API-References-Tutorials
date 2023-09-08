---
title: Exporter les données d'une feuille de calcul Excel vers un tableau
linktitle: Exporter les données d'une feuille de calcul Excel vers un tableau
second_title: Aspose.PDF pour la référence de l'API .NET
description: Exportez des données d'une feuille Excel vers un tableau PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Dans ce didacticiel, nous apprendrons comment exporter des données à partir d'une feuille de calcul Excel et créer un tableau dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons parcourir le code source étape par étape et expliquer chaque section en détail. À la fin de ce didacticiel, vous serez en mesure de générer des fichiers PDF avec des tableaux contenant des données provenant de feuilles de calcul Excel. Commençons!

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Connaissance de base du langage de programmation C#
- Visual Studio installé sur votre machine
- Bibliothèque Aspose.PDF pour .NET ajoutée à votre projet

## Étape 1 : Configuration de l'environnement
Pour commencer, créez un nouveau projet C# dans Visual Studio. Ajoutez la référence à la bibliothèque Aspose.PDF pour .NET en cliquant avec le bouton droit sur votre projet dans l'Explorateur de solutions, en sélectionnant « Gérer les packages NuGet » et en recherchant « Aspose.PDF ». Installez le package et vous êtes prêt à partir.

## Étape 2 : chargement de la feuille de calcul Excel
Dans la première étape de notre code, nous définissons le chemin d'accès au répertoire contenant le document Excel. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin du répertoire réel où se trouve votre fichier Excel.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Ici, nous utilisons la bibliothèque Aspose.Cells pour charger le classeur Excel. Assurez-vous de remplacer « newBook1.xlsx » par le nom de votre fichier Excel.

## Étape 3 : Accéder à la feuille de calcul
 Ensuite, nous devons accéder à la première feuille de calcul du fichier Excel. Nous faisons cela en utilisant le`Worksheets` collecte des`Workbook` objet.

```csharp
// Accéder à la première feuille de calcul du fichier Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Si votre fichier Excel contient plusieurs feuilles de calcul, vous pouvez modifier la valeur de l'index`[0]` pour accéder à une autre feuille de calcul.

## Étape 4 : Exporter des données vers DataTable
 Maintenant, nous allons exporter le contenu de la feuille de calcul Excel vers un`DataTable` objet. Nous spécifions la plage de cellules à exporter à l'aide du`ExportDataTable` méthode.

```csharp
// Exportation du contenu de 7 lignes et 2 colonnes à partir de la 1ère cellule vers DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Dans cet exemple, nous exportons toutes les lignes et colonnes en commençant par la première cellule (0, 0) jusqu'à la dernière cellule de la feuille de calcul. Définissez la plage appropriée en fonction de vos besoins.

## Étape 5 : Création d'un document PDF
Nous allons maintenant créer un nouveau document PDF à l'aide de la bibliothèque Aspose.PDF.

```csharp
// Instancier une instance de document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Cela crée un document PDF vide dans lequel nous pouvons ajouter du contenu.

## Étape 6 : Ajout d'une page et d'un tableau
Pour afficher les données sous forme de tableau, nous devons ajouter une page et un tableau au document PDF.

```csharp
// Créer une page dans l'instance de document
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Créer un objet Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter l'objet Table dans la collection paragraphes de la section
sec1.Paragraphs.Add(tab1);
```

Ici, nous créons une nouvelle page et un objet table. Nous ajoutons ensuite le tableau à la collection de paragraphes de la page.

## Étape 7 : Définition des propriétés du tableau
Avant d'importer les données, nous devons définir certaines propriétés du tableau, telles que la largeur des colonnes et les bordures de cellules par défaut.

```csharp
// Définir les largeurs de colonnes du tableau
tab1.ColumnWidths = "40 100 100";

// Définir la bordure de cellule par défaut du tableau à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Dans cet exemple, nous définissons les largeurs de colonnes sur 40, 100 et 100 unités. Ajustez les valeurs en fonction de vos données. Nous définissons également la bordure de cellule par défaut pour afficher les bordures de tous les côtés de chaque cellule.

## Étape 8 : Importation de données dans la table
 Maintenant, nous allons importer les données du`DataTable` objet dans le tableau en utilisant le`ImportDataTable` méthode.

```csharp
// Importer des données dans l'objet Table à partir du DataTable créé ci-dessus
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Ici, nous spécifions la plage de lignes et de colonnes à importer. Dans cet exemple, nous importons toutes les lignes et colonnes du`dataTable` objet.

## Étape 9 : Formatage du tableau
Pour améliorer l'apparence du tableau, nous pouvons appliquer une mise en forme à des cellules ou des lignes spécifiques. Dans cette étape, nous formaterons la première ligne et les lignes alternées du tableau.

```csharp
// Récupère la 1ère ligne du tableau
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formater la première ligne
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Définir la couleur d'arrière-plan des cellules de la première ligne
     curCell.BackgroundColor = Color.Blue;// Définir le visage des cellules de la première ligne
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Définir la couleur de police des cellules de la première ligne
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Définir l'alignement du texte pour les cellules de la première ligne
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Format de ligne alternatif
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Définir la couleur d'arrière-plan des cellules dans des lignes alternées
         curCell.BackgroundColor = Color.Gray;
        
         // Définir la couleur du texte des cellules dans des lignes alternées
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Ici, nous parcourons les cellules de la première ligne et définissons leur couleur d'arrière-plan, leur police, leur couleur et l'alignement du texte. Ensuite, nous parcourons toutes les cellules des lignes alternées et définissons leur couleur d’arrière-plan et de texte.

## Étape 10 : Enregistrement du document PDF
Enfin, nous enregistrons le document PDF à l'emplacement spécifié.

```csharp
// Enregistrez le PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin du répertoire et le nom de fichier souhaités pour le fichier PDF de sortie.

### Exemple de code source pour exporter les données d'une feuille de calcul Excel vers un tableau à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
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

// Créer un objet Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter l'objet Table dans la collection paragraphes de la section
sec1.Paragraphs.Add(tab1);

// Définissez les largeurs de colonnes du tableau. Nous devons spécifier le ColumnCount manuellement.
// Comme la feuille de calcul Excel actuelle comporte trois colonnes, nous spécifions donc le même nombre
tab1.ColumnWidths = "40 100 100";

// Définir la bordure de cellule par défaut du tableau à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importer des données dans l'objet Table à partir du DataTable créé ci-dessus
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Récupère la 1ère ligne du tableau
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Parcourez toutes les cellules de la 1ère ligne et définissez leur couleur d'arrière-plan sur bleu
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Définissez l’arrière-plan de toutes les cellules de la 1ère ligne du tableau.
	curCell.BackgroundColor = Color.Blue;
	// Définissez la police pour les cellules de la 1ère ligne du tableau.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Définissez la couleur de la police de toutes les cellules de la 1ère ligne du tableau.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Définissez l'alignement du texte pour les cellules de la 1ère ligne sur Centre.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Parcourez toutes les cellules de la 1ère ligne et définissez leur couleur d'arrière-plan sur bleu
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Définissez la couleur d'arrière-plan de toutes les cellules sauf de la 1ère ligne.
		curCell.BackgroundColor = Color.Gray;
		// Définissez la couleur du texte de toutes les cellules sauf la 1ère ligne.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Enregistrez le PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à exporter des données d'une feuille de calcul Excel vers un tableau PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons couvert le processus étape par étape de chargement de la feuille de calcul Excel, de création d'un document PDF, d'ajout d'un tableau, d'importation de données et de formatage du tableau. Vous pouvez désormais générer des fichiers PDF avec des tableaux contenant des données Excel par programmation.

### FAQ

#### Q : A quoi sert l’exportation des données d’une feuille de calcul Excel vers un tableau PDF ?

R : L'exportation des données d'une feuille de calcul Excel vers un tableau PDF vous permet de présenter les données dans un format structuré et organisé. Il vous permet de générer des fichiers PDF avec des tableaux contenant des données de feuilles de calcul Excel, facilitant ainsi le partage et la conservation des informations dans un format de document portable.

#### Q : Puis-je personnaliser l’apparence du tableau PDF ?

: Oui, vous pouvez personnaliser l'apparence du tableau PDF à l'aide de diverses propriétés fournies par Aspose.PDF pour .NET. Dans le code source C# fourni, vous pouvez modifier les largeurs de colonnes, les bordures de cellules, l'alignement du texte, le style de police, etc. pour répondre à vos besoins spécifiques.

#### Q : Comment gérer les fichiers Excel contenant plusieurs feuilles de calcul ?

 R : Dans le code C# fourni, nous avons accédé à la première feuille de calcul du fichier Excel à l'aide de l'index`[0]` . Si votre fichier Excel contient plusieurs feuilles de calcul, vous pouvez y accéder en modifiant la valeur d'index en conséquence, par exemple`[1]` pour la deuxième feuille de calcul ou`[2]` pour la troisième feuille de travail.

#### Q : Puis-je appliquer une mise en forme différente à des lignes ou des cellules spécifiques du tableau PDF ?

R : Oui, vous pouvez appliquer une mise en forme différente à des lignes ou des cellules spécifiques du tableau PDF. Dans le code source C# fourni, nous avons montré comment formater différemment la première ligne et les lignes alternées en modifiant leur couleur d'arrière-plan, leur style de police et leur couleur. Vous pouvez appliquer des techniques de formatage similaires à des lignes ou cellules spécifiques selon vos besoins.

#### Q : Aspose.PDF pour .NET est-elle la seule bibliothèque permettant d'exporter des données Excel vers un tableau PDF ?

R : Aspose.PDF pour .NET est une bibliothèque puissante permettant de travailler avec des documents PDF dans des applications .NET. Bien qu'il puisse exister d'autres bibliothèques disponibles, Aspose.PDF pour .NET offre un large éventail de fonctionnalités et de capacités pour générer, manipuler et exporter des fichiers PDF avec des tableaux à partir de données Excel, ce qui en fait un choix populaire pour de telles tâches.