---
title: Valider le PDF
linktitle: Valider le PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à valider un document PDF avec Aspose.PDF pour .NET. Vérifiez sa conformité aux normes et générez un rapport de validation.
type: docs
weight: 240
url: /fr/net/programming-with-tagged-pdf/validate-pdf/
---
Dans ce didacticiel, nous vous expliquerons comment valider un document PDF à l'aide d'Aspose.PDF pour .NET. Suivez les instructions ci-dessous pour comprendre comment utiliser le code source C# fourni pour valider un PDF et générer un rapport de validation.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela inclut l'installation de la bibliothèque Aspose.PDF et la configuration de votre projet pour le référencer.

## Étape 2 : Préparation du document PDF

Placez votre fichier PDF à valider dans le répertoire spécifié. Assurez-vous d'ajuster le chemin du fichier dans le code source en utilisant votre propre répertoire docs.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chemin du fichier d'entrée PDF
string inputFileName = dataDir + "StructureElements.pdf";

// Chemin du fichier de sortie du rapport de validation
string outputLogName = dataDir + "ua-20.xml";
```

Assurez-vous que votre fichier PDF à valider est correctement spécifié dans le code source.

## Étape 3 : Validation du PDF

Dans cette étape, nous utiliserons Aspose.PDF pour .NET pour valider le document PDF spécifié et générer un rapport de validation.

```csharp
// Ouvrir le document PDF
using (var document = new Aspose.Pdf.Document(inputFileName))
{
// Valider le document PDF
bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}
```

Nous avons ouvert le document PDF et validé son format en utilisant Aspose.PDF pour .NET. Le résultat de la validation sera stocké dans le fichier de rapport spécifié.

### Exemple de code source pour valider le PDF à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFileName = dataDir + "StructureElements.pdf";
string outputLogName = dataDir + "ua-20.xml";

using (var document = new Aspose.Pdf.Document(inputFileName))
{
	bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}

```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser Aspose.PDF pour .NET pour valider un document PDF et générer un rapport de validation. Valider le PDF permet de s'assurer qu'il est conforme aux normes et garantit son accessibilité. Utilisez ces fonctionnalités pour améliorer la qualité de vos documents PDF.
