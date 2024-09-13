---
title: Définir la bordure du PDF sur un tableau
linktitle: Définir la bordure du PDF sur un tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir une bordure dans un tableau PDF avec Aspose.PDF pour .NET.
type: docs
weight: 200
url: /fr/net/programming-with-tables/set-border/
---
Dans ce tutoriel, nous vous guiderons étape par étape pour définir une bordure dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Instanciation de l'objet Document
Tout d’abord, nous allons instancier un objet Document :

```csharp
Document doc = new Document();
```

## Étape 2 : Ajout d'une page au document PDF
Ensuite, nous allons ajouter une page au document PDF :

```csharp
Page page = doc.Pages.Add();
```

## Étape 3 : création de l'objet BorderInfo
Nous allons maintenant créer un objet BorderInfo pour définir la bordure du tableau :

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Étape 4 : Spécification des bordures supérieure et inférieure
Nous préciserons que les bordures hautes et basses seront doubles :

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Étape 5 : Instanciation de l'objet Table
Instancions maintenant un objet Table :

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Étape 6 : Spécification de la largeur des colonnes
Nous allons préciser les largeurs des colonnes du tableau :

```csharp
table. ColumnWidths = "100";
```

## Étape 7 : Création de l'objet Row
Nous allons créer un objet Row :

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Étape 8 : Ajout d'une cellule à la ligne
Ensuite, nous allons ajouter une cellule à la ligne :

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Étape 9 : Définition de la bordure de la cellule
Nous allons définir la bordure de la cellule (double bordure) :

```csharp
cell. Border = border;
```

## Étape 10 : Ajout du tableau à la page
Ajoutons maintenant le tableau à la page du document :

```csharp
page.Paragraphs.Add(table);
```

## Étape 11 : Enregistrer le document PDF
Enfin, nous allons enregistrer le document PDF :

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour définir une bordure à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page au document PDF
Page page = doc.Pages.Add();
// Créer un objet BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Spécifiez que la bordure supérieure sera double
border.Top.IsDoubled = true;
// Spécifiez que la bordure inférieure sera double
border.Bottom.IsDoubled = true;
// Instancier l'objet Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Spécifier les informations sur la largeur des colonnes
table.ColumnWidths = "100";
// Créer un objet Row
Aspose.Pdf.Row row = table.Rows.Add();
// Ajouter une cellule de tableau à la collection de cellules de la ligne
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Définir la bordure de l'objet cellule (double bordure)
cell.Border = border;
// Ajouter un tableau à la collection de paragraphes de la page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusion
Félicitations ! Vous avez maintenant appris à définir une bordure dans un tableau d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment créer un document, ajouter une page, configurer la bordure du tableau et enregistrer le document PDF. Vous pouvez désormais appliquer ces connaissances à vos propres projets.

### FAQ

#### Q : Puis-je définir des styles de bordure différents (par exemple, en pointillés ou en tirets) pour les bordures supérieure et inférieure du tableau ?

 R : Oui, vous pouvez définir différents styles de bordure pour les bordures supérieure et inférieure du tableau en modifiant le`border.Top.Style` et`border.Bottom.Style`propriétés dans le code source C# fourni. Aspose.PDF pour .NET vous permet de choisir parmi différents styles de bordure, notamment Solid, Dashed, Dotted, Double, etc.

#### Q : Comment puis-je définir la couleur de la bordure du tableau ?

 A : Vous pouvez définir la couleur de la bordure du tableau en modifiant la`border.Color` propriété dans le code source C#. Fournissez simplement la couleur souhaitée, par exemple`Aspose.Pdf.Color.Red` ou toute autre représentation de couleur valide, pour personnaliser la couleur de la bordure.

#### Q : Est-il possible d'appliquer des bordures à des cellules individuelles dans le tableau avec des paramètres différents (par exemple, des couleurs ou des styles de bordure différents) ?

 R : Oui, vous pouvez appliquer des bordures à des cellules individuelles dans le tableau avec différents paramètres en configurant le`cell.Border` propriété pour chaque cellule individuellement. Cela vous permet d'avoir des styles et des couleurs de bordure spécifiques à chaque cellule en fonction de vos besoins.

#### Q : Puis-je supprimer la bordure de certains côtés du tableau (par exemple, les bordures gauche et droite) ?

 R : Oui, vous pouvez supprimer la bordure de certains côtés du tableau en modifiant le`border.Left`, `border.Right`, `border.Top` , et`border.Bottom`propriétés dans le code source C#. Définition de ces propriétés sur`null` supprimera la bordure des côtés correspondants du tableau.

#### Q : Comment puis-je ajuster l'épaisseur de la bordure du tableau ?

 A : Vous pouvez ajuster l'épaisseur de la bordure du tableau en modifiant le`border.Width` propriété dans le code source C#. Définissez simplement la largeur de bordure souhaitée (en points) pour obtenir l'épaisseur souhaitée.