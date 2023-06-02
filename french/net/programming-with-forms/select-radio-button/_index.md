---
title: Sélectionner le bouton radio
linktitle: Sélectionner le bouton radio
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à sélectionner un bouton radio dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 250
url: /fr/net/programming-with-forms/select-radio-button/
---

Voici un tutoriel détaillé sur la façon de sélectionner un bouton radio en utilisant Aspose.PDF pour .NET. Suivez ces étapes:

##  Etape 1 : Commencez par définir le répertoire de vos documents en précisant le chemin dans le`dataDir` variable.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Étape 2 : Ouvrez le document PDF à l'aide du`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Étape 3 : Récupérez le champ du bouton radio à partir du formulaire de document.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Étape 4 : Spécifiez l'index du bouton radio à sélectionner dans le groupe.

```csharp
radioField. Selected = 2;
```

## Étape 5 : Définissez le chemin de sortie du fichier PDF modifié.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Étape 6 : Enregistrez le fichier PDF modifié.

```csharp
pdfDocument.Save(dataDir);
```

## Étape 7 : Affichez un message de confirmation et l'emplacement du fichier enregistré.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour Select Radio Button en utilisant Aspose.Words pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Obtenir un champ
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Spécifiez l'index du bouton radio du groupe
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Enregistrez le fichier PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à sélectionner un bouton radio à l'aide de Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez manipuler et modifier les boutons radio dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.