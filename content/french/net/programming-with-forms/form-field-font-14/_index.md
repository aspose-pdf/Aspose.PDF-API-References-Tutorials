---
title: Police du champ de formulaire 14
linktitle: Police du champ de formulaire 14
second_title: Aspose.PDF pour la référence de l'API .NET
description: Configurez facilement la police des champs de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-forms/form-field-font-14/
---
Dans ce didacticiel, nous allons vous montrer comment configurer la police d'un champ de formulaire à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# étape par étape pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Tout d'abord, assurez-vous d'avoir importé les bibliothèques nécessaires et défini le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : ouvrez le document

Ouvrez le document PDF existant :

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Étape 3 : Obtenez un champ de formulaire particulier

Obtenez le champ de formulaire souhaité (dans cet exemple, nous utilisons le champ "textbox1") :

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Étape 4 : Créer un objet police

Créez un objet police pour la nouvelle police que vous souhaitez utiliser (par exemple, "ComicSansMS") :

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Étape 5 : Configurer les informations de police pour le champ du formulaire

Configurez les informations de police pour le champ du formulaire à l'aide de la police créée précédemment :

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Étape 6 : Enregistrez le document mis à jour

Enregistrez le document PDF mis à jour :

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Exemple de code source pour Form Field Font 14 à l’aide d’Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Obtenir un champ de formulaire particulier à partir du document
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Créer un objet de police
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Définir les informations de police pour le champ du formulaire
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à configurer la police d'un champ de formulaire à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement spécifier la police et la taille de la police des champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF.

### FAQ

#### Q : Puis-je utiliser n'importe quelle police pour les champs de formulaire dans Aspose.PDF pour .NET ?

R : Oui, vous pouvez utiliser n'importe quelle police TrueType ou OpenType pour les champs de formulaire dans Aspose.PDF pour .NET. Tant que la police est disponible et installée sur le système ou accessible via FontRepository, vous pouvez l'utiliser pour personnaliser l'apparence du texte des champs de formulaire.

#### Q : Comment puis-je trouver les polices disponibles dans Aspose.PDF pour .NET ?

 R : Pour trouver les polices disponibles dans Aspose.PDF pour .NET, vous pouvez utiliser le`FontRepository.GetAvailableFonts()`méthode. Cette méthode renvoie un tableau de polices disponibles que vous pouvez utiliser pour les champs de formulaire ou toute autre opération liée au texte dans votre document PDF.

#### Q : Puis-je modifier la taille de la police des champs de formulaire en n'importe quelle valeur ?

R : Oui, vous pouvez modifier la taille de la police des champs de formulaire en n'importe quelle valeur numérique positive à l'aide d'Aspose.PDF pour .NET. Cependant, il est essentiel de s'assurer que la taille de la police est adaptée au champ de formulaire spécifique et n'entraîne pas de troncature du texte ou de chevauchement avec d'autres éléments du document.

#### Q : Puis-je modifier la couleur de la police des champs de formulaire ?

R : Oui, vous pouvez modifier la couleur de la police des champs de formulaire à l'aide d'Aspose.PDF pour .NET. Dans le code source C# fourni, la couleur de la police est définie sur noir (`System.Drawing.Color.Black`), mais vous pouvez le personnaliser avec n'importe quelle autre valeur de couleur valide.

#### Q : Comment puis-je aligner le texte dans le champ du formulaire ?

 R : Pour aligner le texte dans le champ du formulaire, vous pouvez utiliser le`Multiline`propriété du champ de formulaire et définissez-la sur true. Cette propriété active le texte multiligne dans le champ du formulaire, vous permettant de contrôler l'alignement du texte avec les sauts de ligne et les retours chariot.