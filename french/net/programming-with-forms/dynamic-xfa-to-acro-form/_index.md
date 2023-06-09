---
title: Formulaire XFA dynamique vers Acro
linktitle: Formulaire XFA dynamique vers Acro
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement les formulaires XFA To dynamiques en formulaires AcroForm standard avec Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

Dans ce didacticiel, nous allons vous montrer comment convertir un formulaire dynamique XFA en AcroForm en utilisant Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le formulaire XFA dynamique

Chargez le formulaire XFA dynamique :

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Étape 3 : Définissez le type de formulaire sur AcroForm standard

Définissez le type de formulaire sur AcroForm standard :

```csharp
document.Form.Type = FormType.Standard;
```

## Étape 4 : Enregistrez le PDF obtenu

Enregistrez le PDF obtenu :

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Exemple de code source pour Dynamic XFA To Acro Form en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le formulaire XFA dynamique
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Définissez le type de champs de formulaire sur AcroForm standard
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Enregistrez le PDF résultant
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à convertir un formulaire dynamique XFA en formulaire AcroForm standard à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement convertir vos formulaires dynamiques XFATo en AcroForms pour une utilisation plus courante.