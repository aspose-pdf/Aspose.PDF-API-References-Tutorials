---
title: Fenêtre Obtenir le document
linktitle: Fenêtre Obtenir le document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser la fonction GetDocumentWindow d'Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.
type: docs
weight: 170
url: /fr/net/programming-with-document/getdocumentwindow/
---

 Aspose.PDF pour .NET est une puissante bibliothèque de manipulation de PDF qui permet aux développeurs de créer, modifier et convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la possibilité de récupérer des informations sur les propriétés de la fenêtre d'un document. Ce didacticiel vous guidera à travers les étapes d'utilisation de`GetDocumentWindow` fonctionnalité d'Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF pour .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Aspose.PDF pour la page de téléchargement .NET](https://releases.aspose.com/pdf/net).

Une fois que vous avez téléchargé la bibliothèque, extrayez le contenu du fichier ZIP dans un dossier sur votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Chargez le document PDF

 Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetDocumentWindow` fonctionnalité pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.

La première étape de l'utilisation de cette fonctionnalité consiste à charger le document PDF sur lequel vous souhaitez récupérer des informations. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour récupérer des informations sur les propriétés de la fenêtre du document.

## Étape 3 : Récupérer les propriétés de la fenêtre du document

Pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF, vous pouvez utiliser le code suivant :

```csharp
// Récupérer les propriétés de la fenêtre du document
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Dans le code ci-dessus, chaque ligne récupère une propriété de fenêtre différente du document PDF et l'envoie à la console. Vous pouvez personnaliser ce code pour récupérer uniquement les propriétés qui vous intéressent.

### Exemple de code source pour obtenir la fenêtre de document du fichier PDF à l'aide d'Aspose.PDF pour .NET 

 Voici le code source complet pour récupérer les propriétés de la fenêtre d'un document PDF en utilisant le`GetDocumentWindow` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Obtenir différentes propriétés de document
// Position de la fenêtre du document - Par défaut : false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordre de lecture prédominant ; détermine la position de la page
// Lorsqu'il est affiché côte à côte - Par défaut : L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Indique si la barre de titre de la fenêtre doit afficher le titre du document
// Si faux, la barre de titre affiche le nom du fichier PDF - Par défaut : faux
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// S'il faut redimensionner la fenêtre du document pour l'adapter à la taille de
// Première page affichée - Par défaut : false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Indique s'il faut masquer la barre de menus de l'application de visualisation - Par défaut : false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Indique s'il faut masquer la barre d'outils de l'application de visualisation - Par défaut : false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// S'il faut masquer les éléments de l'interface utilisateur comme les barres de défilement
// Et ne laissant que le contenu de la page affiché - Par défaut : false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Mode page du document. Comment afficher le document en quittant le mode plein écran.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// La mise en page, c'est-à-dire une seule page, une colonne
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Comment le document doit s'afficher lorsqu'il est ouvert
// C'est-à-dire afficher les vignettes, plein écran, afficher le panneau de pièces jointes
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```
