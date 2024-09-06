---
title: Table à coins arrondis dans un document PDF
linktitle: Table à coins arrondis dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-tables/rounded-corner-table/
---
Dans ce tutoriel, nous vous guiderons étape par étape pour créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Création du tableau
Tout d’abord, nous allons créer la table en utilisant le code suivant :

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Étape 2 : Configuration du style de coins arrondis
Ensuite, nous allons configurer le style des coins arrondis du tableau :

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Étape 3 : Configuration de la bordure du tableau
Pour donner au tableau une bordure aux coins arrondis, nous devons créer un objet BorderInfo et le configurer avec les paramètres appropriés :

```csharp
// Créez un objet GraphInfo pour définir la couleur de la bordure
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Créer un objet BorderInfo vide
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Définissez le rayon de la bordure arrondie à 15
bInfo.RoundedBorderRadius = 15;

// Appliquer les informations de bordure au tableau
tab1.Border = bInfo;
```

### Exemple de code source pour une table à coins arrondis à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Créer un objet BorderInfo vide
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Définissez une bordure plus arrondie où le rayon du rond est de 15
bInfo.RoundedBorderRadius = 15;
// Définissez le style de coin de la table comme rond.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Définir les informations de bordure du tableau
tab1.Border = bInfo;
```

## Conclusion
Félicitations ! Vous avez maintenant appris à créer un tableau à coins arrondis dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment configurer le style de coins arrondis et la bordure du tableau. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.

### FAQ pour la table à coins arrondis dans le document PDF

#### Q : Puis-je personnaliser le rayon des coins arrondis de la table ?

 : Oui, vous pouvez personnaliser le rayon des coins arrondis de la table en modifiant la valeur du`bInfo.RoundedBorderRadius` propriété dans le code source C# fourni. Définissez simplement la valeur de rayon souhaitée (en points) pour obtenir l'apparence de coin arrondi souhaitée.

#### Q : Puis-je appliquer des coins arrondis à des cellules individuelles du tableau ?

R : Non, le style de coins arrondis s'applique à l'ensemble du tableau. Aspose.PDF pour .NET ne fournit actuellement pas de prise en charge intégrée pour l'application de coins arrondis à des cellules individuelles du tableau.

#### Q : Puis-je changer la couleur de la bordure des coins arrondis ?

 R : Oui, vous pouvez modifier la couleur de la bordure des coins arrondis en modifiant la valeur de la`graph.Color` propriété dans le code source C#. Fournissez simplement la couleur souhaitée, par exemple`Aspose.Pdf.Color.Red` ou toute autre représentation de couleur valide.

#### Q : Est-il possible d'appliquer différents styles d'angle (par exemple, carrés et arrondis) à différents tableaux dans le même document PDF ?

: Oui, il est possible d'appliquer différents styles d'angle à différents tableaux dans le même document PDF. Vous pouvez créer plusieurs tableaux et configurer leurs styles d'angle individuellement en fonction de vos besoins.

#### Q : Puis-je ajuster l’épaisseur de la bordure des coins arrondis ?

 R : Oui, vous pouvez ajuster l'épaisseur de la bordure des coins arrondis en modifiant le`BorderInfo` propriétés de l'objet dans le code source C#. Par exemple, vous pouvez définir le`bInfo.Width` propriété permettant d'ajuster l'épaisseur de la bordure.