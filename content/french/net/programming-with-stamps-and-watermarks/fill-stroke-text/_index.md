---
title: Remplir le texte du trait dans un fichier PDF
linktitle: Remplir le texte du trait dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Apprenez à remplir et à décrire facilement du texte dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment remplir et décrire le texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous allons vous montrer comment utiliser le code source C# fourni pour appliquer des couleurs de remplissage et de contour au texte du fichier PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création de l'objet TextState

La première étape consiste à créer un objet TextState pour transmettre les propriétés avancées. Voici comment:

```csharp
// Créer un objet TextState pour transférer les propriétés avancées
TextState ts = new TextState();

// Définir la couleur du contour
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Le code ci-dessus crée un nouvel objet TextState et définit la couleur du contour ainsi que la façon dont le texte est rendu.

## Étape 3 : Chargement du document PDF

Maintenant que l'objet TextState est prêt, nous pouvons charger le document PDF où nous souhaitons appliquer le remplissage et le contour du texte. Voici comment:

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

// Lier l'objet TextState
stamp.BindTextState(ts);

// Définir l'origine X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Ajouter le cachet au document
fileStamp.AddStamp(stamp);
```

Le code ci-dessus crée un tampon avec le texte spécifié et les propriétés de remplissage et de contour définies.

## Étape 5 : Enregistrez le document de sortie

Une fois le tampon de texte ajouté, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document modifié
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Fill Stroke Text à l’aide d’Aspose.PDF pour .NET 
```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un objet TextState pour transférer les propriétés avancées
TextState ts = new TextState();

// Définir la couleur du trait
ts.StrokingColor = Color.Gray;

// Définir le mode de rendu du texte
ts.RenderingMode = TextRenderingMode.StrokeText;

// Charger un document PDF d'entrée
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Lier l'état de texte
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

Félicitation ! Vous avez appris à remplir et à décrire le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances pour personnaliser les couleurs de remplissage et de contour de vos documents PDF.

### FAQ pour remplir le texte du trait dans un fichier PDF

#### Q : Que signifie remplir et mettre en surbrillance du texte dans un document PDF, et quand dois-je le faire ?

R : Le remplissage et le contour du texte dans un document PDF impliquent l'application de couleurs à l'intérieur des caractères du texte (remplissage) et aux bordures autour du texte (contour). Cela peut être utilisé pour améliorer l’apparence visuelle du texte, mettre l’accent ou mettre en évidence un contenu spécifique dans le PDF.

#### Q : Comment le code source C# fourni permet-il de remplir et de décrire le texte dans un fichier PDF ?

 R : Le code source fourni montre comment créer un`TextState` objet pour définir des propriétés de texte avancées, telles que la couleur du contour et le mode de rendu. Il utilise ensuite Aspose.PDF.Facades pour charger un document PDF existant, créer un tampon contenant le texte avec les propriétés de remplissage et de contour spécifiées et ajouter le tampon au document.

####  Q : Quel est le but du`TextState` object in the code?

 R : Le`TextState`L'objet est utilisé pour définir les propriétés avancées du texte, notamment la couleur du contour du texte (trait) et le mode de rendu. Il vous permet de personnaliser l'apparence du texte en termes de contour et de remplissage.

#### Q : Puis-je appliquer différentes couleurs de remplissage et de contour à différentes parties du même texte ?

 R : Oui, vous pouvez modifier le code pour créer différents`TextState` objets avec des couleurs de remplissage et de contour distinctes et appliquez-les à des parties spécifiques du texte en utilisant des`Stamp` objets.

#### Q : Puis-je appliquer des couleurs de remplissage et de contour au texte déjà présent dans le document PDF ?

 R : Oui, vous pouvez utiliser des principes similaires pour appliquer des couleurs de remplissage et de contour au texte existant dans le document PDF en sélectionnant les objets texte appropriés et en les ajoutant sous forme de tampons avec le texte souhaité.`TextState` propriétés.

#### Q : Comment puis-je ajuster l'opacité et la fusion du texte rempli et souligné ?

 R : Le code fourni vous permet de définir les propriétés d'opacité et de fusion du tampon à l'aide du`Opacity` et`BlendingSpace`propriétés, respectivement. Vous pouvez ajuster ces valeurs pour obtenir l'effet visuel souhaité.

#### Q : Comment puis-je appliquer différentes couleurs de remplissage et de contour à plusieurs tampons dans le même document PDF ?

 R : Vous pouvez créer plusieurs`TextState` objets avec des couleurs de remplissage et de contour différentes, puis créez des`Stamp` objets pour chaque ensemble de texte avec des couleurs distinctes. Ajoutez ces tampons au même document PDF à l'aide du`PdfFileStamp` classe.

#### Q : Puis-je utiliser des polices autres qu'Arial pour le texte souligné et rempli ?

 R : Oui, vous pouvez changer la police en modifiant le paramètre de nom de police dans le`FormattedText` constructeur lors de la création du tampon. Vous pouvez utiliser n'importe quelle police disponible sur votre système.

#### Q : Comment puis-je modifier l'angle de rotation du texte entouré et rempli ?

 R : Le code fourni vous permet de définir l'angle de rotation du tampon à l'aide du`Rotation` propriété. Vous pouvez ajuster cette propriété pour spécifier l'angle de rotation souhaité pour le texte.

#### Q : Comment puis-je contrôler la position et la taille du texte souligné et rempli sur la page ?

R : Vous pouvez utiliser le`SetOrigin` méthode du`Stamp` objet pour définir les coordonnées X et Y de la position du tampon sur la page. De plus, vous pouvez ajuster la taille de la police dans le`FormattedText` constructeur pour contrôler la taille du texte.