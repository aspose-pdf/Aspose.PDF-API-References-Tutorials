---
title: Mettre à jour les cotes
linktitle: Mettre à jour les cotes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour mettre à jour les dimensions de la page PDF à l'aide d'Aspose.PDF pour .NET. Vérifiez les dimensions selon vos besoins.
type: docs
weight: 150
url: /fr/net/programming-with-pdf-pages/update-dimensions/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus de mise à jour des dimensions de page dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment modifier les dimensions d'une page dans un document PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document PDF modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous pouvez ouvrir le document PDF existant en utilisant le`Document` classe de Aspose.PDF. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Étape 3 : Obtenir la collection de pages
 Vous pouvez maintenant accéder à la collection de pages du document PDF en utilisant le`Pages` propriété de la`Document` classe.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Étape 4 : Obtenir une page spécifique
Ensuite, vous pouvez sélectionner une page spécifique du document en utilisant l'index de la page dans la collection. Dans cet exemple, nous utilisons la deuxième page (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Étape 5 : Définir les nouvelles dimensions de la page
 Vous pouvez maintenant définir la nouvelle taille de page à l'aide de la`SetPageSize()` méthode de la`Page` objet. Dans cet exemple, nous définissons les dimensions de la page sur A4 (11,7 x 8,3 pouces), converties en points (1 pouce = 72 points).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Étape 6 : Enregistrer le document mis à jour
Enfin, vous pouvez enregistrer le document PDF mis à jour dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour la mise à jour des dimensions à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Obtenir la collection de pages
PageCollection pageCollection = pdfDocument.Pages;
// Obtenir une page particulière
Page pdfPage = pageCollection[1];
// Définissez la taille de la page sur A4 (11,7 x 8,3 pouces) et dans Aspose.Pdf, 1 pouce = 72 points
// Ainsi, les dimensions A4 en points seront (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusion
Dans ce didacticiel, nous avons appris à mettre à jour les dimensions d'une page dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ce guide étape par étape, vous pouvez facilement modifier les dimensions d'une page dans un document PDF selon vos besoins. Aspose.PDF offre une API puissante et flexible pour travailler avec des fichiers PDF et effectuer diverses manipulations, y compris la modification des dimensions de la page. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les dimensions de vos pages PDF pour répondre à vos besoins spécifiques.
