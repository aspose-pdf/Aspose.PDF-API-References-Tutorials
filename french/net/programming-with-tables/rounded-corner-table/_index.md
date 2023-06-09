---
title: Table d'angle arrondie
linktitle: Table d'angle arrondie
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-tables/rounded-corner-table/
---

Dans ce didacticiel, nous vous guiderons pas à pas pour créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Etape 1 : Création du tableau
Tout d'abord, nous allons créer la table à l'aide du code suivant :

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Étape 2 : configuration du style de coin arrondi
Ensuite, nous allons configurer le style de coin arrondi pour le tableau :

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Étape 3 : Configuration de la bordure du tableau
Pour donner au tableau une bordure à coins arrondis, nous devons créer un objet BorderInfo et le configurer avec les paramètres appropriés :

```csharp
//Créer un objet GraphInfo pour définir la couleur de la bordure
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Créer un objet BorderInfo vide
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Définissez le rayon de la bordure arrondie sur 15
bInfo.RoundedBorderRadius = 15;

// Appliquer les informations de bordure au tableau
tab1.Border = bInfo;
```

### Exemple de code source pour Rounded Corner Table utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Créer un objet BorderInfo vide
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Définir la bordure une bordure plus ronde où le rayon du rond est de 15
bInfo.RoundedBorderRadius = 15;
// Définissez le style d'angle de la table sur Rond.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Définir les informations sur la bordure du tableau
tab1.Border = bInfo;
```

## Conclusion
Félicitation ! Vous avez maintenant appris à créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment configurer le style de coin arrondi et la bordure de tableau. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.