---
title: Créer un document
linktitle: Créer un document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement un document avec des boutons radio en utilisant Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-forms/create-doc/
---
Dans ce tutoriel, nous allons vous montrer comment créer un document avec des boutons radio en utilisant Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

##Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document

Créez un nouvel objet Document pour contenir le document PDF :

```csharp
Document doc = new Document();
```

## Étape 3 : Ajouter une page

Ajouter une nouvelle page au document :

```csharp
Page page = doc.Pages.Add();
```

## Étape 4 : Ajouter un champ de bouton radio

Créez un champ de bouton radio et définissez sa position et sa taille :

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Étape 5 : Ajouter des options de bouton radio

Ajoutez les options souhaitées au champ du bouton radio. Vous pouvez définir les coordonnées et la taille de chaque option selon vos besoins :

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Étape 6 : Ajouter le champ du bouton radio au formulaire

Ajoutez le champ de bouton radio à la collection Champs de formulaire de document :

```csharp
doc.Form.Add(field);
```

## Étape 7 : Enregistrez le document

Enregistrez le document PDF :

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Create Doc à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Créer un nouveau document
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Ajouter un champ de bouton radio
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Ajouter des options de bouton radio. veuillez noter que ces options sont situées
	// Ni horizontalement ni verticalement.
	// Vous pouvez essayer de définir toutes les coordonnées (et même la taille) pour eux.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Enregistrez le document PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce tutoriel, nous avons appris à créer un document avec des boutons radio en utilisant Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement ajouter des boutons radio à vos documents PDF en utilisant Aspose.PDF.

### FAQ

#### Q : Puis-je personnaliser l'apparence des boutons radio dans le document à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser l'apparence des boutons radio dans le document à l'aide d'Aspose.PDF pour .NET. Vous pouvez définir des propriétés telles que la taille, la couleur, le style de bordure, etc. pour personnaliser l'apparence des boutons radio.

#### Q : Comment puis-je ajouter des groupes de boutons radio avec des options mutuellement exclusives ?

R : Afin de créer des options mutuellement exclusives, vous pouvez ajouter plusieurs champs de bouton radio avec le même nom. Cela garantira que lorsqu'une option est sélectionnée, les autres options portant le même nom seront automatiquement désélectionnées.

#### Q : Est-il possible de définir une option sélectionnée par défaut pour les boutons radio ?

R : Oui, vous pouvez définir une option sélectionnée par défaut pour les boutons radio à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser le`Selected` propriété de la`RadioButtonOptionField` objet pour marquer une option comme sélectionnée par défaut.

#### Q : Puis-je ajouter des gestionnaires d'événements aux boutons radio ?

 R : Oui, vous pouvez ajouter des gestionnaires d'événements aux boutons radio en utilisant Aspose.PDF pour .NET. Vous pouvez associer des actions JavaScript, telles que`OnValueChanged`, aux boutons radio pour effectuer des actions spécifiques lorsque l'utilisateur sélectionne une option.

#### Q : Comment puis-je récupérer l'option sélectionnée dans le groupe de boutons radio une fois que l'utilisateur a effectué une sélection ?

 R : Vous pouvez récupérer l'option sélectionnée dans le groupe de boutons radio à l'aide d'Aspose.PDF pour .NET. Une fois que l'utilisateur a effectué une sélection, vous pouvez accéder à la`Selected` propriété de la`RadioButtonOptionField` objet pour vérifier quelle option est sélectionnée.