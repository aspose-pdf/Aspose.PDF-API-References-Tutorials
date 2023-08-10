---
title: Extraire le texte de la région de la page
linktitle: Extraire le texte de la région de la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire du texte d'une région spécifique sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-text/extract-text-from-page-region/
---

Ce didacticiel vous guidera tout au long du processus d'extraction de texte d'une région spécifique sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez extraire le texte, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using System.IO;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Ouvrez le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document` constructeur et en transmettant le chemin d'accès au fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Étape 5 : Extraire le texte d'une zone de page
 Créer un`TextAbsorber`objet pour extraire le texte du document. Configurez le`TextSearchOptions` pour limiter la recherche à une zone de page spécifique définie par un rectangle.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Étape 6 : Obtenir le texte extrait
 Accéder au texte extrait de la`TextAbsorber` objet.

```csharp
string extractedText = absorb.Text;
```

## Étape 7 : Enregistrer le texte extrait
 Créer un`TextWriter` et ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait. Écrivez le texte extrait dans le fichier et fermez le flux.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemple de code source pour Extraire le texte de la région de la page à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Créer un objet TextAbsorber pour extraire du texte
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Accepter l'absorbeur pour la première page
pdfDocument.Pages[1].Accept(absorber);
// Obtenir le texte extrait
string extractedText = absorber.Text;
// Créer un écrivain et ouvrir le fichier
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Ecrire une ligne de texte dans le fichier
tw.WriteLine(extractedText);
// Fermer le flux
tw.Close();
```

## Conclusion
Vous avez extrait avec succès du texte d'une région spécifique sur une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.