---
title: Remplacer les polices manquantes
linktitle: Remplacer les polices manquantes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour remplacer les polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/document-conversion/replace-missing-fonts/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de remplacement des polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Lorsque vous ouvrez un fichier PDF sur une machine où une police spécifique est manquante, il peut y avoir des problèmes d'affichage des polices. Dans ce cas, il est possible de remplacer la police manquante par une autre police disponible sur la machine. En suivant les étapes ci-dessous, vous pourrez remplacer les polices manquantes dans un fichier PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Trouver la police manquante
La première étape consiste à trouver la police manquante dans le fichier PDF. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Retrouver la police d'origine
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // La police est manquante sur la machine de destination
     // Ajouter une substitution de police simple
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Remplacer la police manquante
Ensuite, nous remplacerons la police manquante par une autre police disponible. Utilisez le code suivant :

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Convertir le fichier PDF au format PDF/A avec suppression des erreurs
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Enregistrez le fichier PDF résultant
pdf.Save(fileNew.FullName);
```

 Assurez-vous de remplacer`"input.pdf"` avec le chemin d'accès réel à votre fichier PDF d'origine et`"newfile_out.pdf"` avec le nom souhaité pour le fichier PDF résultant.

## Étape 3 : Enregistrer le fichier PDF résultant
Enfin, nous enregistrerons le fichier PDF résultant avec la police remplacée. Utilisez le code suivant :

```csharp
// Enregistrez le fichier PDF résultant
pdf.Save(fileNew.FullName);
```

Assurez-vous que vous avez défini le chemin de destination correct pour le fichier PDF résultant.

### Exemple de code source pour Remplacer les polices manquantes à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// La police est manquante sur la machine de destination
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de remplacement des polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous serez en mesure de remplacer avec succès les polices manquantes dans votre fichier PDF.