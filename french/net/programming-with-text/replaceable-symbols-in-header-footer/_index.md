---
title: Symboles remplaçables dans l'en-tête de pied de page
linktitle: Symboles remplaçables dans l'en-tête de pied de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser des symboles remplaçables dans l'en-tête et le pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 320
url: /fr/net/programming-with-text/replaceable-symbols-in-header-footer/
---

Dans ce didacticiel, nous expliquerons comment utiliser des symboles remplaçables dans l'en-tête et le pied de page d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape de création d'un PDF, de définition des marges, d'ajout d'en-tête et de pied de page avec des symboles remplaçables et d'enregistrement du PDF à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un document PDF et une page

 Ensuite, nous créons un nouveau document PDF et y ajoutons une page en utilisant le`Document` classe et`Page` classe de la bibliothèque Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 3 : Définir les marges

 Nous définissons les marges de la page à l'aide de la`MarginInfo` classe. Ajustez les valeurs de marge en fonction de vos besoins.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Étape 4 : Ajouter un en-tête avec des symboles remplaçables

 Nous créons un`HeaderFooter` objet pour la page et ajoutez un`TextFragment` avec des symboles remplaçables.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Définissez les propriétés du texte si vous le souhaitez
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Ajoutez plus de TextFragments ou personnalisez au besoin
```

## Étape 5 : Ajouter un pied de page avec des symboles remplaçables

 De même, nous créons un`HeaderFooter` objet pour le pied de page et ajouter`TextFragment` objets avec des symboles remplaçables.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Ajoutez plus de TextFragments ou personnalisez au besoin

hfFoot.Paragraphs.Add(tab2);
```

## Étape 6 : Enregistrez le document PDF

Enfin, nous enregistrons le document PDF dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Exemple de code source pour les symboles remplaçables dans l'en-tête de pied de page à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Attribuez l'instance marginInfo à la propriété Margin de sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Instanciez un paragraphe de texte qui stockera le contenu à afficher comme en-tête
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Créer un objet HeaderFooter pour la section
HeaderFooter hfFoot = new HeaderFooter();
// Définissez l'objet HeaderFooter sur un pied de page impair et pair
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Ajouter un paragraphe de texte contenant le numéro de la page actuelle du nombre total de pages
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Instancier un objet table
Table tab2 = new Table();
// Ajouter le tableau dans la collection de paragraphes de la section souhaitée
hfFoot.Paragraphs.Add(tab2);
// Définir avec les largeurs de colonne du tableau
tab2.ColumnWidths = "165 172 165";
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Définir l'alignement vertical du texte comme aligné au centre
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total pour Java est une compilation de tous les composants Java proposés par Aspose. Il est compilé quotidiennement pour s'assurer qu'il contient les versions les plus récentes de chacun de nos composants Java. #$NL " + "En utilisant Aspose.Total pour Java, les développeurs peuvent créer une large gamme d'applications. #$NL #$NL #$NP" + "Aspose.Total pour Java est une compilation de chaque composant Java proposé par Aspose. Il est compilé quotidiennement pour s'assurer qu'il contient les versions les plus récentes de chacun de nos composants Java. #$NL " + "Aspose.Total pour les développeurs Java peut créer un large gamme d'applications. #$NL #$NL #$NP" + "Aspose.Total pour Java est une compilation de tous les composants Java proposés par Aspose. Il est compilé quotidiennement pour s'assurer qu'il contient le plus des versions à jour de chacun de nos composants Java. #$NL " + "Aspose.Total for Java permet aux développeurs de créer une large gamme d'applications. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Ajouter le tableau dans la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(table);
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Définir la bordure du tableau à l'aide d'un autre objet BorderInfo personnalisé
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Créer des lignes dans le tableau, puis des cellules dans les lignes
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, vous avez appris à utiliser des symboles remplaçables dans l'en-tête et le pied de page d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez créer un PDF, définir des marges, ajouter un en-tête et un pied de page avec des symboles remplaçables et enregistrer le PDF.