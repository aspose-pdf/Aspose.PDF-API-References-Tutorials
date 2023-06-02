---
title: Boîte combo
linktitle: Boîte combo
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement une liste de zones de liste déroulante dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-forms/combo-box/
---

Dans ce didacticiel, nous allons vous montrer comment créer une liste déroulante à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un objet de document

Créez un objet Document pour contenir le formulaire PDF :

```csharp
Document doc = new Document();
```

## Étape 3 : Ajouter une page

Ajouter une page au document :

```csharp
doc.Pages.Add();
```

## Étape 4 : instancier un objet ComboBoxField

Instanciez un objet ComboBoxField avec les dimensions souhaitées :

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Étape 5 : Ajouter des options à la liste déroulante

Ajoutez les options souhaitées à la liste déroulante :

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Étape 6 : Ajoutez la liste déroulante au formulaire

Ajoutez l'objet ComboBoxField à la collection Document Form Fields :

```csharp
doc.Form.Add(combo);
```

## Étape 7 : Enregistrez le document

Enregistrez le document PDF :

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Combo Box utilisant Aspose.Words pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Créer un objet Document
	Document doc = new Document();
	// Ajouter une page à l'objet document
	doc.Pages.Add();
	// Instancier l'objet ComboBox Field
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Ajouter une option à ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Ajouter un objet de zone de liste déroulante à la collection de champs de formulaire de l'objet de document
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Enregistrez le document PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer une liste de zones de liste déroulante à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement ajouter une liste de zones de liste déroulante à vos documents PDF à l'aide d'Aspose.PDF.