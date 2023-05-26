---
title: Valider la norme PDFUA
linktitle: Valider la norme PDFUA
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour valider la norme PDF/UA à l'aide du code C#. Guide étape par étape.
type: docs
weight: 400
url: /fr/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui fournit diverses fonctionnalités pour travailler avec des documents PDF. L'une de ses fonctionnalités est la possibilité de valider des documents PDF pour la conformité à la norme PDF/UA. Dans cet article, nous fournirons des conseils étape par étape sur la façon d'utiliser Aspose.PDF pour .NET pour obtenir et valider la conformité à la norme PDF/UA à l'aide du code C#.

## Étape 1 : Définition du chemin d'accès au répertoire de documents

Ensuite, nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Pour ce faire, ajoutez l'extrait de code suivant :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents PDF.

## Étape 2 : Ouverture du document PDF

Après avoir défini le chemin du répertoire du document, nous pouvons ouvrir notre document PDF en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 Ce code crée un nouveau`Document` objet de notre fichier PDF situé dans le répertoire spécifié.

## Étape 3 : Validation du PDF pour PDF/UA

Maintenant que nous avons ouvert le document PDF, nous pouvons utiliser Aspose.PDF pour .NET pour valider le document pour la conformité PDF/UA. L'extrait de code suivant fera l'affaire :

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

Ce code valide le document PDF pour la conformité à la norme PDF/UA et génère un rapport de validation dans le fichier XML spécifié. Le résultat de la validation est stocké dans le`isValidPdfUa` variable, qui est de type booléen.

### Exemple de code source pour Get Validate PDFUAstandard en utilisant Aspose.PDF pour .NET

```csharp
           
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

	// Valider PDF pour PDF/UA
	bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
		   
```
