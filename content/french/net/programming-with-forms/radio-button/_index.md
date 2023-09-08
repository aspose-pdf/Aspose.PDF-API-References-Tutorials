---
title: Bouton radio
linktitle: Bouton radio
second_title: Aspose.PDF pour la référence de l'API .NET
description: Ajoutez facilement des boutons radio à vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 220
url: /fr/net/programming-with-forms/radio-button/
---
Dans ce didacticiel, nous allons vous montrer comment ajouter un bouton radio dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# étape par étape pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et défini le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : instancier un objet de document

Instanciez un objet Document pour créer un nouveau document PDF :

```csharp
Document pdfDocument = new Document();
```

## Étape 3 : Ajouter une page

Ajouter une page au document PDF :

```csharp
pdfDocument.Pages.Add();
```

## Étape 4 : instancier un objet RadioButtonField

Instanciez un objet RadioButtonField en spécifiant le numéro de page comme argument :

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Étape 5 : Ajouter des options de boutons radio

Ajoutez des options de bouton radio à l'objet RadioButtonField en spécifiant les coordonnées de chaque option avec un objet Rectangle :

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Étape 6 : Ajoutez le bouton radio au formulaire

Ajoutez le bouton radio à l'objet Form du document :

```csharp
pdfDocument.Form.Add(radio);
```

## Étape 7 : Enregistrez le document PDF

Enregistrez le document PDF créé :

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour le bouton radio utilisant Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instancier l'objet Document
	Document pdfDocument = new Document();
	// Ajouter une page au fichier PDF
	pdfDocument.Pages.Add();
	// Instancier un objet RadioButtonField avec le numéro de page comme argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Ajoutez la première option de bouton radio et spécifiez également son origine à l'aide de l'objet Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Ajouter une deuxième option de bouton radio
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Ajouter un bouton radio pour former un objet de l'objet Document
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Enregistrez le fichier PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter un bouton radio dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement créer un bouton radio et le placer sur une page spécifique de votre document PDF.


### FAQ

#### Q : Puis-je personnaliser l’apparence du bouton radio, comme sa taille et sa couleur ?

 R : Oui, vous pouvez personnaliser l'apparence du bouton radio à l'aide du bouton`Rectangle` les coordonnées de l'objet pour définir sa taille et sa position. Aspose.PDF pour .NET vous permet d'ajuster l'apparence du bouton radio en fonction de vos besoins.

#### Q : Puis-je ajouter plusieurs boutons radio avec différents groupes sur la même page ?

R : Oui, vous pouvez ajouter plusieurs boutons radio avec différents groupes sur la même page. Chaque groupe de boutons radio peut avoir un nom unique et une seule option au sein de chaque groupe peut être sélectionnée à la fois.

#### Q : Comment puis-je ajouter une étiquette ou une description textuelle aux options des boutons radio ?

 R : Pour ajouter une étiquette ou une description textuelle aux options du bouton radio, vous pouvez utiliser l'option`TextStamp`classe d'Aspose.PDF pour .NET pour superposer du texte sur le document PDF à des coordonnées spécifiques.

#### Q : Aspose.PDF pour .NET est-il compatible avec toutes les versions de .NET Framework ?

R : Oui, Aspose.PDF pour .NET est compatible avec toutes les versions de .NET Framework, y compris .NET Core et .NET Standard.

#### Q : Puis-je contrôler par programme la sélection d’une option de bouton radio dans le document PDF ?

 R : Oui, vous pouvez contrôler par programme la sélection d'une option de bouton radio à l'aide de l'option`IsSelected` propriété du`RadioButtonOption` classe. Cette propriété vous permet de définir une option spécifique comme sélectionnée.