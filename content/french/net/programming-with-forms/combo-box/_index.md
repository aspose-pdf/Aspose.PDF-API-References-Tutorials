---
title: Zone de liste déroulante
linktitle: Zone de liste déroulante
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement une liste déroulante dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-forms/combo-box/
---
Dans ce tutoriel, nous vous montrerons comment créer une liste déroulante à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# étape par étape pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Tout d’abord, assurez-vous d’avoir importé les bibliothèques nécessaires et défini le chemin d’accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un objet de document

Créez un objet Document pour contenir le formulaire PDF :

```csharp
Document doc = new Document();
```

## Étape 3 : Ajouter une page

Ajouter une page au document :

```csharp
doc.Pages.Add();
```

## Étape 4 : instancier un objet ComboBoxField

Instanciez un objet ComboBoxField avec les dimensions souhaitées :

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Étape 5 : ajouter des options à la liste déroulante

Ajoutez les options souhaitées à la liste déroulante :

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Étape 6 : ajouter la liste déroulante au formulaire

Ajoutez l’objet ComboBoxField à la collection Document Form Fields :

```csharp
doc.Form.Add(combo);
```

## Étape 7 : Enregistrer le document

Enregistrer le document PDF :

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Combo Box utilisant Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin vers le répertoire des documents.
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
	// Enregistrer le document PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce tutoriel, nous avons appris à créer une liste déroulante à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement ajouter une liste déroulante à vos documents PDF à l'aide d'Aspose.PDF.

### FAQ

#### Q : Puis-je personnaliser l’apparence de la liste déroulante à l’aide d’Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser l'apparence de la liste déroulante à l'aide d'Aspose.PDF pour .NET. Vous pouvez définir des propriétés telles que la taille de la police, la couleur, la couleur d'arrière-plan, le style de bordure, etc. pour correspondre à l'apparence souhaitée.

#### Q : Puis-je définir des options sélectionnées par défaut dans la liste déroulante ?

 R : Oui, vous pouvez définir des options sélectionnées par défaut dans la liste déroulante à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser l'`Selected` propriété de la`ComboBoxField` objet permettant de marquer une ou plusieurs options comme sélectionnées par défaut.

#### Q : Comment puis-je récupérer la valeur sélectionnée dans la liste déroulante une fois que l'utilisateur a effectué une sélection ?

 R : Vous pouvez récupérer la valeur sélectionnée dans la liste déroulante à l'aide d'Aspose.PDF pour .NET. Une fois que l'utilisateur a effectué une sélection, vous pouvez accéder à la`Value` propriété de la`ComboBoxField`objet pour obtenir la valeur sélectionnée.

#### Q : Est-il possible d’ajouter des gestionnaires d’événements ou des actions à la liste déroulante ?

 R : Oui, Aspose.PDF pour .NET vous permet d'ajouter des gestionnaires d'événements ou des actions à la liste déroulante. Vous pouvez associer des actions JavaScript, telles que`OnValueChanged`, à la liste déroulante pour effectuer des actions spécifiques lorsque l'utilisateur sélectionne une option.

#### Q : Puis-je ajouter des info-bulles ou des descriptions aux options de la liste déroulante ?

 R : Oui, vous pouvez ajouter des info-bulles ou des descriptions aux options de la liste déroulante à l'aide d'Aspose.PDF pour .NET. Vous pouvez définir les`AlternateName` propriété de chaque option pour fournir une info-bulle ou une description qui s'affichera lorsque l'utilisateur survolera l'option.