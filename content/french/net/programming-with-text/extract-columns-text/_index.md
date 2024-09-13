---
title: Extraire le texte des colonnes dans un fichier PDF
linktitle: Extraire le texte des colonnes dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire le texte des colonnes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-text/extract-columns-text/
---
Ce didacticiel vous guidera tout au long du processus d'extraction de texte de colonnes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez extraire le texte des colonnes, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Ouvrir le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document`constructeur et en passant le chemin vers le fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Étape 5 : Ajustez la taille de la police
Réduisez la taille de la police des fragments de texte d'un facteur 0,7 pour améliorer la lisibilité et mieux représenter le texte en colonnes.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Étape 6 : Extraire le texte des colonnes
 Enregistrez le document PDF modifié dans un flux de mémoire et rechargez-le en tant que nouveau document. Ensuite, utilisez le`TextAbsorber` classe pour extraire le texte des colonnes.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Étape 7 : Enregistrer le texte extrait
Enregistrez le texte extrait dans un fichier texte au chemin de fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Exemple de code source pour extraire le texte des colonnes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Il faut réduire la taille de la police d'au moins 70 %
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez extrait avec succès le texte des colonnes d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel propose un guide étape par étape sur l'extraction de colonnes de texte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# qui l'accompagne fournit une démonstration pratique des procédures requises.

#### Q : Quels espaces de noms dois-je importer ?

R : Dans le fichier de code dans lequel vous souhaitez extraire des colonnes de texte, incluez les directives using suivantes au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` dans le code et remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment ouvrir un document PDF existant ?

 A : À l'étape 4, vous ouvrirez un document PDF existant à l'aide de l'`Document` constructeur et fournissant le chemin vers le fichier PDF d'entrée.

#### Q : Pourquoi la taille de la police est-elle ajustée ?

R : L'étape 5 consiste à réduire la taille de police des fragments de texte d'un facteur 0,7. Ce réglage améliore la lisibilité et représente plus précisément le texte en colonnes.

#### Q : Comment extraire du texte des colonnes ?

 A : L'étape 6 consiste à enregistrer le document PDF modifié dans un flux de mémoire, à le recharger en tant que nouveau document, puis à utiliser le`TextAbsorber` classe pour extraire le texte des colonnes.

#### Q : Quel est le but de sauvegarder le texte extrait ?

R : À l’étape 7, vous enregistrerez le texte extrait dans un fichier texte au chemin de fichier de sortie spécifié.

#### Q : Pourquoi réduire la taille de la police avant l’extraction ?

R : La réduction de la taille de la police permet de garantir que le texte extrait s’aligne correctement dans les colonnes, offrant ainsi une représentation plus précise de la mise en page d’origine.

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez acquis les connaissances et les compétences nécessaires pour extraire des colonnes de texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le texte obtenu a été enregistré dans le fichier de sortie spécifié.