---
title: Obtenir des valeurs de tous les champs
linktitle: Obtenir des valeurs de tous les champs
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement les valeurs de tous les champs de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-forms/get-values-from-all-fields/
---

Dans ce didacticiel, nous allons vous montrer comment obtenir les valeurs de tous les champs de formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document

Ouvrez le document PDF :

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Étape 3 : Obtenir des valeurs pour tous les champs

Parcourez tous les champs de formulaire du document et obtenez leurs noms et leurs valeurs :

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Exemple de code source pour Get Values From All Fields en utilisant Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Obtenir des valeurs de tous les champs
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir les valeurs de tous les champs de formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement extraire les valeurs de tous les champs de formulaire de vos documents PDF à l'aide d'Aspose.PDF.