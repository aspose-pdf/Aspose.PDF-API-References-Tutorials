---
title: Remplir le texte du contour dans un fichier PDF
linktitle: Remplir le texte du contour dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment remplir et contourner facilement du texte dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment remplir et contourner du texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour appliquer des couleurs de remplissage et de contour au texte du fichier PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : création de l'objet TextState

La première étape consiste à créer un objet TextState pour transmettre les propriétés avancées. Voici comment procéder :

```csharp
// Créer un objet TextState pour transférer des propriétés avancées
TextState ts = new TextState();

// Définir la couleur du contour
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Le code ci-dessus crée un nouvel objet TextState et définit la couleur du contour ainsi que la manière dont le texte est rendu.

## Étape 3 : Chargement du document PDF

Maintenant que l'objet TextState est prêt, nous pouvons charger le document PDF dans lequel nous souhaitons appliquer le remplissage et le contour du texte. Voici comment procéder :

```csharp
// Charger le document PDF en tant qu'entrée
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Le code ci-dessus charge le document PDF existant à l'aide de la classe PdfFileStamp de la bibliothèque Aspose.PDF.Facades.

## Étape 4 : ajouter un remplissage et un contour au texte

Maintenant que le document PDF est chargé, nous pouvons ajouter le remplissage et le contour au texte. Voici comment procéder :

```csharp
// Créer un tampon (Stamp) avec le texte et les propriétés définis
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Lier l'objet TextState
stamp.BindTextState(ts);

// Définir l'origine X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Ajoutez le tampon au document
fileStamp.AddStamp(stamp);
```

Le code ci-dessus crée un tampon avec le texte spécifié et les propriétés de remplissage et de contour définies.

## Étape 5 : Enregistrer le document de sortie

Une fois le tampon de texte ajouté, nous pouvons enregistrer le document PDF modifié. Voici comment procéder :

```csharp
// Enregistrer le document modifié
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour le remplissage du texte avec contour à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un objet TextState pour transférer des propriétés avancées
TextState ts = new TextState();

// Définir la couleur du trait
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;

// Charger un document PDF d'entrée
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Lier TextState
stamp.BindTextState(ts);

// Définir l'origine X,Y
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

Félicitations ! Vous avez appris à remplir et à contourner du texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances pour personnaliser les couleurs de remplissage et de contour dans vos documents PDF.

### FAQ sur le texte de remplissage et de contour dans un fichier PDF

#### Q : Que signifie remplir et contourner du texte dans un document PDF, et quand puis-je avoir besoin de le faire ?

R : Le remplissage et le contour du texte dans un document PDF impliquent l'application de couleurs à l'intérieur des caractères du texte (remplissage) et aux bordures autour du texte (contour). Cela peut être utilisé pour améliorer l'apparence visuelle du texte, créer une emphase ou mettre en évidence un contenu spécifique dans le PDF.

#### Q : Comment le code source C# fourni permet-il de remplir et de décrire le texte dans un fichier PDF ?

 A : Le code source fourni montre comment créer un`TextState` objet pour définir des propriétés de texte avancées, telles que la couleur du contour et le mode de rendu. Il utilise ensuite Aspose.PDF.Facades pour charger un document PDF existant, créer un tampon contenant le texte avec les propriétés de remplissage et de contour spécifiées, et ajouter le tampon au document.

####  Q : Quel est le but de la`TextState` object in the code?

 A : Le`TextState`L'objet permet de définir des propriétés de texte avancées, notamment la couleur du contour du texte (trait) et le mode de rendu. Il permet de personnaliser l'apparence du texte en termes de trait et de remplissage.

#### Q : Puis-je appliquer différentes couleurs de remplissage et de contour à différentes parties du même texte ?

 R : Oui, vous pouvez modifier le code pour créer différents`TextState` objets avec des couleurs de remplissage et de contour distinctes et les appliquer à des parties spécifiques du texte à l'aide de couleurs distinctes`Stamp` objets.

#### Q : Puis-je appliquer des couleurs de remplissage et de contour à du texte déjà présent dans le document PDF ?

 R : Oui, vous pouvez utiliser des principes similaires pour appliquer des couleurs de remplissage et de contour au texte existant dans le document PDF en sélectionnant les objets texte appropriés et en les ajoutant sous forme de tampons avec les couleurs souhaitées.`TextState` propriétés.

#### Q : Comment puis-je régler l’opacité et le mélange du texte rempli et contourné ?

 R : Le code fourni vous permet de définir les propriétés d'opacité et de fusion du tampon à l'aide de l'`Opacity` et`BlendingSpace`propriétés, respectivement. Vous pouvez ajuster ces valeurs pour obtenir l'effet visuel souhaité.

#### Q : Comment puis-je appliquer différentes couleurs de remplissage et de contour à plusieurs tampons dans le même document PDF ?

 A : Vous pouvez créer plusieurs`TextState` objets avec différentes couleurs de remplissage et de contour, puis créez des objets séparés`Stamp` objets pour chaque ensemble de texte avec des couleurs distinctes. Ajoutez ces tampons au même document PDF à l'aide de`PdfFileStamp` classe.

#### Q : Puis-je utiliser d’autres polices qu’Arial pour le texte souligné et rempli ?

 R : Oui, vous pouvez changer la police en modifiant le paramètre de nom de police dans le`FormattedText` constructeur lors de la création du tampon. Vous pouvez utiliser n'importe quelle police disponible sur votre système.

#### Q : Comment puis-je modifier l’angle de rotation du texte encadré et rempli ?

 R : Le code fourni vous permet de définir l'angle de rotation du tampon à l'aide du`Rotation` propriété. Vous pouvez ajuster cette propriété pour spécifier l'angle de rotation souhaité pour le texte.

#### Q : Comment puis-je contrôler la position et la taille du texte souligné et rempli sur la page ?

 A : Vous pouvez utiliser le`SetOrigin` méthode de la`Stamp` objet pour définir les coordonnées X et Y de la position du tampon sur la page. De plus, vous pouvez ajuster la taille de la police dans le`FormattedText` constructeur pour contrôler la taille du texte.