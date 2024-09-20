---
title: Créer un élément de tableau
linktitle: Créer un élément de tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour créer un élément de tableau avec Aspose.PDF pour .NET. Générez facilement des PDF dynamiques avec des tableaux.
type: docs
weight: 80
url: /fr/net/programming-with-tagged-pdf/create-table-element/
---
## Introduction

Vous êtes-vous déjà demandé comment créer et personnaliser sans effort des éléments de tableau dans un PDF à l'aide de .NET ? Eh bien, Aspose.PDF pour .NET est votre solution de référence ! Que vous automatisiez la génération de rapports ou que vous créiez dynamiquement des tableaux pour divers documents, Aspose.PDF fournit une API riche pour travailler avec des éléments de tableau. Ce guide vous guidera étape par étape sur la façon de créer un tableau, de le styliser et même de vous assurer qu'il est conforme aux normes de conformité PDF/UA. Cela semble passionnant, n'est-ce pas ? Plongeons-nous directement dans le vif du sujet !

## Prérequis

Avant de commencer, vous aurez besoin de quelques éléments en place :
1.  Aspose.PDF pour .NET : Téléchargez la dernière version à partir de[Téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : tout IDE pris en charge par .NET (par exemple, Visual Studio).
3. Connaissances de base de C# : Une familiarité avec la programmation C# est recommandée.

 Enfin, n'oubliez pas votre licence Aspose.PDF. Si vous n'en avez pas, vous pouvez utiliser la[essai gratuit](https://releases.aspose.com/) ou demander un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour tout tester.

## Paquets d'importation

Tout d'abord, nous allons importer les packages nécessaires. Cela nous permettra de travailler avec toutes les classes pertinentes pour créer des tableaux dans des documents PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dans cette section, nous allons décomposer le processus de création d'une table en plusieurs étapes. Chaque étape se concentre sur différentes parties du processus de création et de personnalisation de la table.

## Étape 1 : Créer un nouveau document PDF

La première chose à faire est de créer un nouveau document PDF. Il servira de conteneur pour notre tableau.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un nouveau document PDF
Document document = new Document();
```

 Ici, nous initialisons une nouvelle instance du`Document` classe, qui sera notre fichier PDF vierge. N'oubliez pas de définir le chemin de votre fichier !

## Étape 2 : Configurer le contenu balisé

Ensuite, nous devons activer le contenu balisé, ce qui garantit l'accessibilité du tableau. Les PDF balisés sont nécessaires pour la conformité avec PDF/UA (accessibilité universelle).

```csharp
// Activer le contenu balisé
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Cette étape définit le titre et la langue du document, garantissant ainsi la conformité du tableau aux normes d'accessibilité. L'accessibilité des documents est essentielle pour l'expérience utilisateur et les exigences légales dans certains secteurs.

## Étape 3 : Créer l’élément de tableau

Vient maintenant la partie amusante : créer la table elle-même !

```csharp
// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Ici, nous utilisons le`RootElement` du contenu balisé pour ajouter notre tableau. Il s'agit essentiellement d'ajouter un tableau en tant que nœud enfant à la structure du document.

## Étape 4 : Personnaliser les bordures et les en-têtes du tableau

Vous ne voulez pas que votre table paraisse fade, n'est-ce pas ? Ajoutons un peu de style !

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Nous définissons des bordures et ajoutons des en-têtes, du corps et des pieds de page au tableau. Notez l'utilisation de`BorderInfo` pour styliser les bordures du tableau avec une couleur bleu foncé.

## Étape 5 : ajouter des lignes et des cellules au tableau

Maintenant, remplissons notre tableau avec des lignes et des cellules. Cette partie du processus est celle où nous définissons la disposition de notre tableau.

### Étape 5.1 : Créer une ligne d’en-tête

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Nous créons une ligne d'en-tête avec 4 colonnes, et chaque cellule d'en-tête est stylisée avec une couleur d'arrière-plan de`GreenYellow`Nous définissons également une bordure et un alignement pour les en-têtes.

### Étape 5.2 : Ajouter des lignes de corps

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Ici, nous créons dynamiquement 50 lignes et 4 colonnes, les remplissons de texte et stylisons les cellules. La couleur d'arrière-plan est définie sur jaune, avec le texte centré.

### Étape 5.3 : Ajouter une ligne de pied de page

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Pour compléter le tableau, nous ajoutons un pied de page avec un texte centré et un`LightSeaGreen` arrière-plan.

## Étape 6 : Valider la conformité PDF/UA

Une fois le tableau créé, il est essentiel de s'assurer que le PDF est conforme à la norme PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Valider la conformité PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Cet extrait enregistre le fichier PDF et vérifie s'il est conforme aux normes PDF/UA. Si le document est conforme, il est accessible aux utilisateurs handicapés.

## Conclusion

Félicitations ! Vous avez réussi à créer un tableau entièrement personnalisé dans un PDF à l'aide d'Aspose.PDF pour .NET. Du style du tableau à la conformité PDF/UA, vous disposez désormais d'une base solide pour générer des tableaux dynamiques dans vos documents PDF. N'oubliez pas d'explorer les nombreuses fonctionnalités d'Aspose.PDF pour améliorer encore davantage vos documents !

## FAQ

### Puis-je personnaliser la police et le style du texte du tableau ?
Oui, Aspose.PDF vous permet de personnaliser entièrement les polices, les styles de texte et l'alignement à l'aide de`TextState` classe.

### Comment ajouter dynamiquement des colonnes ou des lignes ?
 Vous pouvez ajuster le nombre de colonnes ou de lignes en modifiant le`rowIndex` et`colIndex` dans les boucles.

### Est-il possible de fusionner des cellules dans le tableau ?
 Oui, vous pouvez utiliser le`ColSpan` et`RowSpan` propriétés permettant de fusionner des cellules sur des colonnes ou des lignes.

### Qu'est-ce que la conformité PDF/UA ?
La conformité PDF/UA garantit que le document est accessible aux utilisateurs handicapés, conformément aux normes internationales d'accessibilité.

### Comment tester la conformité PDF/UA dans Aspose.PDF ?
 Vous pouvez utiliser le`Validate` méthode pour vérifier si le document est conforme aux normes PDF/UA.