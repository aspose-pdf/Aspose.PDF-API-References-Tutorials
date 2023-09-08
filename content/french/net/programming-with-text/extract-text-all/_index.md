---
title: Extraire le texte dans un fichier PDF
linktitle: Extraire le texte du fichier PDF AllIn
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment extraire tout le texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 180
url: /fr/net/programming-with-text/extract-text-all/
---
Ce didacticiel vous guidera tout au long du processus d'extraction de tout le texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez extraire le texte, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using System.IO;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Ouvrez le document PDF
 Ouvrez un document PDF existant à l'aide du`Document`constructeur et en transmettant le chemin d’accès au fichier PDF d’entrée.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Étape 5 : Extraire tout le texte
 Créer un`TextAbsorber`objet pour extraire le texte du document. Ensuite, prenez le absorbeur pour toutes les pages.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Étape 6 : Obtenez le texte extrait
 Accédez au texte extrait depuis le`TextAbsorber` objet.

```csharp
string extractedText = textAbsorber.Text;
```

## Étape 7 : Enregistrez le texte extrait
 Créer un`TextWriter` et ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait. Écrivez le texte extrait dans le fichier et fermez le flux.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemple de code source pour extraire tout le texte à l’aide d’Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Créer un objet TextAbsorber pour extraire du texte
TextAbsorber textAbsorber = new TextAbsorber();
// Acceptez l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textAbsorber);
// Récupérer le texte extrait
string extractedText = textAbsorber.Text;
// Créez un écrivain et ouvrez le fichier
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Écrire une ligne de texte dans le fichier
tw.WriteLine(extractedText);
// Fermer le flux
tw.Close();
```

## Conclusion
Vous avez réussi à extraire tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel sert de guide pour vous aider à extraire tout le texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni fournit des instructions étape par étape pour réaliser cette tâche.

#### Q : Quels espaces de noms dois-je importer ?

R : Dans le fichier de code dans lequel vous souhaitez extraire le texte, incluez les directives using suivantes au début du fichier :

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` dans le code et remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment puis-je ouvrir un document PDF existant ?

 R : À l'étape 4, vous ouvrirez un document PDF existant à l'aide de l'outil`Document` constructeur et fournissant le chemin d’accès au fichier PDF d’entrée.

#### Q : Comment extraire tout le texte du document ?

 R : L'étape 5 consiste à créer un`TextAbsorber` objet pour extraire le texte du document PDF. Ensuite, vous accepterez le absorbeur pour toutes les pages.

#### Q : Comment accéder au texte extrait ?

 R : L'étape 6 vous guide dans l'accès au texte extrait du`TextAbsorber` objet.

#### Q : Comment puis-je enregistrer le texte extrait dans un fichier ?

 R : À l'étape 7, vous allez créer un`TextWriter`, ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait, écrivez le texte extrait dans le fichier, puis fermez le flux.

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris à extraire tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans un fichier de sortie spécifié, vous permettant d'analyser et de manipuler le contenu textuel du document.