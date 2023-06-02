---
title: PDF à EPUB
linktitle: PDF à EPUB
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en EPUB en utilisant Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/document-conversion/pdf-to-epub/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier PDF au format EPUB à l'aide d'Aspose.PDF pour .NET. Le format PDF est couramment utilisé pour afficher des documents, tandis que le format EPUB est spécialement conçu pour les livres électroniques. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers PDF au format EPUB.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDF
Dans cette étape, nous allons télécharger le fichier PDF en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Instanciation des options d'enregistrement EPUB
Après avoir chargé le document PDF, nous allons instancier les options de sauvegarde pour le format EPUB. Utilisez le code suivant :

```csharp
// Instancier les options de sauvegarde EPUB
EpubSaveOptions options = new EpubSaveOptions();
```

## Étape 3 : Spécification de la mise en page du contenu
Nous allons maintenant spécifier la mise en page du contenu du livre EPUB. Utilisez le code suivant :

```csharp
// Spécification de la mise en page du contenu
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## Étape 4 : Enregistrer le document EPUB
Une fois que nous avons configuré les options de sauvegarde, nous pouvons maintenant enregistrer le fichier EPUB résultant. Voici la dernière étape :

```csharp
// Enregistrer le document EPUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier EPUB de sortie.

### Exemple de code source pour PDF vers EPUB en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

// Options d'instanciation d'Epub Save
EpubSaveOptions options = new EpubSaveOptions();

// Spécifier la mise en page du contenu
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

// Enregistrer le document ePUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format EPUB à l'aide d'Aspose.PDF pour .NET. En suivant les instructions ci-dessus, vous pouvez facilement convertir des fichiers PDF au format EPUB. Cette fonctionnalité est particulièrement utile pour convertir des documents PDF en livres électroniques lisibles sur différents appareils.