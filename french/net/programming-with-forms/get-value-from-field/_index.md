---
title: Obtenir la valeur du champ
linktitle: Obtenir la valeur du champ
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement la valeur d'un champ de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 140
url: /fr/net/programming-with-forms/get-value-from-field/
---

Dans ce tutoriel, nous allons vous montrer comment obtenir la valeur d'un champ de formulaire en utilisant Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document

Ouvrez le document PDF :

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Étape 3 : Obtenir le champ

Obtenez le champ de formulaire souhaité (dans cet exemple, nous utilisons le champ "textbox1") :

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Étape 4 : Obtenir la valeur du champ

 Obtenez la valeur du champ à l'aide de la`Value` propriété:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Exemple de code source pour Get Value From Field en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Obtenir un champ
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Obtenir la valeur du champ
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir la valeur d'un champ de formulaire à l'aide de Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement extraire la valeur d'un champ de formulaire spécifique dans vos documents PDF à l'aide d'Aspose.PDF.