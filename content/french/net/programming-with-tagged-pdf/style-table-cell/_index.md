---
title: Style de cellule de tableau
linktitle: Style de cellule de tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment appliquer un style aux cellules d'un tableau avec Aspose.PDF pour .NET. Guide étape par étape pour créer et personnaliser des tableaux.
type: docs
weight: 160
url: /fr/net/programming-with-tagged-pdf/style-table-cell/
---
Bienvenue dans ce didacticiel détaillé sur la mise en forme des cellules de tableau à l'aide d'Aspose.PDF pour .NET. Dans ce guide, nous expliquerons en détail chaque étape du code source C# fourni pour vous aider à comprendre comment styliser les cellules de tableau. Assurez-vous d'avoir installé Aspose.PDF pour .NET et configuré votre environnement de développement avant de commencer.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Nous avons créé un nouveau document et défini le titre et la langue du document.

## Étape 3 : Obtention de l'élément de structure racine

Dans cette étape, nous obtiendrons l’élément de structure racine de notre document.

```csharp
//Obtenir l'élément de structure racinaire
StructureElement rootElement = taggedContent.RootElement;
```

Nous avons obtenu l’élément de structure racine qui servira de conteneur pour les éléments du tableau.

## Étape 4 : Création de l'élément de structure du tableau

Créons maintenant un nouvel élément de structure de tableau pour notre document.

```csharp
// Créer l'élément de structure du tableau
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Nous avons créé un nouvel élément de structure de tableau et l'avons ajouté à l'élément de structure racine. Nous avons également créé les éléments d'en-tête, de corps et de pied de page du tableau.

## Étape 5 : Ajout d'en-têtes de tableau

Dans cette étape, nous allons ajouter les en-têtes de tableau à notre tableau.

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

## Étape 6 : Ajout des lignes du corps du tableau

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

Nous avons ajouté des lignes au corps du tableau en utilisant des boucles pour parcourir chaque cellule du tableau. Nous avons défini les propriétés de mise en forme de chaque cellule, telles que la couleur d'arrière-plan, les bordures, les marges, l'alignement du texte, etc.

## Étape 7 : Ajout du pied de page

Enfin, nous ajouterons le pied de page à notre tableau.

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



## Étape 8 : enregistrement du document PDF balisé

Maintenant que nous avons créé notre document avec le tableau stylisé, nous allons l'enregistrer en tant que document PDF balisé.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "StyleTableCell.pdf");
```

Nous avons enregistré le document PDF balisé dans le répertoire spécifié.

## Étape 9 : Validation de la conformité PDF/UA

Ensuite, nous validerons la conformité PDF/UA de notre document.

```csharp
// Vérification de conformité PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nous avons téléchargé le document PDF balisé et validé sa conformité PDF/UA en générant un rapport XML.

### Exemple de code source pour la cellule de tableau de style à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin vers le répertoire des documents.
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

Dans ce didacticiel, nous avons appris à appliquer un style aux cellules d'un tableau à l'aide d'Aspose.PDF pour .NET. Nous avons vu comment créer un document, ajouter un tableau avec des en-têtes, des lignes de corps et un pied de page, et personnaliser les styles de cellule. Enfin, nous avons enregistré le document PDF balisé et validé sa conformité PDF/UA. Vous pouvez désormais utiliser Aspose.PDF pour .NET pour créer et appliquer un style aux tableaux dans vos applications .NET.

### FAQ

#### Q : Quel est le but de ce tutoriel sur la mise en forme des cellules de tableau à l’aide d’Aspose.PDF pour .NET ?

R : Ce didacticiel vise à fournir un guide complet sur la façon de styliser les cellules d'un tableau dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Il présente des instructions étape par étape et des exemples de code source C# pour vous aider à comprendre et à mettre en œuvre la mise en forme des cellules d'un tableau.

#### Q : Quels sont les prérequis pour suivre ce tutoriel ?

R : Avant de commencer, assurez-vous d'avoir installé Aspose.PDF pour .NET et d'avoir configuré votre environnement de développement. Cela inclut la configuration de votre projet pour référencer la bibliothèque Aspose.PDF.

#### Q : Comment créer un nouveau document PDF à l’aide d’Aspose.PDF pour .NET ?

 : Pour créer un nouveau document PDF, vous devez instancier un`Document` objet de la bibliothèque Aspose.PDF. Le code source C# fourni montre comment créer un document et définir son titre et sa langue.

#### Q : Quelle est la signification de l’élément de structure racine dans un document PDF ?

R : L'élément de structure racine sert de conteneur pour d'autres éléments de structure, aidant à organiser et à catégoriser le contenu du document PDF. Il joue un rôle crucial dans l'établissement de la structure logique du document.

#### Q : Comment puis-je créer un élément de structure de tableau et personnaliser son apparence à l'aide d'Aspose.PDF pour .NET ?

 A : Vous pouvez créer un élément de structure de tableau à l'aide de la`CreateTableElement()` méthode. Le code source fourni montre comment personnaliser l'apparence du tableau, y compris son en-tête, son corps et son pied de page, en définissant des propriétés telles que la couleur d'arrière-plan, les bordures, les marges et l'alignement.

#### Q : Puis-je ajouter plusieurs lignes et colonnes au corps du tableau et personnaliser leur formatage ?

R : Oui, le didacticiel montre comment ajouter plusieurs lignes et colonnes au corps du tableau à l'aide de boucles. Il fournit également des exemples de personnalisation de la mise en forme des cellules, comme la couleur d'arrière-plan, les bordures, l'alignement du texte, le style de police, etc.

#### Q : Quel est le but de la validation de la conformité PDF/UA et comment puis-je effectuer cette validation ?

 A : La validation de la conformité PDF/UA garantit que le document PDF respecte les normes d'accessibilité, le rendant ainsi plus accessible aux utilisateurs handicapés. Le didacticiel montre comment valider la conformité PDF/UA à l'aide de l'outil`Validate()` méthode et générer un rapport XML.

#### Q : Comment puis-je appliquer ces concepts à mes propres applications .NET ?

R : Vous pouvez utiliser les exemples de code source C# fournis comme guide pour implémenter la mise en forme des cellules de tableau dans vos propres applications .NET. Personnalisez le code selon vos besoins et intégrez-le dans vos projets.

#### Q : Existe-t-il des bonnes pratiques recommandées pour styliser les cellules de tableau dans les documents PDF ?

R : Lorsque vous stylisez les cellules d'un tableau, tenez compte des besoins de votre public, notamment des exigences en matière d'accessibilité. Utilisez des couleurs contrastées, des polices appropriées et un alignement clair des cellules pour améliorer la lisibilité. En outre, validez la conformité PDF/UA pour garantir le respect des normes d'accessibilité.

#### Q : Quelles autres fonctionnalités d’Aspose.PDF pour .NET puis-je explorer pour la manipulation de documents PDF ?

R : Aspose.PDF pour .NET offre une large gamme de fonctionnalités pour la manipulation de documents PDF, notamment l'extraction de texte, l'insertion d'images, la gestion des champs de formulaire, les signatures numériques, etc. Explorez la documentation officielle et les ressources pour en savoir plus sur les fonctionnalités supplémentaires.
