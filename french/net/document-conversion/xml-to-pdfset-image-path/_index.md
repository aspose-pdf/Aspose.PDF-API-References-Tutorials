---
title: XML vers PDFDéfinir le chemin de l'image
linktitle: XML vers PDFDéfinir le chemin de l'image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour définir le chemin d'une image lors de la conversion de XML en PDF avec Aspose.PDF pour .NET.
type: docs
weight: 340
url: /fr/net/document-conversion/xml-to-pdfset-image-path/
---

Dans ce didacticiel, nous vous expliquerons étape par étape comment définir le chemin d'une image lors de la conversion d'un fichier XML en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous détaillerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets. À la fin de ce didacticiel, vous pourrez facilement spécifier le chemin d'une image lors de la conversion de XML en PDF.

## Étape 1 : Définir les chemins d'accès aux fichiers
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Définissez les chemins des fichiers XML d'entrée, l'image à utiliser et le fichier PDF de sortie. Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin où vous avez enregistré vos fichiers.

## Étape 2 : instancier un objet Document
```csharp
Document doc = new Document();
```
Créez une instance de l'objet Document.

## Étape 3 : Liez le fichier XML source
```csharp
doc. BindXml(inXml);
```
Lie le fichier XML source au document.

## Étape 4 : Définir le chemin de l'image
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Obtenez la référence de l'objet Image à partir du XML à l'aide de son ID et définissez le chemin de l'image à utiliser.

## Étape 5 : Enregistrez le fichier PDF résultant
```csharp
doc.Save(outFile);
```
Enregistrez le fichier PDF résultant dans le répertoire spécifié.

### Exemple de code source pour XML vers PDFDéfinir le chemin de l'image à l'aide d'Aspose.PDF pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir le chemin d'une image lors de la conversion de XML en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant les étapes fournies, vous pouvez facilement spécifier le chemin de l'image dans vos propres conversions XML en PDF.