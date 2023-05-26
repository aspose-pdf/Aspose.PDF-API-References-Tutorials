---
title: Valider PDFABStandard
linktitle: Valider PDFABStandard
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour valider des documents PDF par rapport au PDFABStandard avec notre guide étape par étape et notre exemple de code.
type: docs
weight: 380
url: /fr/net/programming-with-document/validatepdfabstandard/
---
Si vous travaillez avec des documents PDF dans .NET, vous devrez peut-être valider le PDF par rapport à une norme telle que PDF/A. Aspose.PDF pour .NET fournit une méthode facile à utiliser pour valider un document PDF par rapport à la norme PDF/A-1a. Dans cet article, nous fournirons un guide étape par étape pour expliquer le code source C# suivant pour obtenir et valider la norme PDF/A-1a à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 2 : Ouvrez le document PDF

Ensuite, nous devons ouvrir le document PDF à l'aide de la classe "Document" Aspose.PDF pour .NET. Nous allons stocker le document dans une variable appelée "pdfDocument".

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ValidatePDFAStandard.pdf");
```

Remplacez "ValidatePDFAStandard.pdf" par le nom de votre document PDF.

### Étape 3 : Valider le PDF pour PDF/A-1a

Enfin, nous pouvons valider le document PDF par rapport à la norme PDF/A-1a en utilisant la méthode "Valider" de la classe "Document". Nous stockerons le résultat de la validation dans un fichier appelé "validation-result-A1A.xml".

```csharp
// Valider PDF pour PDF/A-1a
pdfDocument.Validate(dataDir + "validation-result-A1A.xml", PdfFormat.PDF_A_1B);
```

Le deuxième paramètre "PdfFormat.PDF_A_1B" spécifie que nous voulons valider le PDF par rapport à la norme PDF/A-1a.

## Conclusion

Dans cet article, nous avons expliqué comment utiliser Aspose.PDF pour .NET pour valider un document PDF par rapport à la norme PDF/A-1a. En suivant les étapes ci-dessus, vous pouvez facilement valider vos documents PDF par rapport à diverses normes à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour Get Validate PDFABStandard en utilisant Aspose.PDF pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "ValidatePDFAStandard.pdf");

	// Valider PDF pour PDF/A-1a
	pdfDocument.Validate(dataDir + "validation-result-A1A.xml", PdfFormat.PDF_A_1B);
	
```
