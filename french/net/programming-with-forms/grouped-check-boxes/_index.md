---
title: Cases à cocher groupées
linktitle: Cases à cocher groupées
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des cases à cocher groupées dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 170
url: /fr/net/programming-with-forms/grouped-check-boxes/
---

Dans ce didacticiel, nous allons vous montrer comment créer des cases à cocher groupées dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : instancier un objet document

Instanciez un objet Document :

```csharp
Document pdfDocument = new Document();
```

## Étape 3 : Ajouter une page au document PDF

Ajouter une page au document PDF :

```csharp
Page page = pdfDocument.Pages.Add();
```

## Étape 4 : instancier un objet RadioButtonField

Instanciez un objet RadioButtonField avec le numéro de page comme argument :

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Étape 5 : Ajouter des options de bouton radio

Ajoutez des options de bouton radio à l'aide de l'objet RadioButtonOptionField et spécifiez leur position à l'aide de l'objet Rectangle :

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Étape 6 : Personnalisez les options des boutons radio

Personnalisez les options des boutons radio en définissant leur style, leur bordure et leur apparence :

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Étape 7 : Ajouter les boutons radio au formulaire

Ajoutez les boutons radio à l'objet de formulaire de document :

```csharp
pdfDocument.Form.Add(radio);
```

## Étape 8 : Enregistrez le document

Enregistrez le document PDF :

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour les cases à cocher groupées à l'aide d'Aspose.Words pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instancier l'objet Document
	Document pdfDocument = new Document();
	// Ajouter une page au fichier PDF
	Page page = pdfDocument.Pages.Add();
	// Créer un objet RadioButtonField avec le numéro de page comme argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Ajouter la première option de bouton radio et spécifier également son origine à l'aide de l'objet Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Ajouter un bouton radio à l'objet de formulaire de l'objet Document
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Enregistrez le document PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer des cases à cocher groupées dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement ajouter des options de bouton radio personnalisées et les regrouper dans vos documents PDF à l'aide d'Aspose.PDF.