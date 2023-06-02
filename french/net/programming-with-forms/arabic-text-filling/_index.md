---
title: Remplissage de texte arabe
linktitle: Remplissage de texte arabe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Remplissez facilement les champs de formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-forms/arabic-text-filling/
---

Dans ce didacticiel, nous allons apprendre à remplir un champ de formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui permet aux développeurs de manipuler par programmation des documents PDF. Nous vous guiderons pas à pas tout au long du processus, en vous expliquant le code source C# requis pour accomplir cette tâche.

## Étape 1 : charger le contenu du formulaire PDF

Tout d'abord, nous devons charger le formulaire PDF contenant le champ que nous voulons remplir. Nous commençons par définir le chemin vers le répertoire où se trouve le formulaire :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ensuite, nous créons un`FileStream` objet pour lire et écrire le fichier formulaire :

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Ensuite, nous instancions un`Document` objet utilisant le flux qui contient le fichier de formulaire :

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Étape 2 : Accéder au champ TextBoxField

 Pour remplir le champ du formulaire avec du texte arabe, nous devons accéder au`TextBoxField` champ que nous voulons remplir. Dans cet exemple, nous supposons que le nom du champ est "textbox1". Nous pouvons récupérer la référence du champ à l'aide de la`Form` propriété de la`pdfDocument` objet:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Étape 3 : Remplissez le champ du formulaire avec du texte arabe

 Maintenant que nous avons le`TextBoxField` référence, on peut assigner le texte arabe à son`Value` propriété:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Étape 4 : Enregistrer le document mis à jour

Enfin, nous enregistrons le document mis à jour dans un nouveau fichier :

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Nous affichons également un message pour indiquer le succès du remplissage du texte arabe :

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Exemple de code source pour le remplissage de texte arabe à l'aide de Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le contenu du formulaire PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Instancier l'instance de document avec le flux contenant le fichier de formulaire
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtenir la référence d'un TextBoxField particulier
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Remplir le champ du formulaire avec du texte arabe
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment remplir un champ de formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET. Nous avons parcouru le processus étape par étape et expliqué le code source C # pertinent. En suivant ces instructions, vous pouvez facilement intégrer la fonctionnalité de remplissage de texte arabe dans vos applications .NET. Si vous avez d'autres questions ou avez besoin de plus d'informations, n'hésitez pas à contacter l'équipe d'assistance Aspose.PDF ou à consulter les ressources supplémentaires ci-dessous.