---
title: MHT en PDF
linktitle: MHT en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir MHT en PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/document-conversion/mht-to-pdf/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier MHT en PDF à l'aide d'Aspose.PDF pour .NET. MHT (MIME HTML) est un format utilisé pour enregistrer une page Web complète, y compris les images et le contenu associé. En suivant les étapes ci-dessous, vous pourrez convertir les fichiers MHT au format PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du fichier MHT
Dans cette étape, nous allons charger le fichier MHT en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Charger le document
Document document = new Document(dataDir + "test.mht", options);
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier MHT.

## Étape 2 : conversion MHT en PDF
Après avoir chargé le fichier MHT, nous pouvons procéder à la conversion en PDF. Utilisez le code suivant :

```csharp
// Enregistrez la sortie en tant que document PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Le code ci-dessus convertit le fichier MHT au format PDF et l'enregistre sous le nom de fichier`"MHTToPDF_out.pdf"`.

### Exemple de code source pour MHT en PDF en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Charger le document
Document document = new Document(dataDir  + "test.mht", options);
// Enregistrer la sortie en tant que document PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier MHT en PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir les fichiers MHT au format PDF. Cette fonctionnalité peut être utile lorsque vous devez convertir des pages Web entières en documents PDF.