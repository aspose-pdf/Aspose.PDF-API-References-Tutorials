---
title: Table à coins arrondis dans un document PDF
linktitle: Table à coins arrondis dans un document PDF
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
// Créer un objet GraphInfo pour définir la couleur de la bordure
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

### FAQ pour la table à coins arrondis dans le document PDF

#### Q : Puis-je personnaliser le rayon des coins arrondis du tableau ?

 : Oui, vous pouvez personnaliser le rayon des coins arrondis du tableau en modifiant la valeur du`bInfo.RoundedBorderRadius` propriété dans le code source C# fourni. Définissez simplement la valeur de rayon souhaitée (en points) pour obtenir l'apparence de coin arrondi souhaitée.

#### Q : Puis-je appliquer des coins arrondis à des cellules individuelles du tableau ?

R : Non, le style de coin arrondi est appliqué à l'ensemble du tableau dans son ensemble. Aspose.PDF pour .NET ne fournit actuellement pas de prise en charge intégrée pour l'application de coins arrondis à des cellules individuelles dans le tableau.

#### Q : Puis-je changer la couleur de la bordure des coins arrondis ?

 R : Oui, vous pouvez changer la couleur de la bordure des coins arrondis en modifiant la valeur du`graph.Color` propriété dans le code source C#. Fournissez simplement la couleur souhaitée, telle que`Aspose.Pdf.Color.Red` ou toute autre représentation de couleur valide.

#### Q : Est-il possible d'appliquer différents styles de coin (par exemple, carré et arrondi) à différents tableaux dans le même document PDF ?

: Oui, il est possible d'appliquer différents styles de coin à différents tableaux dans le même document PDF. Vous pouvez créer plusieurs tables et configurer leurs styles de coin individuellement en fonction de vos besoins.

#### Q : Puis-je ajuster l'épaisseur de la bordure des coins arrondis ?

 R : Oui, vous pouvez ajuster l'épaisseur de la bordure des coins arrondis en modifiant le`BorderInfo` propriétés de l'objet dans le code source C#. Par exemple, vous pouvez définir le`bInfo.Width` propriété pour ajuster l'épaisseur de la bordure.