---
title: PDFA en PDF
linktitle: PDFA en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir PDFA en PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/document-conversion/pdfa-to-pdf/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDFA (PDF/A) au format PDF standard à l'aide d'Aspose.PDF pour .NET. Le format PDFA est une version spécifique du format PDF utilisé pour garantir l'archivage à long terme des documents. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDFA au format PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDFA
Dans cette étape, nous allons charger le fichier PDFA source en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDFA
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDFA.

## Étape 2 : Suppression des informations de conformité PDF/A
Nous allons maintenant supprimer les informations de conformité PDF/A du document. Utilisez le code suivant :

```csharp
// Supprimer les informations de conformité PDF/A
doc.RemovePdfaCompliance();
```

## Étape 3 : Enregistrer le fichier PDF résultant
Enfin, nous enregistrerons le fichier PDFA converti au format PDF. Utilisez le code suivant :

```csharp
// Enregistrez le document mis à jour au format PDF
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

Le code ci-dessus enregistre le fichier PDFA converti au format PDF avec le nom du fichier`"PDFAToPDF_out.pdf"`.

### Exemple de code source pour PDFA en PDF en utilisant Aspose.PDF pour .NET


```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Supprimer les informations de conformité PDF/A
doc.RemovePdfaCompliance();
// Enregistrer le document mis à jour
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDFA au format PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir un fichier PDFA au format PDF standard. Cette fonctionnalité est utile lorsque vous souhaitez supprimer les restrictions de conformité PDF/A d'un document pour une utilisation plus flexible.