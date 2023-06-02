---
title: Diviser en pages
linktitle: Diviser en pages
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour diviser un document PDF en pages individuelles à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-pdf-pages/split-to-pages/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus de fractionnement d'un document PDF en pages individuelles à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment scinder un document PDF en plusieurs fichiers PDF, chacun contenant une seule page.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. C'est là que se trouve le document PDF que vous souhaitez diviser. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous pouvez ouvrir le document PDF à diviser à l'aide de la`Document` classe de Aspose.PDF. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Étape 3 : Parcourez les pages et divisez-les
Vous pouvez maintenant parcourir toutes les pages du document PDF à l'aide d'une boucle. Pour chaque page, créez un nouveau document et ajoutez cette page à ce nouveau document. Enregistrez ensuite le nouveau document en utilisant un nom de fichier unique pour chaque page.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Exemple de code source pour Split To Pages à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Parcourez toutes les pages
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusion
Dans ce didacticiel, nous avons appris à diviser un document PDF en pages individuelles à l'aide d'Aspose.PDF pour .NET. En suivant ce guide étape par étape, vous pouvez facilement diviser un document PDF en plusieurs fichiers PDF, chacun contenant une seule page. Aspose.PDF offre une API puissante et flexible pour travailler avec des documents PDF dans vos projets. Vous pouvez désormais utiliser cette fonctionnalité pour effectuer des opérations de fractionnement de documents PDF en fonction de vos besoins spécifiques.
