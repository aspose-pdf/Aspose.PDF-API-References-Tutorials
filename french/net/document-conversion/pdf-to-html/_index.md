---
title: PDF vers HTML
linktitle: PDF vers HTML
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en HTML en utilisant Aspose.PDF pour .NET.
type: docs
weight: 130
url: /fr/net/document-conversion/pdf-to-html/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDF au format HTML à l'aide d'Aspose.PDF pour .NET. Le format PDF est couramment utilisé pour afficher et partager des documents, tandis que le format HTML est utilisé pour créer des pages Web. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers PDF au format HTML.

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
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : conversion PDF en HTML
Après avoir ouvert le fichier PDF, nous pouvons procéder à la conversion au format HTML. Utilisez le code suivant :

```csharp
// Enregistrez le fichier au format HTML
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 Le code ci-dessus convertit le fichier PDF au format HTML et l'enregistre sous`"output_out.html"` déposer.

 Remplacer`"YOUR DOCUMENTS DIRECTORY"`avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier HTML de sortie.

### Exemple de code source pour PDF vers HTML en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF source
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Enregistrez le fichier au format de document MS
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format HTML à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir des fichiers PDF au format HTML. Cette fonctionnalité est utile lorsque vous souhaitez intégrer du contenu PDF dans des pages Web ou d'autres applications prenant en charge le format HTML.

