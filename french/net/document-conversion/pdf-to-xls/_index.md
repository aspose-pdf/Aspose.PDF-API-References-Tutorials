---
title: PDF vers XLS
linktitle: PDF vers XLS
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en XLS en utilisant Aspose.PDF pour .NET.
type: docs
weight: 200
url: /fr/net/document-conversion/pdf-to-xls/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDF au format XLS (Microsoft Excel) à l'aide d'Aspose.PDF pour .NET. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDF au format XLS.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : instancier les options de sauvegarde Excel
Après avoir chargé le fichier PDF, nous allons instancier les options de sauvegarde Excel. Utilisez le code suivant :

```csharp
// Instancier un objet ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Étape 3 : Enregistrer le fichier XLS résultant
Nous allons maintenant enregistrer le fichier PDF converti au format XLS. Utilisez le code suivant :

```csharp
// Enregistrez la sortie au format XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Le code ci-dessus enregistre le fichier PDF converti au format XLS avec le nom de fichier`"PDFToXLS_out.xls"`.

### Exemple de code source pour PDF vers XLS en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instancier l'objet ExcelSave Option
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Enregistrez la sortie au format XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format XLS à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir un fichier PDF au format XLS. Cette fonctionnalité est utile lorsque vous souhaitez extraire des données tabulaires d'un fichier PDF et les utiliser dans Microsoft Excel.