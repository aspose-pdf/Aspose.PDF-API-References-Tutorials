---
title: Définir la bordure
linktitle: Définir la bordure
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir une bordure dans un tableau PDF avec Aspose.PDF pour .NET.
type: docs
weight: 200
url: /fr/net/programming-with-tables/set-border/
---

Dans ce didacticiel, nous vous guiderons pas à pas pour définir une bordure dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Instanciation de l'objet Document
Tout d'abord, nous allons instancier un objet Document :

```csharp
Document doc = new Document();
```

## Étape 2 : Ajouter une page au document PDF
Ensuite, nous allons ajouter une page au document PDF :

```csharp
Page page = doc.Pages.Add();
```

## Étape 3 : Création de l'objet BorderInfo
Nous allons maintenant créer un objet BorderInfo pour définir la bordure du tableau :

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Étape 4 : Spécification des bordures supérieure et inférieure
Précisons que les bordures haute et basse seront doubles :

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Étape 5 : Instanciation de l'objet Table
Instancions maintenant un objet Table :

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Étape 6 : Spécification des largeurs de colonne
Nous allons préciser les largeurs des colonnes du tableau :

```csharp
table. ColumnWidths = "100";
```

## Étape 7 : Création de l'objet de ligne
Nous allons créer un objet Row :

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Étape 8 : Ajouter une cellule à la ligne
Ensuite, nous allons ajouter une cellule à la ligne :

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Étape 9 : Définition de la bordure de cellule
Nous allons définir la bordure de la cellule (double bordure) :

```csharp
cell. Border = border;
```

## Étape 10 : Ajouter le tableau à la page
Ajoutons maintenant le tableau à la page du document :

```csharp
page.Paragraphs.Add(table);
```

## Étape 11 : Enregistrer le document PDF
Enfin, nous enregistrerons le document PDF :

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Set Border en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page au document PDF
Page page = doc.Pages.Add();
// Créer un objet BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Spécifiez que la bordure supérieure sera double
border.Top.IsDoubled = true;
// Spécifiez que la bordure inférieure sera double
border.Bottom.IsDoubled = true;
// Instancier l'objet Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Spécifier les informations de largeur des colonnes
table.ColumnWidths = "100";
// Créer un objet Ligne
Aspose.Pdf.Row row = table.Rows.Add();
// Ajouter une cellule de tableau à la collection de cellules de la ligne
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Définir la bordure de l'objet cellule (double bordure)
cell.Border = border;
// Ajouter un tableau à la collection de paragraphes de la page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Enregistrez le document PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusion
Félicitation ! Vous avez maintenant appris à définir une bordure dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment créer un document, ajouter une page, configurer la bordure du tableau et enregistrer le document PDF. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.