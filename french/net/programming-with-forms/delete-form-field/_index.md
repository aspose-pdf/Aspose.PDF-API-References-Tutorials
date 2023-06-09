---
title: Supprimer le champ du formulaire
linktitle: Supprimer le champ du formulaire
second_title: Référence de l'API Aspose.PDF pour .NET
description: Supprimez facilement les champs de formulaire indésirables de vos documents PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-forms/delete-form-field/
---

Dans ce didacticiel, nous allons vous montrer comment supprimer un champ de formulaire à l'aide de Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

Ouvrez le document PDF existant :

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Étape 3 : Supprimer un champ particulier

Supprimez un champ de formulaire particulier en utilisant son nom :

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Étape 4 : Enregistrer le document modifié

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Supprimer le champ de formulaire à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Supprimer un champ particulier par son nom
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Enregistrer le document modifié
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à supprimer un champ de formulaire à l'aide de Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement supprimer les champs de formulaire indésirables de vos documents PDF à l'aide d'Aspose.PDF.