---
title: Ajout de différents en-têtes
linktitle: Ajout de différents en-têtes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter facilement différents en-têtes à chaque page de vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter différents en-têtes à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour ajouter des en-têtes personnalisés à chaque page du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Création de tampons d'en-tête

Maintenant que vous avez téléchargé le document PDF, vous pouvez créer les tampons d'en-tête à ajouter. Voici comment:

```csharp
// Créer trois tampons d'en-tête
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Le code ci-dessus crée trois nouveaux tampons d'en-tête contenant le texte spécifié.

## Étape 4 : Configuration des propriétés du tampon d'en-tête

Avant d'ajouter les tampons d'en-tête au document PDF, vous pouvez configurer différentes propriétés pour chaque tampon, telles que l'alignement, la taille, la couleur, etc. Voici comment :

```csharp
// Configurer le premier tampon d'en-tête
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Configuration du deuxième tampon d'en-tête
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Configurer le troisième tampon d'en-tête
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Vous pouvez ajuster ces propriétés selon vos besoins pour chaque tampon d'en-tête.

## Étape 5 : Ajouter des tampons d'en-tête au PDF

Maintenant que les tampons d'en-tête sont prêts, vous pouvez les ajouter à chaque page spécifique du document PDF. Voici comment:

```csharp
// Ajouter des tampons d'en-tête à des pages spécifiques
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Le code ci-dessus ajoute chaque tampon d'en-tête à la page correspondante du document PDF.

## Étape 6 : Enregistrer le document de sortie

Une fois que vous avez ajouté les tampons d'en-tête, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document mis à jour
doc.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'ajout de différents en-têtes à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document open source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Créer trois tampons
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Définir l'alignement du tampon (placer le tampon en haut de la page, centré horizontalement)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Spécifiez le style de police en gras
stamp1.TextState.FontStyle = FontStyles.Bold;

// Définissez le texte avant les informations de couleur de fond sur rouge
stamp1.TextState.ForegroundColor = Color.Red;

// Spécifiez la taille de la police comme 14
stamp1.TextState.FontSize = 14;

// Maintenant, nous devons définir l'alignement vertical du 2ème objet de tampon sur Haut
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Définissez les informations d'alignement horizontal pour le tampon sur Aligné au centre
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Définir le facteur de zoom pour l'objet tampon
stamp2.Zoom = 10;

// Définir la mise en forme du 3ème objet tampon
// Spécifiez les informations d'alignement vertical pour l'objet de tampon comme TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Définissez les informations d'alignement horizontal pour l'objet de tampon sur Aligné au centre
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Définir l'angle de rotation de l'objet tampon
stamp3.RotateAngle = 35;

// Définir le rose comme couleur d'arrière-plan pour le tampon
stamp3.TextState.BackgroundColor = Color.Pink;

// Changer les informations de police pour le tampon en Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Le premier tampon est ajouté sur la première page ;
doc.Pages[1].AddStamp(stamp1);

// Le deuxième tampon est ajouté sur la deuxième page ;
doc.Pages[2].AddStamp(stamp2);

// Le troisième tampon est ajouté sur la troisième page.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Félicitation ! Vous avez appris à ajouter différents en-têtes à chaque page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour personnaliser les en-têtes de vos documents PDF.
