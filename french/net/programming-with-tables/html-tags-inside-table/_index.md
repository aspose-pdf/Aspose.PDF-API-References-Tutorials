---
title: Balises HTML à l'intérieur du tableau dans un fichier PDF
linktitle: Balises HTML à l'intérieur du tableau dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser les balises HTML dans un tableau dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-tables/html-tags-inside-table/
---
Dans ce didacticiel, nous allons apprendre à utiliser des balises HTML dans un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons pas à pas le code source en C#. À la fin de ce didacticiel, vous saurez comment insérer du contenu HTML dans un tableau d'un document PDF. Commençons!

## Étape 1 : Configurer l'environnement
Assurez-vous d'avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Créer des données de table
Nous créons un DataTable contenant une colonne "data" de type String. Nous ajoutons ensuite des lignes à ce DataTable en utilisant le contenu HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Étape 3 : création du document et du tableau
Nous créons un nouveau document PDF et ajoutons une page dans ce document. Ensuite, nous initialisons une instance de la classe Table et définissons les propriétés de la table.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Étape 4 : Importer des données dans le tableau
Nous importons les données du DataTable dans la table en utilisant la méthode "ImportDataTable". Nous spécifions les paramètres de méthode pour indiquer quelle plage de lignes et de colonnes du DataTable doit être importée.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Étape 5 : Ajouter le tableau au document
Nous ajoutons le tableau à la page du document.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etape 6 : Enregistrer le document
Nous enregistrons le document PDF avec le tableau contenant le contenu HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Exemple de code source pour les balises HTML à l'intérieur du tableau à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Initialise une nouvelle instance de la table
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Définir la largeur des colonnes du tableau
tableProvider.ColumnWidths = "400 50 ";
// Définissez la couleur de la bordure du tableau sur LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Définir la bordure des cellules du tableau
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser des balises HTML dans un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour insérer du contenu HTML dans des cellules de tableau dans un document PDF à l'aide de C#.

### FAQ pour les balises HTML à l'intérieur du tableau dans le fichier PDF

#### Q : Puis-je utiliser d'autres balises et attributs HTML dans les cellules du tableau ?

 R : Oui, vous pouvez utiliser diverses balises et attributs HTML dans les cellules du tableau, tels que`<b>`, `<i>`, `<a>`et beaucoup plus. Aspose.PDF pour .NET prend en charge un large éventail d'éléments et de styles HTML que vous pouvez utiliser pour formater le contenu dans les cellules du tableau.

#### Q : Puis-je appliquer des styles CSS au contenu HTML dans les cellules du tableau ?

R : Oui, vous pouvez appliquer des styles CSS au contenu HTML à l'intérieur des cellules du tableau. Aspose.PDF pour .NET prend en charge les styles CSS de base pouvant être appliqués aux éléments HTML.

#### Q : Est-il possible d'ajouter des images avec du contenu HTML dans les cellules du tableau ?

 R : Oui, vous pouvez ajouter des images avec du contenu HTML dans les cellules du tableau. Vous pouvez utiliser HTML`<img>` balises pour inclure des images provenant de diverses sources, telles que des fichiers locaux ou des URL.

#### Q : Comment puis-je spécifier différentes largeurs de colonne pour le tableau ?

 R : Vous pouvez spécifier différentes largeurs de colonne pour le tableau à l'aide de la`ColumnWidths` propriété du tableau. La propriété prend une chaîne contenant des valeurs séparées par des espaces, où chaque valeur représente la largeur d'une colonne en points.

#### Q : Puis-je utiliser des tableaux imbriqués dans une cellule avec du contenu HTML ?

R : Oui, vous pouvez utiliser des tableaux imbriqués dans une cellule avec du contenu HTML. Vous pouvez créer des instances de tableau distinctes et les ajouter dans le cadre du contenu HTML à l'intérieur d'une cellule pour obtenir l'effet d'imbrication.