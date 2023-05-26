---
title: Déterminer les progrès
linktitle: Déterminer les progrès
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à déterminer la progression du processus de conversion d'un document PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape et cet exemple de code.
type: docs
weight: 110
url: /fr/net/programming-with-document/determineprogress/
---

Aspose.PDF pour .NET fournit une fonctionnalité qui vous permet de déterminer la progression du processus de conversion d'un document PDF. Dans ce didacticiel, nous fournirons un guide étape par étape sur la façon d'implémenter cette fonctionnalité à l'aide de C# et Aspose.PDF pour .NET.

## Étape 1 : Chargement du document PDF

La première étape consiste à charger le document PDF que vous souhaitez convertir. Pour ce tutoriel, nous utiliserons le fichier "AddTOC.pdf". Remplacez le chemin d'accès à ce fichier par le chemin d'accès à votre propre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## Étape 2 : Configurer le gestionnaire de progression personnalisé

 Ensuite, nous devons configurer le gestionnaire de progression personnalisé qui sera appelé pendant le processus de conversion. Dans ce tutoriel, nous utiliserons le`ConversionProgressEventHandler` délégué fourni par Aspose.PDF pour .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## Étape 3 : Enregistrer le document PDF

 Enfin, nous devons enregistrer le document PDF en utilisant le`Save()` méthode de la`Document`objet. Nous transmettrons le gestionnaire de progression personnalisé que nous avons configuré à l'étape précédente en tant que paramètre.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## Étape 4 : implémenter le gestionnaire de progression

 Pour implémenter le gestionnaire de progression, nous devons définir une méthode qui prend un seul paramètre de type`ConversionProgressEventArgs`. Cette méthode sera appelée pendant le processus de conversion pour signaler la progression de la conversion.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### Exemple de code source pour déterminer la progression à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## Conclusion

Dans ce didacticiel, nous avons fourni un guide étape par étape sur la façon de déterminer la progression du processus de conversion d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous avons également fourni un exemple de code que vous pouvez utiliser comme référence lors de l'implémentation de cette fonctionnalité dans votre propre application.