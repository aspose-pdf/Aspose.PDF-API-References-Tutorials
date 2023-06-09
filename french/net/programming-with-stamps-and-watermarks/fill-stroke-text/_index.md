---
title: Remplir le texte du trait
linktitle: Remplir le texte du trait
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplir et à décrire facilement du texte dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment remplir et décrire du texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour appliquer des couleurs de remplissage et de contour au texte du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création de l'objet TextState

La première étape consiste à créer un objet TextState pour transmettre les propriétés avancées. Voici comment:

```csharp
// Créer un objet TextState pour transférer des propriétés avancées
TextState ts = new TextState();

// Définir la couleur du contour
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Le code ci-dessus crée un nouvel objet TextState et définit la couleur du contour ainsi que la façon dont le texte est rendu.

## Étape 3 : Chargement du document PDF

Maintenant que l'objet TextState est prêt, nous pouvons charger le document PDF où nous voulons appliquer le remplissage et le contour du texte. Voici comment:

```csharp
// Charger le document PDF en entrée
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Le code ci-dessus charge le document PDF existant à l'aide de la classe PdfFileStamp de la bibliothèque Aspose.PDF.Facades.

## Étape 4 : Ajouter un remplissage et un contour au texte

Maintenant que le document PDF est chargé, nous pouvons ajouter le remplissage et le contour au texte. Voici comment:

```csharp
// Créer un tampon (Stamp) avec le texte et les propriétés définis
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Liez l'objet TextState
stamp.BindTextState(ts);

// Définir l'origine X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Ajouter le tampon au document
fileStamp.AddStamp(stamp);
```

Le code ci-dessus crée un Stamp avec le texte spécifié et les propriétés Fill et Stroke définies.

## Étape 5 : Enregistrer le document de sortie

Une fois le tampon de texte ajouté, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document modifié
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Fill Stroke Text à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un objet TextState pour transférer des propriétés avancées
TextState ts = new TextState();

// Définir la couleur du trait
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;

//Charger un document PDF d'entrée
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Lier TextState
stamp.BindTextState(ts);

// Définir l'origine X, Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Ajouter un tampon
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusion

Félicitation ! Vous avez appris à remplir et à décrire du texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances pour personnaliser les couleurs de remplissage et de contour dans vos documents PDF.
