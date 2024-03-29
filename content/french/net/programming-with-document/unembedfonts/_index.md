---
title: Désintégrez les polices et optimisez les fichiers PDF
linktitle: Désintégrez les polices et optimisez les fichiers PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour obtenir des polices non intégrées et optimiser les fichiers PDF. Un guide étape par étape.
type: docs
weight: 370
url: /fr/net/programming-with-document/unembedfonts/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui offre un large éventail de fonctionnalités pour travailler avec des documents PDF. L'une de ses fonctionnalités consiste à obtenir des polices non intégrées à partir d'un document PDF. Cela peut être utile si vous devez extraire des polices d'un document PDF et les utiliser dans d'autres applications.

nous fournirons un guide étape par étape pour expliquer le code source C# suivant de la fonctionnalité d'obtention de polices non intégrées d'Aspose.PDF pour .NET.

## Étape 1 : Définir le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d’accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel vers le répertoire où se trouve votre document PDF.

## Étape 2 : ouvrez le document PDF

 La première étape consiste à charger le document PDF que vous souhaitez faire, utilisez le`Document` classe d’Aspose.PDF pour .NET. L'extrait de code suivant montre comment charger le document PDF :

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 3 : définissez l'option UnembedFonts

 Pour obtenir les polices non intégrées du document PDF, vous devez définir le paramètre`UnembedFonts` possibilité de`true` . Cette option est disponible dans le`OptimizationOptions` classe. L'extrait de code suivant montre comment définir le`UnembedFonts` option:

```csharp
// Définir l'option UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Étape 4 : Optimiser le document PDF

 Après avoir réglé le`UnembedFonts` option, vous pouvez optimiser le document PDF à l'aide de l'option`OptimizeResources` méthode du`Document` classe. L'extrait de code suivant montre comment optimiser le document PDF :

```csharp
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 5 : Enregistrez le document mis à jour

 Une fois le document PDF optimisé, vous pouvez enregistrer le document mis à jour à l'aide du`Save` méthode du`Document`classe. L'extrait de code suivant montre comment enregistrer le document mis à jour :

```csharp
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Étape 6 : Obtenez la taille de fichier originale et réduite

 Enfin, vous pouvez obtenir la taille de fichier originale et réduite du document PDF en utilisant le`FileInfo` classe de System.IO. L'extrait de code suivant montre comment obtenir la taille de fichier originale et réduite :

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Exemple de code source pour obtenir des polices non intégrées à l'aide d'Aspose.PDF pour .NET

Voici l'exemple complet de code source pour obtenir des polices non intégrées à partir d'un document PDF à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Définir l'option UnembedFonts
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

Dans ce didacticiel, nous avons montré comment utiliser Aspose.PDF pour .NET pour obtenir des polices non intégrées à partir d'un document PDF. En suivant le guide étape par étape, vous pouvez facilement implémenter cette fonctionnalité dans vos applications C#. La désintégration des polices peut être avantageuse lorsque vous devez travailler avec les polices extraites séparément ou garantir une utilisation cohérente des polices sur différentes plates-formes.

## FAQ

#### Q : A quoi sert la suppression des polices d'un document PDF ?

R : La suppression des polices d'un document PDF vous permet d'extraire les polices incorporées et de les utiliser dans d'autres applications. Cela peut être utile pour garantir un rendu cohérent des polices et préserver l’apparence visuelle du document.

#### Q : Comment spécifier le chemin d’accès au répertoire de documents dans le code C# ?

 R : Pour spécifier le chemin d'accès au répertoire du document, remplacez`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin réel vers le répertoire où se trouve votre document PDF.

####  Q : Qu’est-ce que le`UnembedFonts` option do, and where is it set?

 R : Le`UnembedFonts` option, disponible dans le`OptimizationOptions` classe, active ou désactive la désintégration des polices du document PDF. Pour définir cette option sur`true`, utilisez le code suivant :

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q : Puis-je annuler les modifications apportées au cours du processus d'optimisation ?

R : Aspose.PDF pour .NET n'apporte pas de modifications permanentes au document PDF d'origine pendant l'optimisation. Le processus d'optimisation est effectué sur une copie du document, laissant l'original intact.

#### Q : Comment puis-je vérifier la taille du fichier d'origine et réduite après l'optimisation ?

R : Vous pouvez utiliser le`FileInfo` une sorte de`System.IO` pour obtenir la taille de fichier originale et réduite. Voici un exemple d'extrait de code pour y parvenir :

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```