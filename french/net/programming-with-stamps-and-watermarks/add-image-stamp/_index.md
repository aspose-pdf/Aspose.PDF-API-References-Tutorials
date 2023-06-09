---
title: Ajouter un tampon d'image
linktitle: Ajouter un tampon d'image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter facilement un tampon d'image à vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter un tampon d'image à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour ajouter un tampon d'image personnalisé à une page spécifique du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : création du framebuffer

Maintenant que vous avez téléchargé le document PDF, vous pouvez créer le tampon d'image à ajouter. Voici comment procéder :

```csharp
// Créer le tampon de trame
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

Le code ci-dessus crée un nouveau tampon d'image en utilisant le fichier "aspose-logo.jpg". Assurez-vous que le chemin du fichier image est correct.

## Étape 4 : Configuration des propriétés du tampon d'image

Avant d'ajouter le tampon d'image au document PDF, vous pouvez configurer diverses propriétés du tampon, telles que l'opacité, la taille, la position, etc. Voici comment :

```csharp
// Configurer les propriétés du tampon d'image
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

Vous pouvez ajuster ces propriétés en fonction de vos besoins.

## Étape 5 : Ajouter le tampon d'image au PDF

Maintenant que le tampon d'image est prêt, vous pouvez l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter le tampon de cadre à la page spécifique
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Le code ci-dessus ajoute le tampon d'image à la première page du document PDF. Vous pouvez spécifier une autre page si nécessaire.

## Étape 6 : Enregistrer le document de sortie

Une fois que vous avez ajouté le tampon d'image, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Ajouter un tampon d'image à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Créer un tampon d'image
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez appris à ajouter un tampon d'image à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour ajouter des tampons d'image personnalisés aux documents PDF.
