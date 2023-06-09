---
title: Remplir le champ du formulaire
linktitle: Remplir le champ du formulaire
second_title: Référence de l'API Aspose.PDF pour .NET
description: Remplissez facilement les champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-forms/fill-form-field/
---

Dans ce didacticiel, nous allons vous montrer comment remplir un champ de formulaire à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

Ouvrez le document PDF existant :

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Étape 3 : Obtenir le champ

Obtenez le champ de formulaire souhaité (dans cet exemple, nous utilisons le champ "textbox1") :

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Étape 4 : modifier la valeur du champ

Modifiez la valeur du champ avec la valeur souhaitée :

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Étape 5 : Enregistrer le document mis à jour

Enregistrez le document PDF mis à jour :

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Remplir le champ de formulaire à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Obtenir un champ
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifier la valeur du champ
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à remplir un champ de formulaire à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement modifier les valeurs des champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF.