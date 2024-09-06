---
title: Insérer un saut de page dans un fichier PDF
linktitle: Insérer un saut de page dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment insérer un saut de page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-tables/insert-page-break/
---
Dans ce tutoriel, nous allons apprendre à insérer un saut de page dans un fichier PDF en utilisant Aspose.PDF pour .NET. Nous expliquerons le code source en C# étape par étape. À la fin de ce tutoriel, vous saurez comment ajouter un saut de page après un certain nombre de lignes dans un tableau d'un document PDF. Commençons !

## Étape 1 : Configuration de l'environnement
Assurez-vous d'avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Création du document et du tableau
Nous créons une nouvelle instance de Document et ajoutons une page à ce document. Ensuite, nous créons une instance de Table pour représenter notre tableau dans le document PDF. Nous définissons également les styles de bordure du tableau.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Étape 3 : Ajouter des lignes au tableau
Nous utilisons une boucle pour ajouter 200 lignes au tableau. Pour chaque ligne, nous créons une instance de Row et ajoutons deux cellules avec du contenu textuel.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Lorsque 10 lignes sont ajoutées, nous insérons un nouveau saut de page
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Étape 4 : Ajout du tableau au document
Nous ajoutons le tableau à la collection de paragraphes de la page du document.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Étape 5 : Enregistrer le document
Nous enregistrons le document PDF avec le saut de page inséré.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Exemple de code source pour l'insertion d'un saut de page à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
doc.Pages.Add();
// Créer une instance de table
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Définir le style de bordure du tableau
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Définir le style de bordure par défaut pour le tableau avec la couleur de bordure en rouge
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Spécifier la largeur des colonnes du tableau
tab.ColumnWidths = "100 100";
// Créer une boucle pour ajouter 200 lignes au tableau
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Lorsque 10 lignes sont ajoutées, afficher la nouvelle ligne dans une nouvelle page
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Ajouter un tableau à la collection de paragraphes du fichier PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce tutoriel, nous avons appris à insérer un saut de page dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour ajouter un saut de page après un certain nombre de lignes dans un tableau dans un document PDF à l'aide de C#.

### FAQ sur l'insertion de saut de page dans un fichier PDF

#### Q : Comment puis-je modifier la taille de la page pour les nouvelles pages créées après le saut de page ?

 A : Pour modifier la taille de la page pour les nouvelles pages créées après le saut de page, vous pouvez définir le`PageSize` propriété de la`Page` objet. Par exemple, vous pouvez utiliser le code suivant pour définir la taille de la page sur A4 :

```csharp
// Définir la taille de la page sur A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q : Puis-je contrôler les marges des nouvelles pages après le saut de page ?

 R : Oui, vous pouvez contrôler les marges des nouvelles pages après le saut de page. Utilisez le`Margin` propriété de la`Page` objet pour définir les marges de la page. Par exemple, pour définir toutes les marges à 10 points, vous pouvez utiliser le code suivant :

```csharp
// Réglez toutes les marges à 10 points
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q : Est-il possible d’ajouter des en-têtes et des pieds de page aux nouvelles pages après le saut de page ?

 R : Oui, vous pouvez ajouter des en-têtes et des pieds de page aux nouvelles pages après le saut de page. Utilisez le`Page.Header` et`Page.Footer` propriétés pour ajouter du contenu aux sections d'en-tête et de pied de page de la page. Par exemple :

```csharp
// Ajouter un en-tête aux nouvelles pages
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Ajouter un pied de page aux nouvelles pages
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Q : Puis-je insérer des sauts de page à des emplacements spécifiques autres qu’après un certain nombre de lignes ?

 R : Oui, vous pouvez insérer des sauts de page à des emplacements spécifiques autres qu'après un certain nombre de lignes. Vous pouvez définir le`IsInNewPage` propriété d'une ligne à`true` pour forcer le tableau à démarrer une nouvelle page après cette ligne.

#### Q : Comment puis-je ajuster le comportement des sauts de page en fonction de la hauteur du contenu ?

 A : Vous pouvez utiliser le`IsBroken` propriété du tableau pour activer ou désactiver le saut de ligne automatique sur les pages. Lorsqu'il est défini sur`true`, il permet aux lignes d'être réparties sur plusieurs pages en fonction de la hauteur du contenu.