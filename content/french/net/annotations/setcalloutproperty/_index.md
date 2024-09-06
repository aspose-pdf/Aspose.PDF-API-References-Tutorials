---
title: Définir la propriété de légende dans le fichier PDF
linktitle: Définir la propriété de légende dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir la propriété de légende dans un fichier PDF à l'aide d'Aspose.PDF pour .NET dans ce didacticiel détaillé, étape par étape.
type: docs
weight: 130
url: /fr/net/annotations/setcalloutproperty/
---
## Introduction

La création de documents PDF professionnels et visuellement attrayants nécessite souvent l'ajout d'annotations qui attirent l'attention sur un contenu spécifique. L'une de ces annotations est la légende, qui ressemble à ces bulles de dialogue que vous voyez dans les bandes dessinées. Elles aident à clarifier ou à mettre en valeur le texte dans votre PDF. Aspose.PDF pour .NET facilite énormément l'ajout de telles annotations à vos documents. Dans ce didacticiel, nous vous expliquerons comment définir la propriété de légende dans un fichier PDF à l'aide de cette puissante bibliothèque. Que vous soyez un développeur chevronné ou que vous débutiez, à la fin de ce guide, vous comprendrez clairement comment utiliser les légendes dans les fichiers PDF.

## Prérequis

Avant de plonger dans le code, couvrons les éléments essentiels dont vous avez besoin pour commencer.

1.  Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF pour .NET est installée. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
2. IDE : un environnement de développement tel que Visual Studio.
3. .NET Framework : assurez-vous que .NET est installé sur votre ordinateur.
4. Licence temporaire : si vous souhaitez tester toutes les fonctionnalités d'Aspose.PDF sans limitations, obtenez une[permis temporaire](https://purchase.aspose.com/temporary-license/).

## Paquets d'importation

Avant de commencer à écrire le code, vous devez importer les packages nécessaires qui vous permettront de travailler avec des fichiers PDF et des annotations.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ces importations vous fourniront toutes les classes et méthodes nécessaires pour manipuler des documents PDF et créer des annotations comme la légende.

## Étape 1 : Initialiser le document PDF

La première étape de notre parcours consiste à initialiser un nouveau document PDF dans lequel nous ajouterons notre annotation de légende. Considérez cela comme la configuration d'une toile vierge sur laquelle vous pouvez commencer à ajouter des éléments.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser un nouveau document PDF
Document doc = new Document();
```
 Ici, nous créons un nouveau`Document` objet qui servira de fichier PDF.`dataDir` la variable est définie sur le répertoire dans lequel vous souhaitez enregistrer votre fichier PDF une fois que nous avons terminé.

## Étape 2 : Ajouter une nouvelle page au document

Un document PDF peut contenir plusieurs pages. Dans cette étape, nous allons ajouter une nouvelle page à notre document. Cette page sera l'endroit où notre annotation de légende sera placée.

```csharp
//Ajouter une nouvelle page au document
Page page = doc.Pages.Add();
```
 Le`Pages.Add()`méthode est utilisée pour ajouter une nouvelle page à la`doc` objet. La nouvelle page est stockée dans le`page` variable, que nous utiliserons plus tard lors de l'ajout de l'annotation.

## Étape 3 : définir l’apparence par défaut

Les annotations, comme la légende, ont une apparence visuelle que vous pouvez personnaliser. Dans cette étape, nous allons définir l'apparence du texte dans la légende.

```csharp
// Définir l'apparence par défaut de l'annotation
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Nous créons un`DefaultAppearance` Objet qui définit la couleur du texte et la taille de la police. Ici, le texte sera rouge et la taille de la police est fixée à 10. Cette apparence sera appliquée à l'annotation de légende.

## Étape 4 : Créer l'annotation de texte libre

Il est maintenant temps de créer l'annotation proprement dite. L'annotation en texte libre nous permet d'ajouter une légende avec un texte et un style spécifiques.

```csharp
// Créer une annotation de texte libre avec une légende
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Nous créons un`FreeTextAnnotation` objet avec des coordonnées spécifiques, définissant sa position sur la page.`Intent` est réglé sur`FreeTextCallout` , indiquant qu'il s'agit d'une annotation de légende.`EndingStyle` est réglé sur`OpenArrow`ce qui signifie que la ligne de légende se terminera par une flèche ouverte.

## Étape 5 : Définir les points de la ligne de légende

Une annotation de légende comporte une ligne qui pointe vers la zone d'intérêt. Ici, nous allons définir les points qui composent cette ligne.

```csharp
// Définir les points pour la ligne de rappel
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 Le`Callout` la propriété est un tableau de`Point` objets, chacun représentant une coordonnée sur la page. Ces points définissent le chemin de la ligne de légende, lui donnant l'apparence classique d'une bulle de dialogue.

## Étape 6 : ajouter l'annotation à la page

Après avoir créé et configuré notre annotation, l’étape suivante consiste à l’ajouter à la page.

```csharp
// Ajouter l'annotation à la page
page.Annotations.Add(fta);
```
 Le`Annotations.Add()` La méthode est utilisée pour placer l'annotation sur la page que nous avons créée précédemment. Cette étape « dessine » effectivement la légende sur la page PDF.

## Étape 7 : définir le contenu du texte enrichi

Les annotations de légende peuvent inclure du texte enrichi, ce qui permet d'insérer du contenu formaté dans la bulle. Ajoutons un exemple de texte.

```csharp
// Définir le texte enrichi pour l'annotation
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Ceci est un échantillon</span></p></body>";
```
 Le`RichText` La propriété est définie avec le contenu HTML. Cela permet un formatage détaillé dans la légende, comme la spécification de la taille de la police, de la couleur et du style.

## Étape 8 : Enregistrez le document PDF

Enfin, après avoir tout configuré, nous devons enregistrer le document. Cette étape finalise la création du PDF avec l'annotation de légende.

```csharp
// Enregistrer le document
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 Le`Save()` La méthode enregistre le document dans le répertoire spécifié avec le nom de fichier « SetCalloutProperty.pdf ». Cette étape conclut notre processus de création de PDF.

## Conclusion

Et voilà ! Vous venez de créer un document PDF avec une annotation de légende à l'aide d'Aspose.PDF pour .NET. Cette annotation peut être incroyablement utile pour mettre en évidence ou expliquer des parties spécifiques de votre document. Aspose.PDF propose une API puissante qui rend la manipulation de PDF simple et flexible. Que vous ajoutiez des annotations, convertissiez des documents ou gériez des tâches PDF complexes, Aspose.PDF est là pour vous.

## FAQ

### Puis-je personnaliser davantage l’apparence de la légende ?

Absolument ! Vous pouvez personnaliser divers aspects tels que la couleur de la ligne, l'épaisseur, la famille de polices et le style du texte.

### Est-il possible d'ajouter plusieurs légendes sur une seule page ?

Oui, vous pouvez ajouter autant de légendes que nécessaire en répétant les étapes pour chaque annotation.

### Comment puis-je modifier la position de la légende ?

 Modifiez simplement les coordonnées dans le`Rectangle` et`Callout` propriétés pour repositionner l'annotation.

### Puis-je ajouter d’autres types d’annotations à l’aide d’Aspose.PDF ?

Oui, Aspose.PDF prend en charge différents types d'annotations, notamment les surlignements, les tampons et les pièces jointes.

### Le contenu de texte enrichi est-il limité au HTML ?

 Le`RichText` La propriété prend en charge un sous-ensemble de HTML, vous permettant d'inclure du texte stylisé et un formatage de base.