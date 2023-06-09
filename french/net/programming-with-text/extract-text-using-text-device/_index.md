---
title: Extraire du texte à l'aide d'un périphérique de texte
linktitle: Extraire du texte à l'aide d'un périphérique de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire du texte d'un document PDF à l'aide du périphérique de texte dans Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-text/extract-text-using-text-device/
---

Ce didacticiel vous guidera tout au long du processus d'extraction de texte d'un document PDF à l'aide du périphérique de texte dans Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Ouvrez le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document` constructeur et en transmettant le chemin d'accès au fichier PDF d'entrée.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Étape 5 : Extrayez du texte à l'aide de Text Device
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
 Spécifiez le chemin du fichier de sortie et enregistrez le texte extrait dans un fichier texte à l'aide de la`File.WriteAllText` méthode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Exemple de code source pour Extraire du texte à l'aide d'un périphérique de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// Chaîne pour contenir le texte extrait
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Créer un périphérique de texte
		TextDevice textDevice = new TextDevice();
		// Définir les options d'extraction de texte - définir le mode d'extraction de texte (Raw ou Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Convertir une page particulière et enregistrer du texte dans le flux
		textDevice.Process(pdfPage, textStream);
		// Convertir une page particulière et enregistrer du texte dans le flux
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Fermer le flux de mémoire
		textStream.Close();
		// Obtenir du texte à partir du flux de mémoire
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Enregistrez le texte extrait dans un fichier texte
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez extrait avec succès du texte d'un document PDF à l'aide du périphérique de texte dans Aspose.PDF pour .NET. Le texte extrait a été enregistré dans le fichier de sortie spécifié.