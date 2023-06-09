---
title: PDF vers XML
linktitle: PDF vers XML
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en XML à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/document-conversion/pdf-to-xml/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDF au format XML à l'aide d'Aspose.PDF pour .NET. XML (eXtensible Markup Language) est un format de données utilisé pour stocker et échanger des informations structurées. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDF au format XML.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Enregistrer le fichier XML résultant
Nous allons maintenant enregistrer le fichier PDF converti au format XML. Utilisez le code suivant :

```csharp
// Enregistrer la sortie au format XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 Le code ci-dessus enregistre le fichier PDF converti au format XML avec le nom de fichier`"PDFToXML_out.xml"`.

### Exemple de code source pour PDF vers XML en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Charger le fichier PDF source
Document doc = new Document(dataDir + "input.pdf");
// Enregistrer la sortie au format XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF en XML à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir un fichier PDF au format XML. Cette fonctionnalité est utile lorsque vous souhaitez extraire le contenu structuré d'un fichier PDF et le traiter au format XML pour une utilisation ultérieure.