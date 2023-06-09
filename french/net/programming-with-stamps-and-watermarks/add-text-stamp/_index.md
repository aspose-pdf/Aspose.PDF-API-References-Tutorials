---
title: Ajouter un tampon de texte
linktitle: Ajouter un tampon de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter facilement un tampon de texte à vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter un tampon de texte à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour ajouter un tampon de texte personnalisé à une page spécifique du document PDF.

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
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Création du tampon de texte

Maintenant que vous avez téléchargé le document PDF, vous pouvez créer le tampon de texte à ajouter. Voici comment procéder :

```csharp
// Créer le tampon de texte
TextStamp textStamp = new TextStamp("Example Stamp");
```

Le code ci-dessus crée un nouveau tampon de texte contenant le texte spécifié.

## Étape 4 : Configurer les propriétés du tampon de texte

Avant d'ajouter le tampon de texte au document PDF, vous pouvez configurer diverses propriétés du tampon, telles que l'arrière-plan, la position, la rotation, la police, la taille, etc. Voici comment :

```csharp
// Configurer les propriétés du tampon de texte
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Vous pouvez ajuster ces propriétés en fonction de vos besoins.

## Étape 5 : Ajouter un tampon de texte au PDF

Maintenant que le tampon de texte est prêt, vous pouvez l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter un tampon de texte à une page spécifique
pdfDocument.Pages[1].AddStamp(textStamp);
```

Le code ci-dessus ajoute le tampon de texte à la première page du document PDF. Vous pouvez spécifier une autre page si nécessaire.

## Étape 6 : Enregistrer le document de sortie

Une fois que vous avez ajouté le tampon de texte, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour ajouter un tampon de texte à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Créer un tampon de texte
TextStamp textStamp = new TextStamp("Sample Stamp");

// Définir si le tampon est en arrière-plan
textStamp.Background = true;

// Définir l'origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Faire pivoter le timbre
textStamp.Rotate = Rotation.on90;

// Définir les propriétés du texte
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusion

Félicitation ! Vous avez appris à ajouter un tampon de texte à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour ajouter des tampons de texte personnalisés aux documents PDF.
