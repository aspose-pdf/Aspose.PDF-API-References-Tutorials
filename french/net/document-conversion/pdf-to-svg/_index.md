---
title: PDF vers SVG
linktitle: PDF vers SVG
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en SVG en utilisant Aspose.PDF pour .NET.
type: docs
weight: 180
url: /fr/net/document-conversion/pdf-to-svg/
---
Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un format PDF au format SVG à l'aide d'Aspose.PDF pour .NET. SVG (Scalable Vector Graphics) est un format d'image vectorielle qui aide à maintenir la qualité et la mise à l'échelle des graphiques. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDF au format SVG.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDF
Dans cette étape, nous allons charger le fichier PDF source en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Instanciation des options de sauvegarde SVG
Après avoir chargé le fichier PDF, nous allons instancier les options de sauvegarde SVG. Utilisez le code suivant :

```csharp
// Instancier un objet SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Ne pas compresser l'image SVG dans une archive Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Étape 3 : Enregistrer le fichier SVG résultant
Nous allons maintenant enregistrer le fichier PDF converti au format SVG. Utilisez le code suivant :

```csharp
// Enregistrer la sortie dans des fichiers SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Le code ci-dessus enregistre le format PDF converti au format SVG avec le nom de fichier`"PDFToSVG_out.svg"`.

### Exemple de code source pour PDF vers SVG en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF
Document doc = new Document(dataDir + "input.pdf");
// Instancier un objet de SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Ne pas compresser l'image SVG en archive Zip
saveOptions.CompressOutputToZipArchive = false;
// Enregistrez la sortie dans des fichiers SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format SVG à l'aide de Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir un fichier PDF au format SVG. Cette fonctionnalité est utile lorsque vous souhaitez conserver la qualité et la mise à l'échelle des graphiques lors de la conversion en images vectorielles.

### FAQ

#### Q : Puis-je contrôler la résolution ou la taille des fichiers SVG résultants lors de la conversion PDF en SVG ?

 R : Oui, vous pouvez contrôler la résolution ou la taille des fichiers SVG résultants lors de la conversion PDF en SVG à l'aide d'Aspose.PDF pour .NET. Le`SvgSaveOptions` classe fournit des propriétés telles que`PageSavingCallback` et`SaveFormat` qui vous permettent de définir la résolution, la taille de la page ou d'autres paramètres liés à la sortie SVG. Vous pouvez personnaliser ces options en fonction de vos besoins pour contrôler la qualité et la taille des fichiers SVG.

#### Q : Aspose.PDF pour .NET prend-il en charge la conversion de fichiers PDF cryptés ou protégés par mot de passe en SVG ?

 : Oui, Aspose.PDF pour .NET prend en charge la conversion de fichiers PDF cryptés ou protégés par mot de passe au format SVG. Lorsque vous chargez un fichier PDF protégé par mot de passe, vous pouvez fournir le mot de passe à l'aide du`Document` constructeur de classe ou en définissant le`Password` propriété avant de charger le PDF. Aspose.PDF pour .NET gérera le décryptage pendant le processus de conversion PDF en SVG.

#### Q : Puis-je convertir uniquement des pages spécifiques du PDF en SVG au lieu du document entier ?

R : Oui, vous pouvez convertir uniquement des pages spécifiques du PDF en SVG au lieu du document entier en utilisant Aspose.PDF pour .NET. Avant d'enregistrer la sortie sous forme de fichiers SVG, vous pouvez sélectionner les pages que vous souhaitez convertir en spécifiant leurs numéros de page ou leurs plages. De cette façon, vous pouvez extraire et convertir uniquement les pages souhaitées du format PDF au format SVG.

#### Q : Aspose.PDF pour .NET est-il compatible avec toutes les versions de SVG ?

: Aspose.PDF pour .NET est conçu pour être compatible avec la spécification SVG 1.1 (Scalable Vector Graphics). Il prend en charge la génération de fichiers SVG selon la norme SVG 1.1. Cependant, veuillez noter que SVG 2.0 a été introduit comme la dernière version de la spécification SVG. Même si Aspose.PDF pour .NET peut toujours bien fonctionner avec SVG 2.0 dans de nombreux cas, il est recommandé de vérifier la compatibilité et les limitations potentielles avec les fonctionnalités SVG spécifiques que vous avez l'intention d'utiliser.