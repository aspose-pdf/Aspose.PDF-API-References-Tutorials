---
title: Créer un PDF A1 avec Aspose Pdf
linktitle: Créer un PDF A1 avec Aspose Pdf
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer un document PDF A1 à l'aide d'Aspose.PDF pour .NET. Guide pas à pas avec le code source C#. Optimisez efficacement les PDF.
type: docs
weight: 90
url: /fr/net/programming-with-document/createpdfa1withasposepdf/
---

Dans ce guide étape par étape, nous expliquerons comment utiliser Aspose.PDF pour .NET pour créer un document PDF A1. Nous vous fournirons le code source C# et les instructions nécessaires pour accomplir cette tâche.

## Étape 1 : Définir des variables et importer des espaces de noms

 Tout d'abord, définissez la variable`dataDir` pour représenter le répertoire où sont stockés vos documents. Ceci sera utilisé pour spécifier le chemin du fichier de sortie.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ensuite, créez une nouvelle instance de`Document` classe de Aspose.PDF.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Étape 2 : Ajouter du contenu au PDF

Dans cette étape, nous allons ajouter une page au document PDF et insérer un fragment de texte contenant le texte "Hello World!".

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## Étape 3 : Enregistrez le PDF dans un flux de mémoire

Pour convertir le PDF au format PDF/A1, nous devons l'enregistrer dans un flux de mémoire.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## Étape 4 : Convertir le PDF au format PDF/A1

 Maintenant, nous allons convertir le PDF au format PDF/A1 en utilisant le`Convert` méthode de la`Document` classe. Nous passons un nouveau flux de mémoire comme flux de sortie et spécifions le`PdfFormat.PDF_A_1A` format.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## Étape 5 : Enregistrez le PDF converti

Enfin, enregistrez le PDF converti dans le répertoire spécifié.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### Exemple de code source pour créer un PDF A1 à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Ajouter une page dans le document pdf
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// Enregistrer le document
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

En suivant ces étapes et en utilisant le code source fourni, vous pouvez créer un document PDF A1 en utilisant Aspose.PDF pour .NET.

N'oubliez pas d'ajuster "VOTRE RÉPERTOIRE DE DOCUMENTS" avec le chemin de répertoire approprié où vous souhaitez enregistrer le fichier de sortie.


