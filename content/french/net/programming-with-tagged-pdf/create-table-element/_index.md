---
title: Créer un élément de tableau
linktitle: Créer un élément de tableau
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour créer un élément de tableau avec Aspose.PDF pour .NET. Générez facilement des PDF dynamiques avec des tableaux.
type: docs
weight: 80
url: /fr/net/programming-with-tagged-pdf/create-table-element/
---
Dans ce guide étape par étape, nous vous guiderons tout au long du processus de création d'un élément de tableau à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de manipuler des documents PDF par programme. La création d'un élément de tableau est une exigence courante lors de la génération de PDF dynamiques, et Aspose.PDF offre un moyen simple et efficace d'y parvenir.

Plongeons dans le code et apprenons à créer un élément de tableau à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Bibliothèque Aspose.PDF pour .NET installée.
2. Une connaissance de base du langage de programmation C#.

## Étape 1 : Configuration de l'environnement

Pour commencer, ouvrez votre environnement de développement C# et créez un nouveau projet. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document

 La première étape consiste à créer un nouveau document PDF à l'aide du`Document` classe.

```csharp
// Créer le document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Ici, nous définissons également le titre et la langue du contenu balisé.

## Étape 3 : Création de l'élément du tableau

Ensuite, nous devons créer l’élément du tableau et l’ajouter au document. Nous commençons par récupérer l'élément de structure racine, puis nous créons un nouvel élément de table en utilisant le`CreateTableElement` méthode.

```csharp
// Obtenez l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Enregistrez le document PDF balisé
document.Save(dataDir + "CreateTableElement.pdf");

// Vérification de la conformité PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Exemple de code source pour créer un élément de table à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Enregistrer le document PDF balisé
document.Save(dataDir + "CreateTableElement.pdf");

// Vérification de la conformité PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Vous avez appris à créer un élément de tableau à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais générer des documents PDF avec des tableaux dynamiques en utilisant cette méthode. N'hésitez pas à explorer davantage de fonctionnalités d'Aspose.PDF pour découvrir tout son potentiel.

### FAQ

#### Q : Qu'est-ce qu'un élément de tableau dans un document PDF et pourquoi devrais-je en créer un à l'aide d'Aspose.PDF pour .NET ?

R : Un élément de tableau dans un document PDF représente une collection structurée de données, souvent utilisée pour créer des tableaux ou des grilles. Vous devrez peut-être créer un élément de tableau à l'aide d'Aspose.PDF pour .NET lors de la génération de PDF dynamiques nécessitant une présentation de données structurées, telles que des informations tabulaires ou des grilles.

#### Q : Comment Aspose.PDF pour .NET simplifie-t-il le processus de création d'un élément de tableau ?

R : Aspose.PDF pour .NET fournit un ensemble complet de classes et de méthodes qui vous permettent de créer, personnaliser et gérer des éléments de tableau (tableaux) dans un document PDF par programmation. Cela élimine le besoin de manipulation manuelle des PDF et rationalise la création de représentations de données structurées.

#### Q : Quelles sont les étapes clés impliquées dans la création d’un élément de tableau à l’aide d’Aspose.PDF pour .NET ?

R : Les étapes clés comprennent la configuration de l'environnement, la création du document, l'obtention de l'élément de structure racine, la création d'un élément de tableau, la définition des lignes et des cellules dans le tableau et la spécification du formatage et des propriétés des éléments. L'exemple de code fourni illustre ces étapes.

####  Q : Quel rôle joue le`taggedContent` object play in creating an array element?

 R : Le`taggedContent` objet, obtenu à partir du document`TaggedContent`propriété, vous permet de définir la structure du contenu balisé dans le document PDF. Cela inclut la création et l'organisation des éléments du tableau et de leurs éléments enfants de manière hiérarchique.

#### Q : Comment le code garantit-il l'accessibilité et la sémantique de l'élément de tableau créé ?

 R : Le code définit des attributs tels que`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , et`ColSpan` pour améliorer l'accessibilité et la sémantique de l'élément du tableau. Ces attributs contribuent à une représentation des données bien structurée, informative et visuellement attrayante.

#### Q : Quelle est l'importance de la conformité PDF/UA dans le contexte de la création d'éléments de tableau ?

 R : La conformité PDF/UA (Accessibilité universelle) garantit que les documents PDF générés sont accessibles aux utilisateurs handicapés et répondent à certaines normes d'accessibilité. L'exemple de code vérifie la conformité PDF/UA à l'aide de l'outil`Validate` méthode, vous aidant à créer des documents inclusifs et accessibles.

#### Q : Puis-je personnaliser davantage le formatage et l’apparence des éléments du tableau ?

: Oui, vous pouvez personnaliser le formatage et l'apparence des éléments du tableau en ajustant des attributs tels que la couleur d'arrière-plan, le style de bordure, la taille de la police et l'alignement. Aspose.PDF pour .NET fournit un large éventail de propriétés pour adapter la présentation visuelle à vos besoins.

#### Q : Comment puis-je étendre ces connaissances pour créer des structures de tableaux plus complexes ou incorporer des éléments de tableau dans des documents PDF plus volumineux ?

R : Vous pouvez étendre ces connaissances en explorant les fonctionnalités supplémentaires d'Aspose.PDF pour .NET, telles que la fusion de plusieurs éléments de tableau, la création de tableaux imbriqués, l'ajout d'en-têtes et de pieds de page et l'intégration d'éléments de tableau dans des mises en page PDF plus grandes. La documentation et les exemples de la bibliothèque fournissent des conseils pour ces scénarios avancés.

#### Q : Est-il possible d'importer des données à partir de sources externes, telles que des bases de données ou des feuilles de calcul, pour remplir les éléments du tableau ?

R : Oui, vous pouvez importer des données à partir de sources externes pour remplir les éléments du tableau. Vous pouvez utiliser des techniques de récupération et de transformation de données en C# pour récupérer des données à partir de bases de données, de feuilles de calcul ou d'autres sources, puis remplir les éléments du tableau en conséquence.

#### Q : Comment puis-je utiliser les connaissances acquises grâce à ce didacticiel pour améliorer la qualité et la convivialité des documents PDF que je crée par programme ?

R : Les connaissances acquises grâce à ce didacticiel vous permettent de créer des éléments de tableau (tableaux) structurés et visuellement attrayants dans des documents PDF. En incorporant ces techniques, vous pouvez améliorer la lisibilité, l'accessibilité et l'expérience utilisateur des PDF générés dynamiquement, les rendant plus informatifs et conviviaux.