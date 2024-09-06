---
title: Tampons de numérotation de page dans le fichier PDF
linktitle: Tampons de numérotation de page dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des numéros de page dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Dans ce tutoriel, nous vous expliquerons étape par étape comment ajouter des numéros de page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour ouvrir un document PDF existant, créer un numéro de page, définir ses propriétés et l'ajouter à une page spécifique du fichier PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF existant

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment procéder :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF existant
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel vers le répertoire où se trouve votre document PDF.

## Étape 3 : Création et configuration du tampon de numérotation des pages

Maintenant que le document PDF est chargé, nous pouvons créer un tampon de numérotation de pages et le configurer selon nos besoins. Voici comment procéder :

```csharp
// Créer un tampon de numéros de page
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

Le code ci-dessus crée un tampon de numéro de page avec des propriétés telles que le format du numéro de page, la marge inférieure, l'alignement horizontal, le numéro de départ et les propriétés de texte.

## Étape 4 : Ajout du tampon de numéro de page à une page spécifique

Une fois le tampon de numérotation de page configuré, nous pouvons l'ajouter à une page spécifique du document PDF. Voici comment procéder :

```csharp
// Ajouter le tampon de numéro de page à une page spécifique
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Le code ci-dessus ajoute le numéro de page à la première page du document PDF. Vous pouvez modifier le numéro de page selon vos besoins.

## Étape 5 : enregistrement du document PDF modifié

Une fois le tampon de numéro de page ajouté au document PDF, nous pouvons enregistrer le document PDF modifié. Voici comment procéder :

```csharp
// Enregistrer le document PDF modifié
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel vers le répertoire dans lequel vous souhaitez enregistrer le document PDF modifié.

### Exemple de code source pour les tampons de numérotation de page à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Créer un tampon de numéro de page
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Que le timbre soit en arrière-plan
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

Félicitations ! Vous avez appris à ajouter des numéros de page à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos documents PDF en ajoutant des numéros de page clairs et informatifs.

### FAQ sur les tampons de numérotation de page dans les fichiers PDF

#### Q : Qu'est-ce qu'un tampon de numéro de page et comment est-il utilisé pour ajouter des numéros de page à un fichier PDF ?

R : Un tampon de numéro de page est une fonctionnalité d'Aspose.PDF qui vous permet d'ajouter des numéros de page dynamiques à des pages spécifiques d'un document PDF. Dans ce didacticiel, cela s'effectue en créant un objet PageNumberStamp, en configurant ses propriétés et en l'ajoutant à une page désignée.

#### Q : Comment le code source C# fourni permet-il d’ajouter des numéros de page à un fichier PDF ?

R : Le code montre comment charger un document PDF existant, créer un PageNumberStamp, définir diverses propriétés (telles que le format, la police, l'alignement, etc.), puis ajouter le tampon à une page spécifique. Le tampon calcule automatiquement le nombre total de pages et insère les numéros de page corrects.

#### Q : Puis-je personnaliser l’apparence du numéro de page, comme le style de police, la couleur et la taille ?

R : Absolument, vous pouvez personnaliser l'apparence du tampon de numéro de page en ajustant les propriétés telles que la police, la taille de la police, le style de police (gras, italique, etc.) et la couleur du texte.

#### Q : Est-il possible d’ajouter des numéros de page à plusieurs pages d’un document PDF ?

R : Oui, vous pouvez ajouter des tampons de numérotation de page à plusieurs pages en créant plusieurs objets PageNumberStamp et en ajoutant chacun d'eux aux pages souhaitées.

#### Q : Puis-je choisir si le tampon de numéro de page apparaît comme partie du contenu de la page ou comme élément d'arrière-plan ?

 R : Oui, vous pouvez contrôler si le tampon du numéro de page apparaît comme partie du contenu de la page ou comme élément d'arrière-plan en définissant le`Background` propriété du PageNumberStamp.

#### Q : Comment puis-je spécifier le format du numéro de page, y compris le nombre total de pages ?

 A : Le code utilise le`Format`Propriété de PageNumberStamp pour spécifier le format du numéro de page. La macro "# of" est utilisée pour représenter le nombre total de pages.

#### Q : Que se passe-t-il si j’ajoute le même tampon de numéro de page à plusieurs pages ?

R : L'ajout de la même instance PageNumberStamp à plusieurs pages affichera les numéros de page corrects pour chaque page. Le tampon ajuste automatiquement le numéro de page et le nombre total de pages.

#### Q : Puis-je ajouter des numéros de page aux sections d’en-tête ou de pied de page d’un document PDF ?

R : Bien que les PageNumberStamps soient généralement ajoutés directement au contenu de la page, vous pouvez utiliser FloatingBox ou d'autres techniques pour les positionner dans les sections d'en-tête ou de pied de page.

#### Q : Comment puis-je spécifier la position du tampon du numéro de page sur la page ?

 A : Le`BottomMargin` et`HorizontalAlignment` Les propriétés du PageNumberStamp vous permettent de contrôler la position du tampon dans la page.

#### Q : Que faire si je souhaite commencer la numérotation des pages à partir d’un numéro différent de 1 ?

 A : Vous pouvez définir le`StartingNumber`propriété du PageNumberStamp pour spécifier le numéro de page de départ.