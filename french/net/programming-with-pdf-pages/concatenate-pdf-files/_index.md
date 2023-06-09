---
title: Concaténer des fichiers PDF
linktitle: Concaténer des fichiers PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour concaténer des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Facile à suivre et à mettre en œuvre dans vos projets.
type: docs
weight: 20
url: /fr/net/programming-with-pdf-pages/concatenate-pdf-files/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus de concaténation de fichiers PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment concaténer des fichiers PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. C'est là que se trouvent vos fichiers PDF à concaténer. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrir les fichiers PDF
 Ensuite, vous pouvez ouvrir les fichiers PDF à concaténer à l'aide de la`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct à chaque fichier PDF.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## Étape 3 : Concaténer des pages
 Vous pouvez maintenant ajouter les pages du deuxième document au premier document à l'aide de la`Add()` la méthode du document`Pages` collection. Cela concaténera les pages des deux documents en un seul document.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## Étape 4 : Enregistrez le fichier PDF concaténé
 Enfin, vous pouvez enregistrer le document PDF concaténé dans un fichier de sortie à l'aide de la`Save()` méthode. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### Exemple de code source pour concaténer des fichiers PDF à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le premier document
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// Ouvrir le deuxième document
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// Ajouter des pages du deuxième document au premier
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
// Enregistrer le fichier de sortie concaténé
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## Conclusion
Dans ce didacticiel, nous avons appris à concaténer des fichiers PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez facilement implémenter cette fonctionnalité dans vos propres projets. N'hésitez pas à explorer davantage la documentation Aspose.PDF pour découvrir d'autres fonctionnalités utiles pour travailler avec des fichiers PDF.
