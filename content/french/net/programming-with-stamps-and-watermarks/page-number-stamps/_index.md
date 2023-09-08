---
title: Timbres de numéro de page dans un fichier PDF
linktitle: Timbres de numéro de page dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter des tampons de numéro de page dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Dans ce didacticiel, nous vous guiderons étape par étape sur la façon d'ajouter des tampons de numéro de page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour ouvrir un document PDF existant, créer un tampon de numéro de page, définir ses propriétés et l'ajouter à une page spécifique du fichier PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF existant

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF existant
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Création et configuration du tampon de numérotation des pages

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

// Numéro de début de la numérotation des pages
pageNumberStamp.StartingNumber = 1;

// Définir les propriétés du texte du tampon de numéro de page
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Le code ci-dessus crée un tampon de numéro de page avec des propriétés telles que le format du numéro de page, la marge inférieure, l'alignement horizontal, le numéro de départ et les propriétés du texte.

## Étape 4 : Ajout du cachet du numéro de page à une page spécifique

Une fois le tampon du numéro de page configuré, nous pouvons l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter le tampon de numéro de page à une page spécifique
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Le code ci-dessus ajoute le cachet du numéro de page à la première page du document PDF. Vous pouvez modifier le numéro de page selon vos besoins.

## Étape 5 : Sauvegarde du document PDF modifié

Une fois le tampon du numéro de page ajouté au document PDF, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document PDF modifié.

### Exemple de code source pour les tampons de numéro de page utilisant Aspose.PDF pour .NET 
```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Créer un tampon de numéro de page
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Si le timbre est en arrière-plan
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

Félicitation ! Vous avez appris à ajouter des tampons de numéro de page à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos documents PDF en ajoutant des numéros de page clairs et informatifs.

### FAQ sur les tampons de numéro de page dans un fichier PDF

#### Q : Qu'est-ce qu'un tampon de numéro de page et comment est-il utilisé pour ajouter des numéros de page à un fichier PDF ?

R : Un tampon de numéro de page est une fonctionnalité d'Aspose.PDF qui vous permet d'ajouter des numéros de page dynamiques à des pages spécifiques d'un document PDF. Dans ce didacticiel, cela est réalisé en créant un objet PageNumberStamp, en configurant ses propriétés et en l'ajoutant à une page désignée.

#### Q : Comment le code source C# fourni permet-il d'ajouter des tampons de numéro de page à un fichier PDF ?

R : Le code montre comment charger un document PDF existant, créer un PageNumberStamp, définir diverses propriétés (telles que le format, la police, l'alignement, etc.), puis ajouter le tampon à une page spécifique. Le tampon calcule automatiquement le nombre total de pages et insère les numéros de page corrects.

#### Q : Puis-je personnaliser l’apparence du numéro de page, comme le style, la couleur et la taille de la police ?

R : Absolument, vous pouvez personnaliser l'apparence du cachet du numéro de page en ajustant les propriétés telles que la police, la taille de la police, le style de police (gras, italique, etc.) et la couleur du texte.

#### Q : Est-il possible d'ajouter des tampons de numéro de page à plusieurs pages d'un document PDF ?

R : Oui, vous pouvez ajouter des tampons de numéro de page à plusieurs pages en créant plusieurs objets PageNumberStamp et en ajoutant chacun aux pages souhaitées.

#### Q : Puis-je choisir si le cachet du numéro de page apparaît dans le contenu de la page ou comme élément d'arrière-plan ?

 R : Oui, vous pouvez contrôler si le cachet du numéro de page apparaît dans le cadre du contenu de la page ou comme élément d'arrière-plan en définissant l'option`Background` propriété du PageNumberStamp.

#### Q : Comment puis-je spécifier le format du numéro de page, y compris le nombre total de pages ?

 R : Le code utilise le`Format`propriété de PageNumberStamp pour spécifier le format du numéro de page. La macro « # de » est utilisée pour représenter le nombre total de pages.

#### Q : Que se passe-t-il si j'ajoute le même tampon de numéro de page sur plusieurs pages ?

R : L'ajout de la même instance de PageNumberStamp à plusieurs pages affichera les numéros de page corrects pour chaque page. Le tampon ajuste automatiquement le numéro de page et le nombre total de pages.

#### Q : Puis-je ajouter des tampons de numéro de page aux sections d'en-tête ou de pied de page d'un document PDF ?

R : Bien que les PageNumberStamps soient généralement ajoutés directement au contenu de la page, vous pouvez utiliser FloatingBox ou d'autres techniques pour les positionner dans les sections d'en-tête ou de pied de page.

#### Q : Comment puis-je spécifier la position du cachet du numéro de page sur la page ?

 R : Le`BottomMargin` et`HorizontalAlignment` Les propriétés du PageNumberStamp vous permettent de contrôler la position du tampon dans la page.

#### Q : Que se passe-t-il si je souhaite commencer la numérotation des pages à partir d'un numéro différent plutôt que de 1 ?

 R : Vous pouvez définir le`StartingNumber`propriété de PageNumberStamp pour spécifier le numéro de page de début.