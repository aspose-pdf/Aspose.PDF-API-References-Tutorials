---
title: Modifier le champ du formulaire
linktitle: Modifier le champ du formulaire
second_title: Référence de l'API Aspose.PDF pour .NET
description: Modifiez facilement les champs de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-forms/modify-form-field/
---

Dans ce didacticiel, nous allons vous montrer comment modifier un champ de formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document

Chargez le document PDF existant :

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Étape 3 : Obtenir le champ du formulaire

Obtenez le champ de formulaire que vous souhaitez modifier :

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Étape 4 : modifier la valeur du champ

Modifiez la valeur du champ de formulaire :

```csharp
textBoxField.Value = "New Value";
```

## Étape 5 : modifier les propriétés du champ

Modifiez les propriétés de champ de formulaire supplémentaires selon vos besoins. Par exemple, vous pouvez le rendre en lecture seule :

```csharp
textBoxField.ReadOnly = true;
```

## Étape 6 : Enregistrer le document modifié

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Modifier le champ de formulaire à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Obtenir un champ
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifier la valeur du champ
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à modifier un champ de formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement accéder à un champ spécifique, modifier sa valeur et ajuster ses propriétés selon vos besoins.