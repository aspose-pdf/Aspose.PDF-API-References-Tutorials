---
title: Désintégrer les polices et optimiser les fichiers PDF
linktitle: Désintégrer les polices et optimiser les fichiers PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir des polices non incorporées et optimiser les fichiers PDF. Un guide étape par étape.
type: docs
weight: 370
url: /fr/net/programming-with-document/unembedfonts/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui fournit un large éventail de fonctionnalités pour travailler avec des documents PDF. L'une de ses fonctionnalités est d'obtenir des polices non intégrées à partir d'un document PDF. Cela peut être utile si vous devez extraire des polices d'un document PDF et les utiliser dans d'autres applications.

nous fournirons un guide étape par étape pour expliquer le code source C # suivant de la fonction d'obtention des polices non incorporées d'Aspose.PDF pour .NET.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 2 : Ouvrez le document PDF

 La première étape consiste à charger le document PDF que vous voulez faire, utilisez le`Document` classe de Aspose.PDF pour .NET. L'extrait de code suivant montre comment charger le document PDF :

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 3 : Définissez l'option UnembedFonts

 Pour obtenir des polices non incorporées à partir du document PDF, vous devez définir le`UnembedFonts` possibilité de`true` . Cette option est disponible dans le`OptimizationOptions` classe. L'extrait de code suivant montre comment définir le`UnembedFonts` option:

```csharp
// Définir l'option Annuler l'intégration des polices
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Étape 4 : Optimisez le document PDF

 Après avoir réglé le`UnembedFonts` option, vous pouvez optimiser le document PDF à l'aide de l'option`OptimizeResources` méthode de la`Document` classe. L'extrait de code suivant montre comment optimiser le document PDF :

```csharp
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 5 : Enregistrer le document mis à jour

 Une fois le document PDF optimisé, vous pouvez enregistrer le document mis à jour à l'aide de la`Save` méthode de la`Document`classe. L'extrait de code suivant montre comment enregistrer le document mis à jour :

```csharp
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Étape 6 : Obtenir la taille de fichier d'origine et réduite

 Enfin, vous pouvez obtenir la taille de fichier d'origine et réduite du document PDF à l'aide de l'outil`FileInfo` classe de System.IO. L'extrait de code suivant montre comment obtenir la taille de fichier d'origine et réduite :

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Exemple de code source pour obtenir des polices non incorporées à l'aide d'Aspose.PDF pour .NET

Voici l'exemple de code source complet permettant d'obtenir des polices non incorporées à partir d'un document PDF à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Définir l'option Annuler l'intégration des polices
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusion

Dans ce didacticiel, nous avons montré comment utiliser Aspose.PDF pour .NET pour obtenir des polices non incorporées à partir d'un document PDF. En suivant le guide étape par étape, vous pouvez facilement implémenter cette fonctionnalité dans vos applications C#. La désintégration des polices peut être avantageuse lorsque vous devez travailler avec les polices extraites séparément ou garantir une utilisation cohérente des polices sur différentes plates-formes.

## FAQ

#### Q : Quel est le but de la désintégration des polices d'un document PDF ?

R : La désintégration des polices d'un document PDF vous permet d'extraire les polices intégrées et de les utiliser dans d'autres applications. Cela peut être utile pour assurer un rendu de police cohérent et préserver l'apparence visuelle du document.

#### Q : Comment spécifier le chemin d'accès au répertoire de documents dans le code C# ?

 A : Pour spécifier le chemin d'accès au répertoire de documents, remplacez`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès réel au répertoire où se trouve votre document PDF.

####  Q : Qu'est-ce que le`UnembedFonts` option do, and where is it set?

 R : Le`UnembedFonts` option, disponible dans le`OptimizationOptions` class, active ou désactive la désintégration des polices du document PDF. Pour définir cette option sur`true`, utilisez le code suivant :

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q : Puis-je annuler les modifications apportées au cours du processus d'optimisation ?

R : Aspose.PDF pour .NET n'apporte pas de modifications permanentes au document PDF d'origine lors de l'optimisation. Le processus d'optimisation est effectué sur une copie du document, laissant l'original intact.

#### Q : Comment puis-je vérifier la taille du fichier original et réduit après l'optimisation ?

 : Vous pouvez utiliser le`FileInfo` une sorte de`System.IO` pour obtenir la taille de fichier d'origine et réduite. Voici un exemple d'extrait de code pour y parvenir :

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```