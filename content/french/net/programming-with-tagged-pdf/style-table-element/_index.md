---
title: Élément de tableau de style
linktitle: Élément de tableau de style
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment formater un élément de tableau avec Aspose.PDF pour .NET. Guide étape par étape pour personnaliser les styles et les propriétés.
type: docs
weight: 170
url: /fr/net/programming-with-tagged-pdf/style-table-element/
---
Dans ce didacticiel détaillé, nous vous guiderons étape par étape à travers le code source C# fourni pour formater l'élément de tableau à l'aide d'Aspose.PDF pour .NET. Suivez les instructions ci-dessous pour comprendre comment personnaliser les styles et les propriétés de l'élément de tableau.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela comprend l'installation de la bibliothèque Aspose.PDF et la configuration de votre projet pour y faire référence.

## Étape 2 : Créer un document

Dans cette étape, nous allons créer un nouvel objet de document Aspose.PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Nous avons créé un nouveau document et défini le titre et la langue du document.

## Étape 3 : Obtention de l'élément de structure racine

Dans cette étape, nous obtiendrons l’élément de structure racine de notre document.

```csharp
// Obtenir l'élément de structure racinaire
StructureElement rootElement = taggedContent.RootElement;
```

Nous avons obtenu l’élément de structure racine qui servira de conteneur pour l’élément du tableau.

## Étape 4 : Création de l'élément de structure du tableau

Créons maintenant un nouvel élément de structure de tableau pour notre document.

```csharp
// Créer l'élément de structure du tableau
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Nous avons créé un nouvel élément de structure de tableau et l'avons ajouté à l'élément de structure racine.

## Étape 5 : Personnalisation des styles et des propriétés des éléments du tableau

Dans cette étape, nous allons personnaliser les styles et les propriétés de l’élément du tableau.

```csharp
// Personnaliser les styles et les propriétés de l'élément du tableau
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Personnaliser le style des lignes répétées
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Nous avons utilisé diverses propriétés pour personnaliser l'élément du tableau, telles que la couleur d'arrière-plan, les bordures, l'alignement, le style de cellule par défaut, les marges, la largeur de la colonne, etc.

## Étape 6 : ajouter des en-têtes, un corps et un pied de page de tableau

Ajoutons maintenant les en-têtes, le corps et le pied de page du tableau à l'élément de tableau.
```csharp
// Ajouter des en-têtes de tableau
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Nombre de lignes et de colonnes dans le tableau
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Créer la ligne d'en-tête du tableau
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Ajouter les lignes du corps du tableau
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Ajouter la ligne de pied de tableau
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Nous avons ajouté les en-têtes, les lignes de corps et la ligne de pied de page au tableau en utilisant les éléments correspondants.

## Étape 7 : enregistrement du document PDF balisé

Maintenant que nous avons créé notre document avec l’élément de tableau stylisé, nous allons l’enregistrer en tant que document PDF balisé.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "StyleTableElement.pdf");
```

Nous avons enregistré le document PDF balisé dans le répertoire spécifié.

## Étape 8 : Validation de la conformité PDF/UA

Ensuite, nous validerons la conformité PDF/UA de notre document.

```csharp
// Vérification de conformité PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nous avons téléchargé le document PDF balisé et validé sa conformité PDF/UA en générant un rapport XML.

### Exemple de code source pour l'élément de tableau de style utilisant Aspose.PDF pour .NET 

```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;

// Créer un élément de structure de table
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
document.Save(dataDir + "StyleTableElement.pdf");

// Vérification de la conformité PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, nous avons appris à formater l'élément de tableau avec Aspose.PDF pour .NET. Nous avons personnalisé les styles et les propriétés de l'élément de tableau, ajouté des en-têtes, des lignes de corps et un pied de page, enregistré le document PDF balisé et validé sa conformité PDF/UA.

### FAQ

#### Q : Quel est le but de ce tutoriel sur la mise en forme de l'élément de tableau à l'aide d'Aspose.PDF pour .NET ?

R : L'objectif de ce didacticiel est de vous guider tout au long du processus de mise en forme de l'élément de tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Il fournit des instructions étape par étape et des exemples de code source C# pour vous aider à personnaliser les styles et les propriétés de l'élément de tableau.

#### Q : Quels sont les prérequis pour suivre ce tutoriel ?

R : Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela implique d'installer la bibliothèque Aspose.PDF et de configurer votre projet pour y faire référence.

#### Q : Comment puis-je créer un nouveau document PDF et définir son titre et sa langue à l'aide d'Aspose.PDF pour .NET ?

 R : Pour créer un nouveau document PDF, vous devez créer un`Document` objet de la bibliothèque Aspose.PDF. Le code source C# fourni dans le didacticiel montre comment créer un document et définir ses propriétés de titre et de langue.

#### Q : Quelle est la signification de l’élément de structure racine dans un document PDF ?

: L'élément de structure racine agit comme un conteneur pour d'autres éléments de structure, aidant à organiser et à catégoriser le contenu du document PDF. Il joue un rôle crucial dans l'établissement de la structure logique du document.

#### Q : Comment créer et personnaliser un élément de structure de tableau à l’aide d’Aspose.PDF pour .NET ?

 A : Vous pouvez créer un élément de structure de tableau à l'aide de`CreateTableElement()` méthode. Le code source du didacticiel fournit des exemples de personnalisation de diverses propriétés de l'élément de tableau, telles que la couleur d'arrière-plan, les bordures, l'alignement, la largeur des colonnes, etc.

#### Q : Puis-je personnaliser les styles et les propriétés des cellules du tableau dans l’élément de tableau ?

R : Oui, le didacticiel explique comment personnaliser les styles et les propriétés de l'élément de tableau dans son intégralité, y compris les en-têtes, les lignes de corps et le pied de page. Cependant, il n'aborde pas spécifiquement la personnalisation des cellules individuelles du tableau.

#### Q : Comment puis-je ajouter des en-têtes, des lignes de corps et un pied de page à l’élément de tableau ?

R : Le didacticiel explique comment créer et ajouter des en-têtes, des lignes de corps et un pied de page à l’élément de tableau à l’aide des méthodes appropriées fournies par Aspose.PDF pour .NET.

#### Q : Qu’est-ce que la conformité PDF/UA et comment puis-je la valider pour mon document PDF balisé ?

 R : La conformité PDF/UA garantit que le document PDF est conforme aux normes d'accessibilité, ce qui le rend plus accessible aux utilisateurs handicapés. Le didacticiel montre comment valider la conformité PDF/UA à l'aide de`Validate()` méthode et générer un rapport de conformité XML.

#### Q : Comment puis-je intégrer ces concepts dans mes propres applications .NET ?

R : Vous pouvez utiliser les exemples de code source C# fournis comme guide pour implémenter le formatage des éléments de tableau dans vos propres applications .NET. Modifiez et adaptez le code pour qu'il corresponde à vos besoins et intégrez-le dans vos projets.

#### Q : Existe-t-il des bonnes pratiques recommandées pour la mise en forme des éléments de tableau dans les documents PDF ?

R : Lors de la mise en forme des éléments de tableau (tableaux), tenez compte de la lisibilité et de l'accessibilité du contenu. Utilisez des polices claires et lisibles, des couleurs appropriées et maintenez une mise en page cohérente. Validez la conformité PDF/UA pour garantir le respect des normes d'accessibilité.

#### Q : Quelles autres fonctionnalités d’Aspose.PDF pour .NET puis-je explorer pour la personnalisation des documents PDF ?

R : Aspose.PDF pour .NET propose une gamme de fonctionnalités pour la personnalisation des documents PDF, notamment la manipulation de texte, l'insertion d'images, la gestion des champs de formulaire, les signatures numériques, les annotations, etc. Consultez la documentation et les ressources officielles pour découvrir des fonctionnalités supplémentaires.