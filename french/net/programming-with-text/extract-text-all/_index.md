---
title: Extraire tout le texte
linktitle: Extraire tout le texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 180
url: /fr/net/programming-with-text/extract-text-all/
---

Ce didacticiel vous guidera tout au long du processus d'extraction de tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

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

## Étape 5 : Extrayez tout le texte
 Créer un`TextAbsorber` objet pour extraire le texte du document. Ensuite, acceptez l'absorbeur pour toutes les pages.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Étape 6 : Obtenir le texte extrait
 Accéder au texte extrait de la`TextAbsorber` objet.

```csharp
string extractedText = textAbsorber.Text;
```

## Étape 7 : Enregistrer le texte extrait
 Créer un`TextWriter` et ouvrez le fichier dans lequel vous souhaitez enregistrer le texte extrait. Écrivez le texte extrait dans le fichier et fermez le flux.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemple de code source pour Extraire tout le texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Créer un objet TextAbsorber pour extraire du texte
TextAbsorber textAbsorber = new TextAbsorber();
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textAbsorber);
// Obtenir le texte extrait
string extractedText = textAbsorber.Text;
// Créer un écrivain et ouvrir le fichier
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Ecrire une ligne de texte dans le fichier
tw.WriteLine(extractedText);
// Fermer le flux
tw.Close();
```

## Conclusion
Vous avez réussi à extraire tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.