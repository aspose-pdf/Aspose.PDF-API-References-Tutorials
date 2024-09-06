---
title: Extraire du texte à l'aide d'un périphérique texte
linktitle: Extraire du texte à l'aide d'un périphérique texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire du texte d’un document PDF à l’aide du périphérique texte dans Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-text/extract-text-using-text-device/
---
Ce didacticiel vous guidera tout au long du processus d'extraction de texte d'un document PDF à l'aide du périphérique de texte dans Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Ouvrir le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document` constructeur et en passant le chemin vers le fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Étape 5 : Extraire le texte à l'aide d'un périphérique texte
 Créer un`StringBuilder` objet pour contenir le texte extrait. Parcourez chaque page du document et utilisez un`TextDevice` pour extraire le texte de chaque page.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Étape 6 : Enregistrez le texte extrait
 Spécifiez le chemin du fichier de sortie et enregistrez le texte extrait dans un fichier texte à l'aide de l'`File.WriteAllText` méthode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Exemple de code source pour l'extraction de texte à l'aide d'un périphérique texte avec Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Chaîne pour contenir le texte extrait
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Créer un périphérique texte
		TextDevice textDevice = new TextDevice();
		// Définir les options d'extraction de texte - définir le mode d'extraction de texte (brut ou pur)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Convertir une page particulière et enregistrer le texte dans le flux
		textDevice.Process(pdfPage, textStream);
		// Convertir une page particulière et enregistrer le texte dans le flux
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Fermer le flux mémoire
		textStream.Close();
		// Récupérer du texte à partir du flux mémoire
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Enregistrer le texte extrait dans un fichier texte
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez extrait avec succès du texte d'un document PDF à l'aide du périphérique de texte dans Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel fournit des conseils sur l'extraction de texte à partir d'un document PDF à l'aide de la fonctionnalité Périphérique de texte dans Aspose.PDF pour .NET. Le code source C# qui l'accompagne illustre les étapes nécessaires pour réaliser cette tâche.

#### Q : Quels espaces de noms dois-je importer ?

R : Dans le fichier de code dans lequel vous prévoyez d'extraire le texte, incluez les directives using suivantes au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment ouvrir un document PDF existant ?

 A : À l'étape 4, vous ouvrirez un document PDF existant à l'aide de l'`Document` constructeur et fournissant le chemin vers le fichier PDF d'entrée.

#### Q : Comment extraire du texte à l’aide du périphérique texte ?

 A : L'étape 5 consiste à créer un`StringBuilder` objet pour contenir le texte extrait. Vous parcourrez ensuite chaque page du document et utiliserez un`TextDevice` avec`TextExtractionOptions` pour extraire le texte de chaque page.

#### Q : Comment enregistrer le texte extrait dans un fichier ?

 A : À l’étape 6, vous spécifiez le chemin du fichier de sortie et utilisez le`File.WriteAllText`méthode pour enregistrer le texte extrait dans un fichier texte.

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à exploiter la fonctionnalité Périphérique de texte dans Aspose.PDF pour .NET pour extraire du texte d'un document PDF. Le texte extrait a été enregistré dans un fichier de sortie spécifié, ce qui vous permet de manipuler et d'utiliser le contenu extrait selon vos besoins.