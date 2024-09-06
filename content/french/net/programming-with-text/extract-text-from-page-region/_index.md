---
title: Extraire le texte d'une zone de page dans un fichier PDF
linktitle: Extraire le texte d'une zone de page dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire du texte d’une région spécifique d’une page dans un fichier PDF à l’aide d’Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-text/extract-text-from-page-region/
---
Ce didacticiel vous guidera tout au long du processus d'extraction de texte d'une région spécifique d'une page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez extraire le texte, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using System.IO;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Ouvrir le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document` constructeur et en passant le chemin vers le fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Étape 5 : Extraire le texte d’une zone de page
 Créer un`TextAbsorber` objet pour extraire le texte du document. Configurez l'`TextSearchOptions` pour limiter la recherche à une région de page spécifique définie par un rectangle.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Étape 6 : Récupérer le texte extrait
 Accédez au texte extrait du`TextAbsorber` objet.

```csharp
string extractedText = absorb.Text;
```

## Étape 7 : Enregistrer le texte extrait
 Créer un`TextWriter` et ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait. Écrivez le texte extrait dans le fichier et fermez le flux.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemple de code source pour extraire du texte d'une zone de page à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
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
// Créez un écrivain et ouvrez le fichier
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Écrire une ligne de texte dans le fichier
tw.WriteLine(extractedText);
// Fermer le flux
tw.Close();
```

## Conclusion
Vous avez extrait avec succès du texte d'une zone spécifique d'une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel a pour objectif de vous guider dans le processus d'extraction de texte d'une région spécifique d'une page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni fournit des instructions étape par étape pour accomplir cette tâche.

#### Q : Quels espaces de noms dois-je importer ?

R : Dans le fichier de code dans lequel vous souhaitez extraire le texte, incluez les directives using suivantes au début du fichier :

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` dans le code et remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment ouvrir un document PDF existant ?

 A : À l'étape 4, vous ouvrirez un document PDF existant à l'aide de l'`Document` constructeur et fournissant le chemin vers le fichier PDF d'entrée.

#### Q : Comment extraire du texte d’une zone de page spécifique ?

 A : L'étape 5 consiste à créer un`TextAbsorber`objet pour extraire le texte du document PDF. Vous configurerez ensuite l'`TextSearchOptions` pour définir une région rectangulaire spécifique sur la page à l'aide de coordonnées.

#### Q : Comment puis-je accéder au texte extrait ?

 A : L'étape 6 vous guide pour accéder au texte extrait du`TextAbsorber` objet.

#### Q : Comment enregistrer le texte extrait dans un fichier ?

 A : À l'étape 7, vous allez créer un`TextWriter`, ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait, écrivez le texte extrait dans le fichier, puis fermez le flux.

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à extraire du texte d'une zone spécifique d'une page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans un fichier de sortie spécifié, ce qui vous permet de cibler et d'analyser précisément le contenu textuel souhaité.