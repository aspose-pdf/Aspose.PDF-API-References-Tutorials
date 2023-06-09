---
title: Tampons de numéro de page
linktitle: Tampons de numéro de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des tampons de numéro de page à un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Dans ce tutoriel, nous vous guiderons étape par étape sur la façon d'ajouter des tampons de numéro de page à un document PDF en utilisant Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour ouvrir un document PDF existant, créer un tampon de numéro de page, définir ses propriétés et l'ajouter à une page spécifique du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Charger le document PDF existant

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF existant
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : création et configuration du tampon de numérotation des pages

Maintenant que le document PDF est chargé, nous pouvons créer un tampon de numérotation des pages et le configurer selon nos besoins. Voici comment:

```csharp
// Créer un tampon de numéro de page
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Définir si le tampon est en arrière-plan ou non
pageNumberStamp.Background = false;

// Format du tampon de numérotation des pages
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Marge inférieure du tampon de numérotation des pages
pageNumberStamp.BottomMargin = 10;

// Alignement horizontal du tampon de numérotation des pages
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Numéro de départ de la numérotation des pages
pageNumberStamp.StartingNumber = 1;

// Définir les propriétés du texte du tampon de numéro de page
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Le code ci-dessus crée un tampon de numéro de page avec des propriétés telles que le format du numéro de page, la marge inférieure, l'alignement horizontal, le numéro de départ et les propriétés du texte.

## Étape 4 : Ajout du tampon de numéro de page à une page spécifique

Une fois le tampon de numéro de page configuré, nous pouvons l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter le tampon de numéro de page à une page spécifique
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Le code ci-dessus ajoute le tampon du numéro de page à la première page du document PDF. Vous pouvez modifier le numéro de page si nécessaire.

## Étape 5 : Enregistrer le document PDF modifié

Une fois le tampon de numéro de page ajouté au document PDF, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF modifié.

### Exemple de code source pour les tampons de numéro de page utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Créer un tampon de numéro de page
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Si le tampon est en arrière-plan
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Définir les propriétés du texte
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Félicitation ! Vous avez appris à ajouter des tampons de numéro de page à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant personnaliser vos documents PDF en ajoutant des numéros de page clairs et informatifs.
