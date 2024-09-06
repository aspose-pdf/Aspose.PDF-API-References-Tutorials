---
title: Obtenir toutes les polices dans le fichier PDF
linktitle: Obtenir toutes les polices dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un fichier PDF par programmation avec ce guide étape par étape et cet exemple de code.
type: docs
weight: 160
url: /fr/net/programming-with-document/getallfonts/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PDF par programmation. L'une des fonctionnalités qu'elle offre est la possibilité d'obtenir toutes les polices utilisées dans un fichier PDF. Cela peut être utile si vous devez analyser ou manipuler par programmation les polices d'un fichier PDF.

Dans ce tutoriel, nous verrons comment utiliser Aspose.PDF pour .NET pour obtenir toutes les polices utilisées dans un document PDF. Nous fournirons un guide étape par étape sur la façon de procéder, ainsi qu'un exemple de code source.

## Étape 1 : créer une nouvelle application console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez lui donner le nom que vous souhaitez. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Charger le document PDF
Chargez le document PDF à partir duquel vous souhaitez obtenir les polices :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Obtenez toutes les polices
Obtenez toutes les polices utilisées dans le document PDF :

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Étape 5 : Imprimez toutes les polices
Imprimez toutes les polices utilisées dans le document PDF :

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Exemple de code source pour obtenir toutes les polices à l'aide d'Aspose.PDF pour .NET
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET. Obtenir toutes les polices utilisées dans un document PDF peut être utile si vous devez analyser ou manipuler par programmation les polices d'un document PDF. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, notamment pour obtenir toutes les polices utilisées dans un document PDF.

### FAQ

#### Q : Pourquoi aurais-je besoin d’obtenir toutes les polices utilisées dans un document PDF ?

R : Obtenir toutes les polices utilisées dans un document PDF peut être utile si vous devez analyser ou manipuler par programmation les polices à diverses fins, telles que le remplacement ou la personnalisation des polices.

#### Q : Comment puis-je obtenir toutes les polices utilisées dans un document PDF à l’aide d’Aspose.PDF pour .NET ?

 R : Vous pouvez obtenir toutes les polices utilisées dans un document PDF à l'aide d'Aspose.PDF pour .NET en appelant la fonction`GetAllFonts` méthode de la`FontUtilities` classe. Cette méthode renvoie un tableau de`Aspose.Pdf.Text.Font` objets, qui représentent les polices utilisées dans le document PDF.

#### Q : Puis-je filtrer les polices en fonction de certains critères ?

R : Oui, vous pouvez filtrer les polices en fonction de certains critères à l'aide d'Aspose.PDF pour .NET. Après avoir obtenu toutes les polices, vous pouvez les analyser par programmation et appliquer une logique de filtrage selon vos besoins.

#### Q : Aspose.PDF pour .NET est-il compatible avec différents formats de polices ?

R : Oui, Aspose.PDF pour .NET est compatible avec divers formats de polices, notamment les polices TrueType, OpenType et Type 1. Il peut fonctionner avec différents formats de polices et les gérer lors de la manipulation de documents PDF.