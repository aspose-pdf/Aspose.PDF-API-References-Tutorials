---
title: Remplacer les polices manquantes
linktitle: Remplacer les polices manquantes
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour remplacer les polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 260
url: /fr/net/document-conversion/replace-missing-fonts/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de remplacement des polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Lorsque vous ouvrez un fichier PDF sur un ordinateur sur lequel une police spécifique est manquante, des problèmes d'affichage des polices peuvent survenir. Dans de tels cas, il est possible de remplacer la police manquante par une autre police disponible sur la machine. En suivant les étapes ci-dessous, vous pourrez remplacer les polices manquantes dans un fichier PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Trouver la police manquante
La première étape consiste à trouver la police manquante dans le fichier PDF. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Trouver la police d'origine
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

// Convertissez le fichier PDF au format PDF/A avec suppression des erreurs
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Enregistrez le fichier PDF résultant
pdf.Save(fileNew.FullName);
```

 Assurez-vous de remplacer`"input.pdf"` avec le chemin réel vers votre fichier PDF original et`"newfile_out.pdf"` avec le nom souhaité pour le fichier PDF résultant.

## Étape 3 : Enregistrement du fichier PDF résultant
Enfin, nous enregistrerons le fichier PDF résultant avec la police remplacée. Utilisez le code suivant :

```csharp
// Enregistrez le fichier PDF résultant
pdf.Save(fileNew.FullName);
```

Assurez-vous que vous avez défini le chemin de destination correct pour le fichier PDF résultant.

### Exemple de code source pour remplacer les polices manquantes à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
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
Dans ce didacticiel, nous avons couvert le processus étape par étape de remplacement des polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous pourrez remplacer avec succès les polices manquantes dans votre fichier PDF.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre diverses fonctionnalités, notamment la possibilité de remplacer les polices manquantes dans les fichiers PDF.

#### Q : Pourquoi devrais-je rencontrer des polices manquantes dans un fichier PDF ?

R : Des polices manquantes dans un fichier PDF peuvent se produire lorsque le fichier est ouvert sur un ordinateur sur lequel les polices nécessaires ne sont pas installées. Cela peut conduire à une substitution de police, affectant l'apparence visuelle du document.

#### Q : Comment puis-je rechercher et remplacer les polices manquantes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Pour rechercher et remplacer les polices manquantes, vous pouvez utiliser l'outil`FontRepository.FindFont` méthode pour vérifier la présence de la police requise. Si la police est manquante, vous pouvez ajouter une substitution de police à l'aide du`FontRepository.Substitutions` propriété.

#### Q : Puis-je personnaliser le processus de substitution de police ?

R : Oui, vous pouvez personnaliser le processus de substitution de police en spécifiant une police différente pour la substitution. Dans le code fourni, nous avons utilisé Arial comme substitut à la police "AgencyFB" manquante, mais vous pouvez choisir une police différente selon vos préférences.

#### Q : Comment puis-je garantir l’exactitude du rendu des polices après substitution ?

R : Aspose.PDF pour .NET offre des capacités robustes de gestion des polices, garantissant un rendu précis des polices après substitution. Vous pouvez prévisualiser le fichier PDF résultant pour vérifier le remplacement de la police.