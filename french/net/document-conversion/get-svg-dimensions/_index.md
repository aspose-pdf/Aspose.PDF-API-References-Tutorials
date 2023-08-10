---
title: Obtenir les cotes SVG
linktitle: Obtenir les cotes SVG
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour obtenir des dimensions SVG à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/document-conversion/get-svg-dimensions/
---
## Introduction
Dans ce didacticiel, nous vous expliquerons comment obtenir les dimensions d'un fichier SVG à l'aide d'Aspose.PDF pour .NET. SVG (Scalable Vector Graphics) est un format d'image basé sur XML utilisé pour représenter des graphiques vectoriels. En suivant les étapes ci-dessous, vous pourrez obtenir les dimensions d'un fichier SVG et les enregistrer au format PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du fichier SVG
Dans cette étape, nous allons charger le fichier SVG en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier SVG.

## Étape 2 : Ajustement de la taille de la page
Maintenant que nous avons chargé le fichier SVG, nous pouvons ajuster la taille de la page pour accueillir le contenu SVG. Utilisez le code suivant :

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Le code ci-dessus définit les marges de la page sur zéro, permettant à la taille de la page de s'ajuster en fonction du contenu SVG.

## Étape 3 : Enregistrer le PDF résultant
Après avoir ajusté la taille de la page, nous pouvons maintenant enregistrer le document PDF résultant. Voici la dernière étape :

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier PDF de sortie.
  
### Exemple de code source pour Get SVG Dimensions en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape d'obtention des dimensions d'un fichier SVG à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure d'obtenir les dimensions d'un fichier SVG et de les enregistrer au format PDF. Cette fonctionnalité peut être utile lorsque vous devez mesurer les dimensions d'un graphique vectoriel.

### FAQ

#### Q : Qu'est-ce que le SVG ?

R : SVG (Scalable Vector Graphics) est un format d'image basé sur XML utilisé pour représenter des graphiques vectoriels. Contrairement aux images raster, les fichiers SVG sont indépendants de la résolution et peuvent être mis à l'échelle sans perte de qualité. SVG est largement utilisé pour afficher des graphiques sur le Web et peut être modifié et manipulé facilement.

#### Q : Pourquoi utiliser Aspose.PDF pour .NET pour la conversion SVG en PDF ?

R : Aspose.PDF pour .NET fournit un moyen fiable et efficace de gérer les fichiers SVG et de les convertir au format PDF. Il offre diverses options et paramètres pour personnaliser le processus de conversion, tels que l'ajustement de la taille de la page, des marges et d'autres propriétés pour assurer une représentation précise dans le PDF.

#### Q : Puis-je convertir des fichiers SVG avec des graphiques et du texte complexes ?

R : Oui, Aspose.PDF pour .NET peut gérer les fichiers SVG avec des éléments graphiques, textuels et vectoriels complexes. Il préserve avec précision les détails et la qualité du contenu SVG pendant le processus de conversion, ce qui donne des documents PDF de haute qualité.

#### Q : Est-il possible d'extraire du texte de fichiers SVG avec Aspose.PDF pour .NET ?

R : Oui, Aspose.PDF pour .NET vous permet d'extraire du texte à partir de fichiers SVG. Vous pouvez utiliser les fonctionnalités d'extraction de texte de la bibliothèque pour extraire des éléments de texte de SVG et les enregistrer séparément pour un traitement ultérieur.