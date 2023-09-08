---
title: Obtenez toutes les polices dans un fichier PDF
linktitle: Obtenez toutes les polices dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un fichier PDF par programme avec ce guide étape par étape et cet exemple de code.
type: docs
weight: 160
url: /fr/net/programming-with-document/getallfonts/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PDF par programme. L'une des fonctionnalités qu'il offre est la possibilité d'obtenir toutes les polices utilisées dans un fichier PDF. Cela peut être utile si vous devez analyser ou manipuler par programme les polices d'un fichier PDF.

Dans ce didacticiel, nous verrons comment utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un document PDF. Nous fournirons un guide étape par étape sur la façon de procéder, ainsi qu'un exemple de code source.

## Étape 1 : Créer une nouvelle application console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez le nommer comme vous le souhaitez. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Charger le document PDF
Chargez le document PDF à partir duquel vous souhaitez obtenir les polices :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Obtenez toutes les polices
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
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET. Obtenir toutes les polices utilisées dans un document PDF peut être utile si vous devez analyser ou manipuler par programme les polices d'un document PDF. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, notamment pour obtenir toutes les polices utilisées dans un document PDF.

### FAQ

#### Q : Pourquoi aurais-je besoin de toutes les polices utilisées dans un document PDF ?

R : Obtenir toutes les polices utilisées dans un document PDF peut être utile si vous devez analyser ou manipuler les polices par programme à diverses fins, telles que le remplacement ou la personnalisation des polices.

#### Q : Comment puis-je obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Vous pouvez obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET en appelant le`GetAllFonts` méthode du`FontUtilities` classe. Cette méthode renvoie un tableau de`Aspose.Pdf.Text.Font` objets, qui représentent les polices utilisées dans le document PDF.

#### Q : Puis-je filtrer les polices en fonction de certains critères ?

R : Oui, vous pouvez filtrer les polices en fonction de certains critères à l'aide d'Aspose.PDF pour .NET. Après avoir obtenu toutes les polices, vous pouvez analyser les polices par programme et appliquer une logique de filtrage si nécessaire.

#### Q : Aspose.PDF pour .NET est-il compatible avec différents formats de police ?

R : Oui, Aspose.PDF pour .NET est compatible avec différents formats de polices, notamment les polices TrueType, OpenType et Type 1. Il peut fonctionner avec différents formats de polices et les gérer lors de la manipulation de documents PDF.