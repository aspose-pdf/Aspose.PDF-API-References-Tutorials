---
title: Extraire la bordure dans un fichier PDF
linktitle: Extraire la bordure dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire les bordures d'un fichier PDF et les enregistrer sous forme d'image à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec des exemples de code et des conseils pour réussir.
type: docs
weight: 80
url: /fr/net/programming-with-tables/extract-border/
---
## Introduction

Lorsque vous travaillez avec des fichiers PDF, l'extraction d'éléments spécifiques tels que des bordures ou des chemins graphiques peut sembler une tâche ardue. Mais avec Aspose.PDF pour .NET, vous pouvez facilement extraire des bordures ou des formes d'un fichier PDF et les enregistrer sous forme d'image. Dans ce didacticiel, nous allons nous plonger dans le processus d'extraction d'une bordure d'un fichier PDF et de son enregistrement sous forme d'image PNG. Préparez-vous à prendre le contrôle du contenu graphique de votre PDF !

## Prérequis

Avant de plonger dans le code, assurez-vous que tout est configuré :

1.  Aspose.PDF pour .NET : si vous n'avez pas encore installé la bibliothèque Aspose.PDF, vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/)Vous devrez également appliquer la licence, soit via l'essai gratuit, soit via une licence achetée.
2. Configuration de l'IDE : configurez un projet C# dans Visual Studio ou tout autre IDE .NET. Assurez-vous d'avoir ajouté les références nécessaires à la bibliothèque Aspose.PDF.
3. Fichier PDF d'entrée : préparez un fichier PDF à partir duquel vous extrairez les bordures. Ce didacticiel fera référence à un fichier nommé`input.pdf`.

## Importation des packages requis

Commençons par importer les espaces de noms requis. Ces packages fournissent les outils nécessaires pour manipuler le contenu PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Maintenant que nous avons couvert les bases, passons au guide étape par étape où nous décomposerons chaque partie du code pour l'expliquer en détail.


## Étape 1 : Chargement du document PDF

La première étape consiste à charger le document PDF contenant la bordure que vous souhaitez extraire. C'est comme ouvrir un livre avant de commencer à le lire : vous devez accéder au contenu !

 Nous commencerons par spécifier le répertoire dans lequel votre fichier PDF est stocké et chargerons le document à l'aide de la`Aspose.Pdf.Document` classe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Ce code charge le`input.pdf` fichier de votre répertoire spécifié. Assurez-vous que le chemin du fichier est correct, sinon vous risquez d'obtenir une erreur de fichier introuvable.

## Étape 2 : Configuration des graphiques et des images bitmap

Avant de commencer l'extraction, nous devons créer une toile sur laquelle dessiner. Dans le monde de .NET, cela signifie configurer des objets Bitmap et Graphics. Le Bitmap représente l'image et l'objet Graphics nous permettra de dessiner des formes, telles que des bordures, extraites du PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Voici un aperçu :
- Nous créons une image bitmap de la taille de la première page du PDF.
- GraphicsPath est utilisé pour définir des formes (dans ce cas, des bordures).
- La matrice définit la manière dont les graphiques seront transformés ; nous avons besoin d'une matrice d'inversion car PDF et .NET ont des systèmes de coordonnées différents.

## Étape 3 : Traitement du contenu du PDF


Le fichier PDF est une série de commandes de dessin, et nous devons traiter chacune de ces commandes pour identifier et extraire les informations de bordure.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Traitement des commandes telles que la sauvegarde/restauration de l'état, le dessin de lignes, le remplissage de formes, etc.
}
```

Le code parcourt chaque opérateur de dessin dans le flux de contenu du PDF. Chaque opérateur peut représenter une ligne, un rectangle ou une autre instruction graphique.

## Étape 4 : Gestion des opérateurs PDF

Chaque opérateur du fichier PDF contrôle une action. Pour extraire la bordure, nous devons identifier des commandes telles que « déplacer vers », « ligne vers » et « dessiner un rectangle ». Les opérateurs suivants gèrent ces actions :

- MoveTo : déplace le curseur vers un point de départ.
- LineTo : dessine une ligne du point actuel vers un nouveau point.
- Re : Dessine un rectangle (cela pourrait faire partie de la bordure).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Dans cette étape :
- Nous capturons les points pour chaque ligne ou forme dessinée.
- Pour les rectangles (`opRe` ), nous les ajoutons directement à la`graphicsPath`, que nous utiliserons plus tard pour dessiner la bordure.

## Étape 5 : Dessiner la bordure

Une fois que nous avons identifié les lignes et les rectangles qui forment la bordure, nous devons les dessiner sur l'objet Bitmap. C'est là qu'intervient l'objet Graphics.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Nous créons un objet graphique basé sur le bitmap.
- SmoothingMode.HighQuality garantit que nous obtenons une image agréable et lisse.
- Enfin, nous utilisons DrawPath pour dessiner la bordure.

## Étape 6 : Sauvegarde de la bordure extraite

Maintenant que nous avons extrait la bordure, il est temps de l'enregistrer en tant que fichier image. Cela enregistrera la bordure au format PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- L'image bitmap est enregistrée sous forme d'image PNG.
- Vous pouvez maintenant ouvrir cette image pour visualiser la bordure extraite.

## Conclusion

L'extraction des bordures d'un fichier PDF à l'aide d'Aspose.PDF pour .NET peut sembler compliquée au début, mais une fois que vous l'aurez décomposée, cela deviendra simple. En comprenant les opérateurs de dessin dans un PDF et en utilisant les puissantes bibliothèques .NET, vous pouvez manipuler et extraire efficacement le contenu graphique. Ce guide vous donne une base solide pour commencer à manipuler des PDF !

## FAQ

### Comment gérer plusieurs pages dans le PDF ?  
 Vous pouvez parcourir chaque page du document en effectuant une itération sur`doc.Pages` au lieu de coder en dur`doc.Pages[1]`.

### Puis-je extraire d’autres éléments, comme du texte, en utilisant la même approche ?  
Oui, Aspose.PDF fournit des API riches pour extraire du texte, des images et d'autres contenus des fichiers PDF.

### Comment puis-je appliquer une licence pour éviter les limitations ?  
 Tu peux[appliquer une licence](https://purchase.aspose.com/temporary-license/) en le chargeant via le`License` classe fournie par Aspose.

### Que faire si mon PDF n’a pas de bordures ?  
Si votre PDF ne contient aucune bordure visible, le processus d'extraction des graphiques risque de ne donner aucun résultat. Assurez-vous que le contenu PDF comprend des bordures dessinables.

### Puis-je enregistrer la sortie dans des formats autres que PNG ?  
 Oui, changez simplement le`ImageFormat.Png` vers un autre format pris en charge tel que`ImageFormat.Jpeg`.