---
title: Style de ligne du tableau
linktitle: Style de ligne du tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment styliser les lignes de tableau dans un PDF à l'aide d'Aspose.PDF pour .NET avec un guide étape par étape pour améliorer facilement la mise en forme de votre document.
type: docs
weight: 180
url: /fr/net/programming-with-tagged-pdf/style-table-row/
---
## Introduction

Pour créer des documents PDF bien structurés et joliment formatés, Aspose.PDF pour .NET est une solution incontournable. Que vous automatisiez des rapports, des factures ou que vous créiez des tableaux dynamiques, la mise en forme de tableaux avec différents styles est essentielle pour un document soigné. Dans ce didacticiel, nous allons nous plonger dans le style d'une ligne de tableau à l'aide d'Aspose.PDF pour .NET. Et ne vous inquiétez pas, je vous guiderai étape par étape, comme une bonne conversation autour d'un café !

## Prérequis

Avant de passer aux choses sérieuses, assurons-nous que vous avez tout prévu. Vous aurez besoin de :

1. Bibliothèque Aspose.PDF pour .NET  
    Si vous ne l'avez pas déjà, vous pouvez le récupérer à partir de[ici](https://releases.aspose.com/pdf/net/) . Vous pouvez également obtenir un[essai gratuit](https://releases.aspose.com/) pour commencer.
2. Environnement de développement  
   Installez Visual Studio ou tout autre IDE C# de votre choix. Vous aurez également besoin d'installer .NET, mais je suppose que vous le connaissez déjà.
3. Connaissances de base de C# et .NET  
   Une bonne compréhension de C# rendra ce tutoriel facile. Mais ne vous inquiétez pas, je vais vous expliquer chaque étape en détail !

## Paquets d'importation

Avant de pouvoir commencer à travailler avec Aspose.PDF, nous devons importer les espaces de noms nécessaires. Dans votre projet C#, assurez-vous d'inclure les éléments suivants :

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ceux-ci sont essentiels pour créer et styliser le tableau et, bien sûr, pour travailler avec du contenu balisé pour plus de conformité.

Décomposons maintenant la tâche étape par étape, afin que vous puissiez styliser les lignes de votre tableau comme un pro !

## Étape 1 : Créer un nouveau document PDF

Tout d'abord, créons un tout nouveau document PDF. Ce document contiendra toutes les lignes stylisées du tableau.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document
Document document = new Document();
```

 Ici, nous initialisons simplement un nouveau`Document` objet qui représentera notre fichier PDF. Assurez-vous de définir le chemin du répertoire où vous enregistrerez vos fichiers de sortie.

## Étape 2 : travailler avec du contenu balisé

Pour structurer votre PDF en vue de son accessibilité, nous utiliserons du contenu balisé. Cela permet de créer des éléments structurés tels que des tableaux, garantissant ainsi leur conformité aux normes d'accessibilité telles que PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Ici, nous définissons le titre et la langue du contenu balisé du PDF. C'est comme si vous donniez un nom à votre PDF et lui disiez dans quelle langue il doit être écrit !

## Étape 3 : Définir la structure du tableau

Ensuite, définissons la structure du tableau que nous sommes sur le point de créer. Chaque tableau a besoin d'un en-tête, d'un corps et d'un pied de page, un peu comme un article de blog bien organisé !

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

Ce que nous faisons ici est de créer un tableau avec un en-tête (`THead`), corps (`TBody`), et le pied de page (`TFoot`). Ces éléments vont contenir nos lignes.

## Étape 4 : ajouter la ligne d’en-tête du tableau

Les tableaux sans en-têtes sont comme des livres sans titres. Commençons par créer la ligne d'en-tête pour donner un contexte aux données.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Ici, nous parcourons et ajoutons trois cellules d'en-tête (`TableTHElement`), en donnant à chacun un texte descriptif. Simple, non ?

## Étape 5 : ajouter des lignes de corps stylisées

Vient maintenant la partie amusante : styliser les lignes ! Créons sept lignes avec des styles personnalisés. Nous allons définir les couleurs d'arrière-plan, les bordures, le remplissage et l'alignement du texte.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Couleur de fond : Nous avons utilisé un jaune verge d'or clair pour cette touche professionnelle mais chaleureuse.
- Bordures : Chaque ligne est dotée d'une bordure extérieure gris foncé et de bordures de cellule bleues pour un aspect net.
- Hauteur et remplissage : les hauteurs de ligne sont définies et un remplissage est ajouté pour une apparence nette.
- Sauts de page : pour rendre le tableau plus lisible, chaque deuxième ligne commence sur une nouvelle page.

## Étape 6 : ajouter la ligne de pied de page

Tout comme l'en-tête, le pied de page ancre le tableau. Créons-en un.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Nous parcourons simplement trois cellules de pied de page et ajoutons un peu de texte. Le texte alternatif pour le pied de page est « Rangée de pied » pour le rendre accessible.

## Étape 7 : Enregistrer le document PDF

Maintenant que la table est prête, il est temps de sauvegarder votre chef-d'œuvre !

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Comme ça, votre PDF est enregistré avec toutes les belles lignes de tableau que nous venons de styliser.

## Étape 8 : Valider la conformité PDF/UA

Pour garantir que notre PDF respecte les normes d'accessibilité, nous le validerons pour la conformité PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Cela garantit que votre PDF répond à la norme PDF/UA, le rendant ainsi accessible à tous. L'accessibilité est le maître mot !

## Conclusion

Et voilà ! Avec seulement quelques lignes de code, vous avez créé un tableau entièrement stylisé dans un PDF à l'aide d'Aspose.PDF pour .NET. Des en-têtes aux pieds de page, nous avons stylisé chaque ligne, ajouté des éléments d'accessibilité et même validé la conformité du document. Que vous travailliez sur des rapports d'entreprise, des présentations ou que vous vous amusiez simplement avec des PDF, ce guide vous couvre. Maintenant, allez-y et commencez à styliser vos tableaux comme un pro !

## FAQ

### Puis-je également modifier le style de police du tableau ?  
 Oui ! Vous pouvez modifier le style de police à l'aide de la`TextState` objet pour chaque cellule, permettant une personnalisation complète.

### Comment ajouter plus de colonnes à mon tableau ?  
 Il suffit d'ajuster le`colCount`variable et ajoutez plus de cellules dans les boucles pour les en-têtes, le corps et les pieds de page.

### Que se passe-t-il si je ne définis pas la hauteur de ligne ?  
Si vous ne définissez pas la hauteur des lignes, le tableau s'ajustera automatiquement en fonction du contenu.

### Puis-je l'utiliser pour un nombre dynamique de lignes ?  
Absolument ! Vous pouvez récupérer des données à partir d'une base de données ou de toute autre source et ajuster dynamiquement le nombre de lignes et de colonnes.

### L'utilisation d'Aspose.PDF pour .NET est-elle gratuite ?  
 Aspose.PDF pour .NET est un produit sous licence, mais vous pouvez l'essayer avec un[essai gratuit](https://releases.aspose.com/) ou obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/).