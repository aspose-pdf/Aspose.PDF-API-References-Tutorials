---
title: Police du champ de formulaire 14
linktitle: Police du champ de formulaire 14
second_title: Référence de l'API Aspose.PDF pour .NET
description: Configurez facilement la police des champs de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-forms/form-field-font-14/
---

Dans ce didacticiel, nous allons vous montrer comment configurer la police d'un champ de formulaire à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

Ouvrez le document PDF existant :

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Étape 3 : Obtenir un champ de formulaire particulier

Obtenez le champ de formulaire souhaité (dans cet exemple, nous utilisons le champ "textbox1") :

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Étape 4 : Créer un objet police

Créez un objet de police pour la nouvelle police que vous souhaitez utiliser (par exemple, "ComicSansMS") :

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Étape 5 : configurer les informations de police pour le champ de formulaire

Configurez les informations de police pour le champ de formulaire à l'aide de la police créée précédemment :

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Étape 6 : Enregistrer le document mis à jour

Enregistrez le document PDF mis à jour :

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Exemple de code source pour Form Field Font 14 en utilisant Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
//Obtenir un champ de formulaire particulier à partir du document
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Créer un objet police
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Définir les informations de police pour le champ de formulaire
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à configurer la police d'un champ de formulaire à l'aide de Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement spécifier la police et la taille de police des champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF.