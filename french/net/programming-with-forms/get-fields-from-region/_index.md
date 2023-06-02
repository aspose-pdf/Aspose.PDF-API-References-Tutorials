---
title: Obtenir les champs de la région
linktitle: Obtenir les champs de la région
second_title: Référence de l'API Aspose.PDF pour .NET
description: Insérez facilement des champs d'une région spécifique dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 130
url: /fr/net/programming-with-forms/get-fields-from-region/
---

Dans ce tutoriel, nous allons vous montrer comment obtenir les champs d'une région spécifique dans un document PDF en utilisant Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le fichier PDF

Ouvrez le fichier PDF :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Étape 3 : Créer un objet rectangle pour délimiter la région

Créez un objet rectangle pour délimiter la région où vous souhaitez obtenir les champs :

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Étape 4 : Obtenir le formulaire PDF

Obtenir le formulaire PDF du document :

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Étape 5 : Obtenir les champs dans la région rectangulaire

Obtenez les champs situés dans la région rectangulaire spécifiée :

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Étape 6 : Afficher les noms et les valeurs des champs

Parcourez les champs résultants et affichez leurs noms et leurs valeurs :

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Exemple de code source pour Get Fields From Region en utilisant Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le fichier pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Créer un objet rectangle pour obtenir des champs dans cette zone
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Obtenir le formulaire PDF
Aspose.Pdf.Forms.Form form = doc.Form;
//Obtenir des champs dans la zone rectangulaire
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Afficher les noms et les valeurs des champs
foreach (Field field in fields)
{
	// Afficher les propriétés d'emplacement d'image pour tous les emplacements
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir les champs d'une région spécifique dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement extraire les champs situés dans une zone rectangulaire donnée de votre document PDF à l'aide d'Aspose.PDF.