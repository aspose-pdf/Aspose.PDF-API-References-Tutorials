---
title: PDF à XPS
linktitle: PDF à XPS
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en XPS en utilisant Aspose.PDF pour .NET.
type: docs
weight: 220
url: /fr/net/document-conversion/pdf-to-xps/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDF au format XPS (XML Paper Specification) à l'aide d'Aspose.PDF pour .NET. Le format XPS est un format de fichier basé sur XML utilisé pour représenter électroniquement des documents. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDF au format XPS.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDF
Dans cette étape, nous allons charger le fichier PDF source en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Instanciez les options d'enregistrement XPS
Après avoir chargé le fichier PDF, nous allons instancier les options de sauvegarde XPS. Utilisez le code suivant :

```csharp
// Instancier les options de sauvegarde XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Étape 3 : Enregistrement du fichier XPS résultant
Nous allons maintenant enregistrer le fichier PDF converti au format XPS. Utilisez le code suivant :

```csharp
// Enregistrer le document XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Le code ci-dessus enregistre le fichier PDF converti au format XPS avec le nom de fichier`"PDFToXPS_out.xps"`.


### Exemple de code source pour PDF vers XPS en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instancier les options d'enregistrement XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Enregistrer le document XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format XPS à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir un fichier PDF au format XPS. Cette fonction est utile lorsque vous souhaitez afficher ou imprimer des documents PDF au format XPS.