---
title: Ajouter un tableau dans un fichier PDF
linktitle: Ajouter un tableau dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Ajoutez facilement des tableaux dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-tables/add-table/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et transformer des documents PDF par programme. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'un tableau dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons chaque étape de l'extrait de code fourni et fournirons un guide complet pour vous aider à comprendre et à implémenter les fonctionnalités dans vos propres projets.

## Introduction

Les documents PDF sont largement utilisés pour partager et conserver des informations dans un format portable. L'ajout de tableaux aux documents PDF peut améliorer leur apparence visuelle et rendre la présentation des données plus organisée et structurée. Aspose.PDF pour .NET offre un moyen pratique d'ajouter des tableaux à des documents PDF existants ou d'en créer de nouveaux à partir de zéro.

## Qu’est-ce qu’Aspose.PDF pour .NET ?

Aspose.PDF pour .NET est une bibliothèque puissante et riche en fonctionnalités qui permet aux développeurs .NET de créer, manipuler et convertir des documents PDF par programme. Il offre un large éventail de fonctionnalités, notamment la création de fichiers PDF à partir de zéro, la modification de documents PDF existants, la fusion ou le fractionnement de fichiers PDF, l'ajout de texte, d'images et de tableaux, l'extraction de données à partir de PDF et bien plus encore. Avec Aspose.PDF pour .NET, les développeurs peuvent automatiser des tâches complexes liées aux PDF et fournir des solutions PDF de haute qualité.

## Ajout d'un tableau à un document PDF

Pour ajouter un tableau à un document PDF à l'aide d'Aspose.PDF pour .NET, suivez le guide étape par étape ci-dessous :

## Étape 1 : Chargement du document PDF source

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

L'extrait de code ci-dessus charge le document PDF source auquel vous souhaitez ajouter le tableau. Assurez-vous de fournir le chemin correct vers votre fichier PDF.

## Étape 2 : initialisation d'une nouvelle instance de la table

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

Dans cette étape, nous créons une nouvelle instance de la classe Table, qui représente un tableau dans un document PDF.

## Étape 3 : Définition de la couleur de la bordure du tableau

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Ici, nous définissons la couleur de la bordure du tableau à l'aide de la classe BorderInfo. Vous pouvez personnaliser le style, la largeur et la couleur de la bordure selon vos besoins.

## Étape 4 : Définition de la bordure des cellules du tableau

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Nous définissons également la bordure des cellules du tableau à l’aide de la propriété DefaultCellBorder de l’objet tableau. Cela garantit que chaque cellule du tableau a le style de bordure, la largeur et la couleur spécifiés.

## Étape 5 : Ajout de lignes et de cellules au tableau

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

Dans cette étape, nous créons une boucle pour ajouter 10 lignes au tableau. Dans chaque ligne, nous ajoutons trois cellules avec des exemples de données. Vous pouvez modifier le code pour ajouter des lignes et des cellules en fonction de vos besoins spécifiques.

## Étape 6 : Ajout de l'objet tableau au document

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Enregistrer le document mis à jour contenant l'objet table
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Enfin, nous ajoutons l'objet tableau à la première page du document PDF en utilisant la collection Paragraphs de la page correspondante.

### Exemple de code source pour ajouter une table à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Charger le document PDF source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Initialise une nouvelle instance de la Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définissez la couleur de la bordure du tableau sur LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Définir la bordure des cellules du tableau
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Créez une boucle pour ajouter 10 lignes
for (int row_count = 1; row_count < 10; row_count++)
{
	// Ajouter une ligne au tableau
	Aspose.Pdf.Row row = table.Rows.Add();
	// Ajouter des cellules de tableau
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Ajouter un objet tableau à la première page du document d'entrée
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Enregistrer le document mis à jour contenant l'objet table
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Conclusion

Dans ce didacticiel, nous avons expliqué le processus étape par étape d'ajout d'un tableau à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous avons couvert le chargement du document PDF source, l'initialisation d'une nouvelle instance de la classe Table, la définition de la couleur de la bordure du tableau et des bordures des cellules, l'ajout de lignes et de cellules au tableau et l'ajout de l'objet tableau au document. En suivant ce guide, vous pouvez facilement incorporer des tableaux dans vos documents PDF par programmation et les personnaliser en fonction de vos besoins spécifiques.

### FAQ pour ajouter un tableau dans un fichier PDF

#### Q : Puis-je ajouter plus de colonnes au tableau ?

: Oui, vous pouvez ajouter plus de colonnes au tableau en augmentant le nombre de cellules ajoutées à chaque ligne. Dans l'exemple fourni, chaque ligne comporte trois cellules représentant trois colonnes. Vous pouvez ajouter plus de cellules à chaque ligne pour ajouter des colonnes supplémentaires.

#### Q : Comment puis-je modifier l’apparence du tableau, comme la taille et le style de la police ?

 R : Vous pouvez personnaliser l'apparence du tableau, notamment la taille et le style de la police, en définissant les propriétés dans l'onglet`Aspose.Pdf.Table` et`Aspose.Pdf.TextFragment` objets. Par exemple, vous pouvez définir le`DefaultCellTextState` propriété pour modifier les propriétés de police du texte dans les cellules du tableau.

#### Q : Est-il possible de fusionner des cellules dans le tableau ?

 R : Oui, vous pouvez fusionner des cellules dans le tableau à l'aide de l'outil`MergeCells` méthode du`Aspose.Pdf.Row` classe. Cela vous permet de créer des cellules qui s'étendent sur plusieurs lignes et colonnes.

#### Q : Puis-je ajouter des images ou tout autre contenu aux cellules du tableau ?

R : Oui, vous pouvez ajouter différents types de contenu aux cellules du tableau, notamment des images, du texte, des hyperliens, etc. Vous pouvez utiliser les classes appropriées d'Aspose.PDF pour .NET pour ajouter différents types de contenu aux cellules.

#### Q : Aspose.PDF pour .NET est-il compatible avec .NET 5.0 ou versions ultérieures ?

R : Oui, Aspose.PDF pour .NET est compatible avec .NET 5.0 et les versions ultérieures. Il prend en charge diverses plates-formes .NET, notamment .NET Framework, .NET Core et .NET 5.0+.