---
title: Sélectionnez le bouton radio dans le document PDF
linktitle: Sélectionnez le bouton radio dans le document PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment sélectionner un bouton radio dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 250
url: /fr/net/programming-with-forms/select-radio-button/
---
Voici un didacticiel détaillé sur la façon de sélectionner un bouton radio à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes:

##  Étape 1 : Commencez par définir le répertoire de vos documents en précisant le chemin dans le`dataDir` variable.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Étape 2 : Ouvrez le document PDF à l'aide du`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Étape 3 : Obtenez le champ du bouton radio à partir du formulaire de document.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Étape 4 : Spécifiez l'index du bouton radio à sélectionner dans le groupe.

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

### Exemple de code source pour Sélectionner le bouton radio à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Obtenez un champ
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

Dans ce didacticiel, nous avons appris à sélectionner un bouton radio à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez manipuler et modifier les boutons radio de vos documents PDF à l'aide d'Aspose.PDF pour .NET.


### FAQ

#### Q : Puis-je sélectionner plusieurs boutons radio dans un groupe à l’aide d’Aspose.PDF pour .NET ?

R : Non, les boutons radio d'un groupe sont conçus pour s'exclure mutuellement. Vous ne pouvez sélectionner qu’un seul bouton radio à la fois au sein d’un groupe, et en sélectionner un désélectionnera automatiquement tout bouton radio précédemment sélectionné dans le même groupe.

#### Q : Comment récupérer le bouton radio sélectionné dans un groupe à l'aide d'Aspose.PDF pour .NET ?

 R : Pour récupérer le bouton radio sélectionné dans un groupe, vous pouvez utiliser le`Selected` propriété du`RadioButtonField` classe. Il renverra l’index du bouton radio sélectionné dans le groupe.

#### Q : Puis-je personnaliser l'apparence du bouton radio sélectionné dans le document PDF ?

: Oui, vous pouvez personnaliser l'apparence du bouton radio sélectionné à l'aide d'Aspose.PDF pour .NET. Vous pouvez modifier sa couleur, sa taille, son style de bordure et d'autres attributs visuels pour qu'ils correspondent à l'apparence souhaitée.

#### Q : Est-il possible de créer de nouveaux groupes de boutons radio par programmation à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez créer de nouveaux groupes de boutons radio par programmation à l'aide d'Aspose.PDF pour .NET. Vous pouvez ajouter de nouveaux boutons radio au formulaire du document et spécifier le même nom de groupe pour chaque bouton radio afin de créer un nouveau groupe.

#### Q : Aspose.PDF pour .NET prend-il en charge l'utilisation de formulaires PDF interactifs ?

R : Oui, Aspose.PDF pour .NET prend entièrement en charge l'utilisation de formulaires PDF interactifs, notamment les boutons radio, les champs de texte, les cases à cocher et d'autres éléments de formulaire. Vous pouvez facilement lire, modifier et créer des formulaires PDF interactifs à l'aide de la bibliothèque.