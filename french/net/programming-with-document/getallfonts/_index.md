---
title: Obtenir toutes les polices
linktitle: Obtenir toutes les polices
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un document PDF par programmation avec ce guide étape par étape et un exemple de code.
type: docs
weight: 160
url: /fr/net/programming-with-document/getallfonts/
---

Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF par programmation. L'une des fonctionnalités qu'il offre est la possibilité d'obtenir toutes les polices utilisées dans un document PDF. Cela peut être utile si vous avez besoin d'analyser ou de manipuler par programme les polices dans un document PDF.

Dans ce didacticiel, nous expliquerons comment utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un document PDF. Nous fournirons un guide étape par étape sur la façon de procéder, ainsi qu'un exemple de code source.

## Étape 1 : Créer une nouvelle application de console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez le nommer comme bon vous semble. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Chargez le document PDF
Chargez le document PDF dont vous souhaitez obtenir les polices :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Obtenir toutes les polices
Obtenez toutes les polices utilisées dans le document PDF :

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Étape 5 : Imprimer toutes les polices
Imprimez toutes les polices utilisées dans le document PDF :

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Exemple de code source pour obtenir toutes les polices à l'aide d'Aspose.PDF pour .NET
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET. Obtenir toutes les polices utilisées dans un document PDF peut être utile si vous devez analyser ou manipuler par programme les polices dans un document PDF. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, notamment pour obtenir toutes les polices utilisées dans un document PDF.


