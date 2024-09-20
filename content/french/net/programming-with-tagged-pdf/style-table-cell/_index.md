---
title: Style de cellule de tableau
linktitle: Style de cellule de tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment appliquer un style aux cellules d'un tableau PDF à l'aide d'Aspose.PDF pour .NET grâce à ce didacticiel détaillé. Suivez les instructions pour créer et formater de magnifiques tableaux PDF.
type: docs
weight: 160
url: /fr/net/programming-with-tagged-pdf/style-table-cell/
---
## Introduction

Créer des tableaux PDF d'aspect professionnel peut s'avérer compliqué, mais avec Aspose.PDF pour .NET, c'est étonnamment simple ! Que vous souhaitiez styliser des en-têtes, des pieds de page ou des cellules de tableau spécifiques, cette puissante bibliothèque vous fournit tous les outils dont vous avez besoin pour créer des documents PDF magnifiquement formatés. Dans ce didacticiel, nous vous expliquerons comment styliser les cellules d'un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ne vous inquiétez pas, nous allons tout décomposer en étapes faciles à suivre.

## Prérequis

Avant de plonger dans le code, assurez-vous d'avoir les prérequis suivants :

1. Aspose.PDF pour .NET : Téléchargez et installez la dernière version d'Aspose.PDF depuis[ici](https://releases.aspose.com/pdf/net/).
2. IDE (comme Visual Studio) : configurer un environnement de développement .NET.
3. Connaissances de base de la programmation C# : Une certaine familiarité avec C# est requise.
4.  Licence Aspose.PDF : obtenez une licence temporaire ou complète pour accéder à toutes les fonctionnalités de la bibliothèque. Vous pouvez obtenir un essai gratuit[ici](https://purchase.aspose.com/temporary-license/).

## Paquets d'importation

Avant de commencer, assurez-vous d'importer les espaces de noms nécessaires. Vous aurez besoin des éléments suivants dans votre projet :

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant que tout est configuré, passons au guide étape par étape !

Nous allons créer un tableau dans un document PDF et styliser ses cellules. Chaque étape expliquera le processus en détail.

## Étape 1 : Créer un nouveau document PDF

 La première étape consiste à créer un nouveau document PDF. Dans Aspose.PDF, vous pouvez initialiser un nouveau`Document` objet, qui représente votre fichier PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un nouveau document PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Ici, nous initialisons un document PDF et définissons son titre et sa langue. Cela donne à votre document une structure appropriée, essentielle pour la conformité PDF/UA.

## Étape 2 : Configurer la structure du tableau

Les tableaux dans les PDF sont définis dans des éléments de structure. Créons le tableau et définissons les lignes et les colonnes du tableau.

```csharp
// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;

// Créer un élément de structure de table
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Nous avons maintenant défini l'en-tête de la table (`TableTHeadElement`), corps (`TableTBodyElement`), et le pied (`TableTFootElement`) sections. Vous pouvez les considérer comme le squelette de votre table.

## Étape 3 : styliser les cellules d'en-tête

Le style des cellules d'en-tête les fait ressortir. Ici, nous appliquons des couleurs d'arrière-plan, des bordures et un alignement du texte.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Dans cette étape, nous parcourons chaque cellule d'en-tête, en lui attribuant un arrière-plan vert-jaune, une bordure grise et un texte aligné à droite. Vous pouvez ajuster ces propriétés pour qu'elles correspondent à la conception souhaitée.

## Étape 4 : Remplir et styliser le corps du tableau

Le corps du tableau contient les données réelles. Voici comment vous pouvez styliser chaque cellule avec des marges, des bordures et des paramètres de texte spécifiques.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Dans cette étape, nous remplissons le corps du tableau avec quatre lignes et stylisons chaque cellule avec des arrière-plans jaunes et du texte bleu gras centré. Nous utilisons également le`MarginInfo`classe pour définir le remplissage autour du texte.

## Étape 5 : styliser le pied de page

Pour donner au tableau une structure complète, nous ajoutons et stylisons les cellules de pied de page, tout comme nous l'avons fait avec l'en-tête.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

La section du pied de page est conçue de manière similaire à l'en-tête, ce qui permet aux lecteurs de suivre facilement la structure du tableau.

## Étape 6 : Enregistrer et valider le document PDF

Enfin, nous enregistrons le document PDF et vérifions s'il est conforme PDF/UA.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "StyleTableCell.pdf");

// Vérification de la conformité PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Nous sauvegardons le PDF et utilisons le`Validate` méthode pour garantir qu'elle répond aux normes d'accessibilité (conformité PDF/UA).

## Conclusion

La mise en forme des tableaux dans un PDF à l'aide d'Aspose.PDF pour .NET est à la fois puissante et flexible. Avec quelques lignes de code, vous pouvez créer des conceptions de tableau personnalisées qui mettront en valeur vos documents PDF. De la personnalisation des bordures et des arrière-plans des cellules à la garantie de la conformité en matière d'accessibilité, Aspose.PDF facilite la création de fichiers PDF soignés.

## FAQ

### Puis-je appliquer différents styles à des cellules de tableau individuelles ?  
Oui, vous pouvez styliser des cellules individuelles en personnalisant les`TableTDElement` propriétés.

### Comment puis-je fusionner des cellules d’un tableau ?  
 Vous pouvez utiliser le`ColSpan` et`RowSpan` propriétés pour fusionner les cellules d'un tableau.

### Est-il possible de créer un tableau compatible PDF/UA ?  
 Oui, comme démontré dans ce guide, vous pouvez garantir la conformité PDF/UA en validant votre document à l'aide de l'`Validate` méthode.

### Puis-je utiliser différentes polices dans les cellules du tableau ?  
 Absolument ! Vous pouvez spécifier différentes polices à l'aide de la`TextState` objet pour chaque cellule.

### Comment télécharger Aspose.PDF pour .NET ?  
 Vous pouvez le télécharger à partir du[page des communiqués](https://releases.aspose.com/pdf/net/).