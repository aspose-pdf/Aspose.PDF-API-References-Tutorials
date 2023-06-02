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

### Exemple de code source pour PDF vers SVG en utilisant Aspose.Words pour .NET

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