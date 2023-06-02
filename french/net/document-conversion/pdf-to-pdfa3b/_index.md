---
title: PDF à PDFA3b
linktitle: PDF à PDFA3b
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en PDF/A-3b en utilisant Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/document-conversion/pdf-to-pdfa3b/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier PDF au format PDF/A-3b à l'aide d'Aspose.PDF pour .NET. PDF/A-3b est une norme ISO pour l'intégration de fichiers et de données dans un document PDF. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers PDF au format PDF/A-3b.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Ouverture du document PDF source
Dans cette étape, nous allons ouvrir le fichier PDF source en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF source
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Convertir en PDF/A-3b
Après avoir ouvert le fichier PDF, nous pouvons procéder à la conversion au format PDF/A-3b. Utilisez le code suivant :

```csharp
// Convertir au format PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Le code ci-dessus convertit le fichier PDF au format PDF/A-3b et supprime toutes les erreurs de conversion.

## Étape 3 : Enregistrement du fichier PDF/A-3b résultant
Une fois la conversion terminée, nous devons enregistrer le fichier PDF/A-3b résultant. Voici la dernière étape :

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier de sortie PDF/A-3b.

### Exemple de code source pour PDF vers PDFA3b en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format PDF/A-3b à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir des fichiers PDF au format PDF/A-3b. Cette fonctionnalité est utile lorsque vous souhaitez incorporer des fichiers et des données supplémentaires dans un document PDF conforme à la norme PDF/A-3b.