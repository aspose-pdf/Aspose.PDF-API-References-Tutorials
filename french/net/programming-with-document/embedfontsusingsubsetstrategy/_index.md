---
title: Incorporer des polices à l'aide de la stratégie de sous-ensemble
linktitle: Incorporer des polices à l'aide de la stratégie de sous-ensemble
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à incorporer des polices dans un fichier PDF avec Subset Strategy en utilisant Aspose.PDF pour .NET. Optimisez la taille de votre PDF en incorporant uniquement les caractères nécessaires.
type: docs
weight: 130
url: /fr/net/programming-with-document/embedfontsusingsubsetstrategy/
---

Dans ce didacticiel, nous expliquerons comment incorporer des polices dans un fichier PDF avec une stratégie de sous-ensemble à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des documents PDF par programme. L'intégration de polices dans un fichier PDF est une étape importante pour garantir que le document s'affiche correctement sur différents appareils, que les polices requises soient installées ou non sur ces appareils.

## Étape 1 : Créer une nouvelle application de console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez le nommer comme bon vous semble. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : charger un fichier PDF existant
Pour incorporer des polices dans un fichier PDF existant, vous devez charger ce fichier à l'aide de la classe Document. Le code suivant montre comment charger un fichier PDF existant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Intégrer des polices avec une stratégie de sous-ensemble
Aspose.PDF pour .NET propose deux stratégies d'incorporation de polices : SubsetAllFonts et SubsetEmbeddedFontsOnly.

La stratégie SubsetAllFonts incorporera toutes les polices dans le document en tant que sous-ensemble. Un sous-ensemble est une partie de la police qui contient uniquement les caractères utilisés dans le document. Cette stratégie est utile pour réduire la taille du fichier du document PDF.

La stratégie SubsetEmbeddedFontsOnly incorporera uniquement le sous-ensemble de polices déjà incorporées dans le document. Si une police n'est pas intégrée, elle ne sera pas affectée par cette stratégie.

Le code suivant montre comment incorporer des polices dans un fichier PDF avec une stratégie de sous-ensemble :

```csharp
// Toutes les polices seront intégrées en tant que sous-ensemble dans le document en cas de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Le sous-ensemble de polices sera intégré pour les polices entièrement intégrées, mais les polices qui ne sont pas intégrées au document ne seront pas affectées.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Étape 5 : Enregistrez le document PDF
Une fois que vous avez intégré toutes les polices dans le fichier PDF avec une stratégie de sous-ensemble, vous devez enregistrer le document. Le code suivant montre comment enregistrer le fichier PDF :

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Exemple de code source pour l'intégration de polices avec une stratégie de sous-ensemble à l'aide d'Aspose.PDF pour .NET. 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Toutes les polices seront intégrées en tant que sous-ensemble dans le document en cas de SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Le sous-ensemble de polices sera intégré pour les polices entièrement intégrées, mais les polices qui ne sont pas intégrées au document ne seront pas affectées.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusion
Dans cet article, nous avons expliqué comment incorporer des polices dans un fichier PDF avec une stratégie de sous-ensemble à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, y compris l'ajout et l'intégration de polices avec différentes stratégies. L'intégration de polices dans un fichier PDF est une étape importante pour garantir que le document s'affiche correctement sur différents appareils, et la stratégie de sous-ensemble est une fonctionnalité utile pour réduire la taille du fichier du document PDF.

