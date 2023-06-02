---
title: Boutons radio horizontalement et verticalement
linktitle: Boutons radio horizontalement et verticalement
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des boutons radio horizontaux et verticaux dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 180
url: /fr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

Dans ce didacticiel, nous allons vous montrer comment créer des boutons radio disposés horizontalement et verticalement dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document

Chargez le document PDF existant :

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Étape 3 : Personnalisez les options des boutons radio

Personnalisez les options des boutons radio en définissant les propriétés suivantes :

```csharp
formEditor. RadioGap = 4; // Distance entre deux options de bouton radio
formEditor. RadioHoriz = true; // Disposition horizontale des boutons radio
formEditor.RadioButtonItemSize = 20; // Taille des boutons radio
formEditor.Facade.BorderWidth = 1; // Largeur de la bordure du bouton radio
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Couleur de la bordure du bouton radio
```

## Étape 4 : Ajouter des boutons radio horizontaux

Ajoutez des boutons radio disposés horizontalement en spécifiant les options et la position du champ :

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Étape 5 : Ajouter des boutons radio verticaux

Ajoutez des boutons radio disposés verticalement en spécifiant les options et la position du champ :

```csharp
formEditor. RadioHoriz = false; // Disposition verticale des boutons radio
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Étape 6 : Enregistrez le document

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Exemple de code source pour les boutons radio horizontalement et verticalement à l'aide de Aspose.Words pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le document précédemment enregistré
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap est la distance entre deux options de bouton radio.
	formEditor.RadioGap = 4;
	// Ajouter un bouton radio horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize si la taille de l'élément du bouton radio.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Ajouter un autre bouton radio situé verticalement
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Enregistrez le document PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer des boutons radio disposés horizontalement et verticalement dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement personnaliser la disposition des boutons radio et les ajouter à vos documents PDF à l'aide d'Aspose.PDF.