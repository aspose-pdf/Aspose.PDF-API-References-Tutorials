---
title: Cellule du tableau des styles
linktitle: Cellule du tableau des styles
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à styliser les cellules de tableau avec Aspose.PDF pour .NET. Guide étape par étape pour créer et personnaliser des tableaux.
type: docs
weight: 160
url: /fr/net/programming-with-tagged-pdf/style-table-cell/
---
Bienvenue dans ce didacticiel détaillé sur le formatage des cellules de tableau à l'aide d'Aspose.PDF pour .NET. Dans ce guide, nous expliquerons en détail chaque étape du code source C # fourni pour vous aider à comprendre comment styliser les cellules de tableau. Assurez-vous d'avoir installé Aspose.PDF pour .NET et configuré votre environnement de développement avant de commencer.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela inclut l'installation de la bibliothèque Aspose.PDF et la configuration de votre projet pour le référencer.

## Étape 2 : création d'un document

Dans cette étape, nous allons créer un nouvel objet de document Aspose.PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// création de documents
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Nous avons créé un nouveau document et défini le titre et la langue du document.

## Etape 3 : Obtention de l'élément de structure racine

Dans cette étape, nous obtiendrons l'élément de structure racine de notre document.

```csharp
// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
```

Nous avons obtenu l'élément de structure racine qui servira de conteneur pour les éléments du tableau.

## Étape 4 : Création de l'élément de structure de tableau

Créons maintenant un nouvel élément de structure de table pour notre document.

```csharp
// Créer l'élément de structure de tableau
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Nous avons créé un nouvel élément de structure de tableau et l'avons ajouté à l'élément de structure racine. Nous avons également créé les éléments d'en-tête, de corps et de pied de page du tableau.

## Étape 5 : Ajouter des en-têtes de tableau

Dans cette étape, nous ajouterons les en-têtes de tableau à notre tableau.

```csharp
// Nombre de lignes et de colonnes dans le tableau
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Créer la ligne d'en-tête du tableau
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Nous avons créé une ligne d'en-tête pour notre tableau et ajouté des cellules d'en-tête avec des propriétés de formatage telles que la couleur d'arrière-plan, les bordures, les marges et l'alignement.

## Étape 6 : Ajout des lignes du corps du tableau

Ajoutons maintenant les lignes du corps du tableau à notre tableau.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Nous avons ajouté des lignes au corps du tableau en utilisant des boucles pour parcourir chaque cellule du tableau. Nous définissons des propriétés de formatage pour chaque cellule, telles que la couleur d'arrière-plan, les bordures, les marges, l'alignement du texte, etc.

## Étape 7 : Ajouter le pied de page

Enfin, nous ajouterons le pied de tableau à notre tableau.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Nous avons créé un pied de page pour notre tableau et ajouté des cellules de pied de page avec du texte.



## Étape 8 : Enregistrer le document PDF balisé

Maintenant que nous avons créé notre document avec le tableau stylisé, nous allons l'enregistrer en tant que document PDF balisé.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "StyleTableCell.pdf");
```

Nous avons enregistré le document PDF balisé dans le répertoire spécifié.

## Étape 9 : Validation de la conformité PDF/UA

Ensuite, nous validerons la conformité PDF/UA de notre document.

```csharp
// Contrôle de conformité PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nous avons téléchargé le document PDF balisé et validé sa conformité PDF/UA en générant un rapport XML.

### Exemple de code source pour Style Table Cell en utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;

// Créer un élément de structure de table
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Enregistrer le document PDF balisé
document.Save(dataDir + "StyleTableCell.pdf");

// Vérification de la conformité PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, nous avons appris à styliser les cellules d'un tableau à l'aide d'Aspose.PDF pour .NET. Nous avons vu comment créer un document, ajouter un tableau avec des en-têtes, des lignes de corps et un pied de page, et personnaliser les styles de cellule. Enfin, nous avons enregistré le document PDF balisé et validé sa conformité PDF/UA. Vous pouvez désormais utiliser Aspose.PDF pour .NET pour créer et styliser des tableaux dans vos applications .NET.
