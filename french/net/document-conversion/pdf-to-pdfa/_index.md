---
title: PDF à PDFA
linktitle: PDF à PDFA
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en PDFA en utilisant Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/document-conversion/pdf-to-pdfa/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier PDF au format PDF/A à l'aide d'Aspose.PDF pour .NET. Le format PDF/A est une norme ISO qui garantit la conservation à long terme des documents électroniques. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers PDF au format PDF/A.

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
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Conversion au format PDF/A
Après avoir ouvert le fichier PDF, nous pouvons procéder à la conversion au format PDF/A. Utilisez le code suivant :

```csharp
// Convertir en document conforme PDF/A
// Au cours du processus de conversion, une validation est également effectuée
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Le code ci-dessus convertit le fichier PDF au format PDF/A-1b et effectue également la validation pendant le processus de conversion. Toute erreur est enregistrée dans le`"log.xml"` déposer.

## Étape 3 : Enregistrer le fichier PDF/A résultant
Une fois la conversion terminée, nous devons enregistrer le fichier PDF/A résultant. Voici la dernière étape :

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier PDF/A de sortie.

### Exemple de code source pour PDF vers HTML en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Convertir en document conforme PDF/A
// Pendant le processus de conversion, la validation est également effectuée
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format PDF/A à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir des fichiers PDF au format PDF/A. Cette fonctionnalité est utile lorsque vous souhaitez assurer la conformité à long terme de vos documents électroniques.