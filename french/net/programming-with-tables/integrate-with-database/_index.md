---
title: Intégrer avec la base de données
linktitle: Intégrer avec la base de données
second_title: Référence de l'API Aspose.PDF pour .NET
description: Intégrez les données d'une base de données dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-tables/integrate-with-database/
---

Dans ce didacticiel, nous allons apprendre à intégrer des données d'une base de données dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons pas à pas le code source en C#. À la fin de ce didacticiel, vous saurez comment importer des données de tableau d'une base de données dans un document PDF. Commençons!

## Étape 1 : Configurer l'environnement
Assurez-vous d'avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Création du tableau de données
Nous créons une instance de DataTable pour représenter les données que nous voulons intégrer dans le document PDF. Dans cet exemple, nous créons un DataTable avec trois colonnes : Employee_ID, Employee_Name et Gender. Nous ajoutons également deux lignes au DataTable avec des données factices.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Étape 3 : Création du document PDF et du tableau
Nous créons une instance de Document et ajoutons une page à ce document. Ensuite, nous créons une instance Table pour représenter notre table dans le document PDF. Nous définissons les largeurs de colonne de tableau et les styles de bordure.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Étape 4 : Importation des données du DataTable dans la table
Nous utilisons la méthode ImportDataTable pour importer les données du DataTable dans le tableau du document PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Étape 5 : Ajouter le tableau au document
Nous ajoutons le tableau à la collection de paragraphes de la page du document.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Étape 6 : Enregistrez le document
Nous enregistrons le document PDF avec les données de la base de données intégrée.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Toutes nos félicitations! Vous savez maintenant comment intégrer des données de base de données dans un document PDF à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour l'intégration à la base de données à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Ajouter 2 lignes dans l'objet DataTable par programmation
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Créer une instance de document
Document doc = new Document();
doc.Pages.Add();
// Initialise une nouvelle instance de la table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définir la largeur des colonnes du tableau
table.ColumnWidths = "40 100 100 100";
// Définissez la couleur de la bordure du tableau sur LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Définir la bordure des cellules du tableau
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Ajouter un objet tableau à la première page du document d'entrée
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Enregistrer le document mis à jour contenant l'objet tableau
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons appris à intégrer des données d'une base de données dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour importer les données de votre propre base de données et les afficher dans des documents PDF. Explorez plus en détail la documentation Aspose.PDF pour découvrir d'autres fonctionnalités et possibilités offertes par cette puissante bibliothèque.