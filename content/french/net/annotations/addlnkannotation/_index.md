---
title: Ajouter une annotation de lien
linktitle: Ajouter une annotation de lien
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des annotations manuscrites aux fichiers PDF avec Aspose.PDF pour .NET dans ce guide engageant, étape par étape.
type: docs
weight: 20
url: /fr/net/annotations/addlnkannotation/
---
## Introduction

Bienvenue dans le monde de la manipulation PDF avec Aspose.PDF pour .NET ! Si vous cherchez à améliorer vos documents PDF, que ce soit pour un usage professionnel, des projets personnels ou autre, vous êtes au bon endroit. Aujourd'hui, nous allons nous pencher sur une fonctionnalité spécifique mais pratique d'Aspose.PDF : l'ajout d'une annotation manuscrite à vos fichiers PDF. Cette fonctionnalité peut s'avérer incroyablement utile lorsque vous souhaitez ajouter des notes ou des signatures de type manuscrit à vos documents, les rendant ainsi plus interactifs et attrayants.

## Prérequis

Avant de nous plonger dans la magie du codage, assurons-nous que vous disposez de tout ce dont vous avez besoin pour commencer :

1. .NET Framework : assurez-vous que .NET est installé sur votre ordinateur. Cette bibliothèque fonctionne parfaitement avec différentes versions de .NET, y compris .NET Core.
2.  Bibliothèque Aspose.PDF : vous devez avoir téléchargé et référencé la bibliothèque Aspose.PDF pour .NET dans votre projet. Si vous ne l'avez pas encore fait, vous pouvez récupérer la dernière version à partir du[lien de téléchargement](https://releases.aspose.com/pdf/net/).
3. Un éditeur de code : vous pouvez utiliser n’importe quel éditeur de code de votre choix, mais Visual Studio est fortement recommandé pour sa facilité d’utilisation avec les applications .NET.
4. Compréhension de base de C# : une connaissance pratique de C# vous aidera à parcourir les exemples de codage en douceur.
5. Configuration de votre environnement de développement : assurez-vous que votre IDE est configuré pour gérer les projets .NET et que vous avez correctement référencé la bibliothèque Aspose.PDF dans votre projet. 

Une fois ces conditions préalables remplies, vous êtes prêt à commencer à ajouter des annotations à l'encre à vos PDF !

## Paquets d'importation

Avant de passer au codage, importons les packages nécessaires. En haut de votre fichier C#, ajoutez les instructions using suivantes :

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

Cela vous donnera accès à toutes les classes et méthodes dont vous avez besoin pour travailler avec les annotations PDF.

Maintenant que nous avons préparé le terrain, il est temps de retrousser nos manches et d'entrer dans le vif du sujet ! Nous allons détailler chaque étape pour nous assurer que vous comprenez exactement comment créer et ajouter une annotation manuscrite à votre document PDF.

## Étape 1 : définir le document et le répertoire

La première chose que vous souhaitez faire est de configurer votre document et le chemin vers lequel vous souhaitez enregistrer votre fichier de sortie. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Nous définissons une variable`dataDir` , qui pointe vers le répertoire où le PDF résultant sera enregistré.`Document` L'objet est ensuite instancié, créant un nouveau document PDF à éditer.

## Étape 2 : ajouter une page à votre document

Ensuite, vous souhaiterez ajouter une page à votre document nouvellement créé.

```csharp
Page pdfPage = doc.Pages.Add();
```
Ici, nous ajoutons une nouvelle page à notre document. Chaque PDF nécessite au moins une page, cette étape est donc essentielle.

## Étape 3 : Définir le rectangle de dessin

Avant de pouvoir dessiner quoi que ce soit, vous devez définir où sur la page vous placerez votre annotation à l'encre.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Ici, nous créons un`Rectangle` objet qui spécifie la zone de la page où nous ajouterons notre annotation d'encre. Nous définissons ses dimensions pour qu'elles s'adaptent à la page entière, à partir de (0,0).

## Étape 4 : Préparez les points d'encre

Vient maintenant la partie amusante : définir les points qui composent votre annotation à l’encre. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Ce bloc de code crée une liste de tableaux de points, où chaque tableau représente un ensemble de points pour votre trait d'encre. Ici, nous définissons trois points formant un triangle ; vous pouvez ajuster les coordonnées pour les adapter à votre conception.

## Étape 5 : Créer l'annotation à l'encre

Une fois vos points définis, il est temps de créer l’annotation d’encre proprement dite.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Nous instancions le`InkAnnotation`objet, en passant la page, le rectangle et les points d'encre. De plus, nous définissons certaines propriétés comme`Title`, `Color` , et`CapStyle`Personnalisez-les selon vos besoins !

## Étape 6 : Définir la bordure et l’opacité

Vous souhaitez que votre annotation se démarque ? Donnons-lui du style.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Ici, nous ajoutons une bordure à l'annotation avec une largeur spécifique et définissons son opacité, la rendant semi-transparente.

## Étape 7 : ajouter l'annotation à la page

Maintenant que votre annotation est préparée, il est temps de l'ajouter à la page PDF.

```csharp
pdfPage.Annotations.Add(ia);
```
Cette ligne ajoute l'annotation d'encre que nous avons créée précédemment à la collection d'annotations de la page. 

## Étape 8 : Enregistrer le document

Enfin, sauvegardons notre document modifié.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Nous modifions notre`dataDir` pour inclure le nom du fichier de sortie et enregistrer le document. Un message de confirmation est imprimé sur la console pour vous informer que tout s'est bien passé.

## Conclusion

Et voilà ! Vous avez ajouté avec succès une annotation manuscrite à votre document PDF à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité simple mais efficace peut améliorer vos documents et les rendre interactifs. Que vous ajoutiez des signatures, des notes ou des gribouillages, les annotations manuscrites offrent un moyen unique d'enrichir le contenu.

## FAQ

### Qu'est-ce qu'Aspose.PDF ?
Aspose.PDF est une bibliothèque permettant de créer, de manipuler et de convertir des documents PDF dans des applications .NET.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui ! Aspose propose une version d'essai gratuite pour évaluer ses produits. Vous pouvez la télécharger[ici](https://releases.aspose.com/).

### Est-il possible d'ajouter plusieurs annotations à l'encre ?
 Absolument ! Vous pouvez créer plusieurs`InkAnnotation` objets et les ajouter à la page de votre document.

### Où puis-je trouver plus d’exemples ?
 Vous pouvez consulter le[documentation](https://reference.aspose.com/pdf/net/) pour des tutoriels détaillés et des exemples.

### Que faire si j'ai besoin d'aide ?
 Si vous rencontrez des problèmes, vous pouvez demander de l'aide sur le[Forum de soutien](https://forum.aspose.com/c/pdf/10).