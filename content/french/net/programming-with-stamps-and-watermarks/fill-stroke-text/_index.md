---
title: Remplir le texte du contour dans un fichier PDF
linktitle: Remplir le texte du contour dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplir sans effort du texte en trait dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape rempli d'exemples pratiques.
type: docs
weight: 90
url: /fr/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Introduction

Avez-vous déjà souhaité modifier un fichier PDF pour le rendre plus attrayant ? Peut-être avez-vous besoin d'ajouter un filigrane frappant ou un tampon en gras qui rend un document important incontestablement le vôtre. Avec Aspose.PDF pour .NET, vous pouvez facilement remplir le texte en trait continu dans un fichier PDF, en ajoutant une touche artistique qui attire l'attention. Dans le didacticiel d'aujourd'hui, nous allons vous expliquer comment faire exactement cela : remplir le texte en trait continu dans un PDF à l'aide de C#. À la fin, vous aurez une solide compréhension de la façon de manipuler les fichiers PDF comme un pro.

## Prérequis

Avant de nous plonger dans le codage, vous devez mettre en place quelques éléments pour que ce tutoriel soit un jeu d'enfant :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur, car nous allons écrire du code C#.
2.  Bibliothèque Aspose.PDF : Assurez-vous d'avoir téléchargé la bibliothèque Aspose.PDF pour .NET. Vous pouvez la récupérer[ici](https://releases.aspose.com/pdf/net/).
3. Connaissances de base de C# : une familiarité avec la programmation C# vous aidera à comprendre le didacticiel plus facilement.
4. Exemple de fichier PDF : vous aurez besoin d'un exemple de fichier PDF (`input.pdf`à des fins de test. Vous pouvez en créer un simple ou utiliser n'importe quel PDF existant.

Maintenant que tout est en place, passons aux choses sérieuses du remplissage du texte en trait dans votre fichier PDF.

## Paquets d'importation

Pour commencer, nous devons importer les packages nécessaires. Voici un bref aperçu des importations essentielles pour notre projet :

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ces packages nous permettront d'utiliser les fonctionnalités robustes de la bibliothèque Aspose.PDF.

Décomposons la tâche principale en étapes claires. En suivant ces étapes, vous pouvez facilement remplir du texte en trait continu dans vos fichiers PDF. 

## Étape 1 : Configurez votre environnement

Tout d'abord, assurez-vous que tout est correctement configuré dans votre projet Visual Studio. Créez un nouveau projet ou choisissez-en un existant. Si vous avez besoin d'aide, voici comment procéder :

1. Ouvrez Visual Studio.
2. Créez un nouveau projet C# (par exemple, une application console).
3. Cliquez avec le bouton droit sur le projet dans l’Explorateur de solutions, sélectionnez « Gérer les packages NuGet ».
4.  Rechercher`Aspose.PDF` et installez-le.

## Étape 2 : définissez votre répertoire de documents

Chaque voyage a besoin d'un point de départ, et dans notre cas, il s'agit du répertoire de documents où résideront les fichiers d'entrée et de sortie. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve votre fichier PDF d'entrée. 

## Étape 3 : Créer l'objet TextState

Cette étape est celle où vous commencez à définir les propriétés du texte que vous souhaitez ajouter. 

```csharp
TextState ts = new TextState();
```

 Le`TextState` L'objet contiendra les options de style pour votre texte de trait.

## Étape 4 : définir la couleur du contour

Ensuite, vous souhaiterez définir la couleur du trait de votre texte. 

```csharp
ts.StrokingColor = Color.Gray;
```

Dans ce code, nous utilisons une couleur grise pour le contour. N'hésitez pas à modifier la couleur en fonction de vos besoins !

## Étape 5 : Configurer le mode de rendu

Pour garantir que votre texte s'affiche comme prévu, définissez le mode de rendu :

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Cela indique à la bibliothèque Aspose que nous travaillons avec du texte en trait.

## Étape 6 : Chargez votre document PDF d'entrée

Il est maintenant temps de charger le fichier PDF que vous allez modifier. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Assurez-vous que votre PDF d'entrée (`input.pdf`se trouve dans le répertoire des documents défini dans les étapes précédentes.

## Étape 7 : Créer un objet tampon

Ensuite, créez un tampon qui contiendra votre texte de trait. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Ce tampon sera utilisé pour superposer votre texte sur le PDF.

## Étape 8 : Définir le texte à tamponner

Vous devrez spécifier le texte que vous souhaitez ajouter au PDF :

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Ici, « PAIÉ EN TOTALITÉ » est le texte que nous ajoutons, ainsi que ses attributs de style. Personnalisez-le selon vos besoins !

## Étape 9 : Lier l'état du texte

 Maintenant, liez le`TextState` vous avez défini précédemment au tampon. 

```csharp
stamp.BindTextState(ts);
```

Cette étape applique tous les styles tels que la couleur et le mode de rendu à votre texte.

## Étape 10 : Définir la position du tampon

Déterminez où votre tampon apparaîtra dans le PDF :

```csharp
stamp.SetOrigin(100, 100);
```

 Les arguments`(100, 100)` désigne les coordonnées X et Y (en points) de l'origine du texte. Ajustez ces valeurs pour positionner parfaitement votre texte !

## Étape 11 : Configurer l’opacité et la rotation

C'est ici que vous pouvez jouer avec l'apparence de votre texte :

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

Dans ce cas, une valeur d'opacité et un angle de rotation de 45 degrés ajoutent une touche unique à votre texte. N'hésitez pas à modifier ces paramètres pour obtenir différents effets.

## Étape 12 : ajouter le tampon au PDF

C'est l'étape cruciale où nous ajoutons enfin notre tampon qui inclut le texte du trait au PDF :

```csharp
fileStamp.AddStamp(stamp);
```

Et comme ça, votre texte est prêt à faire une déclaration !

## Étape 13 : Enregistrer et fermer le document

Enfin, enregistrez vos modifications et assurez-vous que tout est correctement nettoyé. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 Votre fichier PDF nouvellement modifié contenant le texte du trait sera enregistré sous`output_out.pdf` dans votre répertoire de documents. 

## Conclusion

Et voilà ! En suivant ces étapes simples, vous pouvez facilement remplir le texte en trait continu d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Que ce soit pour des documents professionnels ou des projets personnels, cette technique vous permet d'ajouter une touche unique à vos PDF, les faisant ressortir dans n'importe quelle pile de papiers.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et convertir des fichiers PDF par programmation.

### Puis-je utiliser Aspose.PDF gratuitement ?
Oui, Aspose propose un essai gratuit. Vous pouvez l'obtenir[ici](https://releases.aspose.com/).

### Dois-je payer pour une licence ?
 Bien que la bibliothèque propose un essai gratuit, une licence temporaire peut également être achetée sur[ce lien](https://purchase.aspose.com/temporary-license/).

### Où puis-je trouver la documentation ?
 Vous pouvez accéder à la documentation complète[ici](https://reference.aspose.com/pdf/net/).

### Existe-t-il une assistance disponible si je rencontre des problèmes ?
 Absolument ! Vous pouvez obtenir de l'aide sur le forum Aspose[ici](https://forum.aspose.com/c/pdf/10).