---
title: Cases à cocher groupées dans un document PDF
linktitle: Cases à cocher groupées dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des cases à cocher groupées dans un document PDF avec Aspose.PDF pour .NET.
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

### Exemple de code source pour les cases à cocher groupées à l'aide d'Aspose.PDF pour .NET 
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

### FAQ

#### Q : Que sont les cases à cocher groupées dans un document PDF ?

: Les cases à cocher groupées dans un document PDF font référence à un ensemble d'options de bouton radio qui sont regroupées. Les boutons radio permettent aux utilisateurs de sélectionner une seule option parmi un groupe de choix mutuellement exclusifs. Lorsqu'un bouton radio est sélectionné, les autres du même groupe sont automatiquement désélectionnés. Ce comportement de regroupement est utile lorsque vous souhaitez présenter plusieurs options aux utilisateurs tout en limitant leur sélection à un seul choix.

#### Q : Puis-je personnaliser l'apparence des cases à cocher groupées dans Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser l'apparence des cases à cocher groupées dans Aspose.PDF pour .NET. L'API fournit diverses options pour définir le style, la bordure et l'apparence des options de bouton radio. Vous pouvez définir la position de chaque option, choisir entre différents styles de boîte (par exemple, carré, cercle, croix) et ajuster les propriétés de bordure pour obtenir la représentation visuelle souhaitée.

#### Q : Comment puis-je ajouter des cases à cocher groupées à une page spécifique dans un document PDF ?

 : Pour ajouter des cases à cocher groupées à une page spécifique d'un document PDF, vous devez instancier un`RadioButtonField` objet avec le numéro de page souhaité comme argument. Ensuite, créez`RadioButtonOptionField` objets représentant chaque option de bouton radio et spécifiez leur position à l'aide de la`Rectangle` objet. Enfin, ajoutez ces options au`RadioButtonField` et personnalisez leur apparence selon vos besoins avant d'ajouter le`RadioButtonField` au formulaire de document.

#### Q : Puis-je ajouter plusieurs groupes de cases à cocher à un seul document PDF ?

 R : Oui, vous pouvez ajouter plusieurs groupes de cases à cocher à un seul document PDF. Chaque groupe doit avoir un`RadioButtonField` objet, et le`RadioButtonOptionField` les objets de chaque groupe doivent partager la même page et des noms uniques pour leurs options. Cela garantit que les boutons radio de chaque groupe fonctionnent correctement et que les sélections s'excluent mutuellement.

#### Q : Les cases à cocher groupées sont-elles prises en charge dans tous les visualiseurs et applications PDF ?

: Oui, les cases à cocher groupées sont prises en charge dans tous les visualiseurs et applications PDF conformes aux normes. La spécification PDF définit les boutons radio et leur comportement de regroupement, ce qui les rend universellement reconnus au format PDF. Cependant, il est essentiel de tester la fonctionnalité dans différents visualiseurs PDF pour garantir un comportement cohérent sur différentes plates-formes.