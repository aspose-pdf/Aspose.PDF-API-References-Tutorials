---
title: Fenêtre Obtenir le document
linktitle: Fenêtre Obtenir le document
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment utiliser la fonctionnalité GetDocumentWindow d'Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de fenêtre d'un document PDF.
type: docs
weight: 170
url: /fr/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF pour .NET est une puissante bibliothèque de manipulation de PDF qui permet aux développeurs de créer, modifier et convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la possibilité de récupérer des informations sur les propriétés de la fenêtre d'un document. Ce tutoriel vous guidera à travers les étapes d'utilisation du`GetDocumentWindow` fonctionnalité d'Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF pour .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Page de téléchargement Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net).

Une fois que vous avez téléchargé la bibliothèque, extrayez le contenu du fichier ZIP dans un dossier sur votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Charger le document PDF

Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetDocumentWindow` fonctionnalité pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF.

La première étape pour utiliser cette fonctionnalité consiste à charger le document PDF sur lequel vous souhaitez récupérer des informations. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Ouvrez le document PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour récupérer des informations sur les propriétés de la fenêtre du document.

## Étape 3 : Récupérer les propriétés de la fenêtre du document

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

Dans le code ci-dessus, chaque ligne récupère une propriété de fenêtre différente du document PDF et la renvoie à la console. Vous pouvez personnaliser ce code pour récupérer uniquement les propriétés qui vous intéressent.

### Exemple de code source pour obtenir la fenêtre de document d'un fichier PDF à l'aide d'Aspose.PDF pour .NET 

 Voici le code source complet pour récupérer les propriétés de la fenêtre d'un document PDF à l'aide de l'outil`GetDocumentWindow` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Obtenez différentes propriétés de document
// Position de la fenêtre du document - Par défaut : false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordre de lecture prédominant ; détermine la position de la page
// Lorsqu'il est affiché côte à côte - Par défaut : L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Si la barre de titre de la fenêtre doit afficher le titre du document
// Si faux, la barre de titre affiche le nom du fichier PDF - Par défaut : false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// S'il faut redimensionner la fenêtre du document pour l'adapter à la taille de
// Première page affichée - Par défaut : false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// S'il faut masquer la barre de menus de l'application de visualisation - Par défaut : false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//S'il faut masquer la barre d'outils de l'application de visualisation - Par défaut : false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// S'il faut masquer les éléments de l'interface utilisateur comme les barres de défilement
// Et en laissant uniquement le contenu de la page affiché - Par défaut : false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Mode page du document. Comment afficher le document en quittant le mode plein écran.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// La mise en page, c'est-à-dire une seule page, une colonne
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Comment le document doit s'afficher une fois ouvert
// C'est-à-dire afficher les vignettes, en plein écran, afficher le panneau des pièces jointes
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser Aspose.PDF pour .NET pour récupérer des informations sur les propriétés de la fenêtre d'un document PDF. En chargeant un document PDF et en accédant aux propriétés de sa fenêtre, vous pouvez recueillir des informations sur la façon dont le document doit être affiché lorsqu'il est ouvert dans une application de visualisation. Aspose.PDF pour .NET fournit un ensemble puissant de fonctionnalités pour travailler avec des fichiers PDF par programmation, ce qui en fait un outil précieux pour la manipulation de PDF dans les applications .NET.

### FAQ

#### Q : Quel est le but de récupérer les propriétés de la fenêtre d'un document PDF ?

R : La récupération des propriétés de la fenêtre d'un document PDF vous permet de recueillir des informations sur la façon dont le document PDF doit être affiché lorsqu'il est ouvert dans une application de visualisation. Ces propriétés contrôlent divers aspects tels que la position de la fenêtre, le mode d'affichage et la visibilité des éléments de l'interface utilisateur.

#### Q : Comment puis-je installer Aspose.PDF pour .NET dans mon projet .NET ?

 R : Pour installer Aspose.PDF pour .NET, vous devez télécharger la bibliothèque à partir du[Page de téléchargement Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net). Après le téléchargement, extrayez le contenu du fichier ZIP et ajoutez une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

#### Q : Puis-je personnaliser le code pour récupérer uniquement des propriétés de fenêtre spécifiques ?

R : Oui, vous pouvez personnaliser le code pour récupérer des propriétés de fenêtre spécifiques en commentant les lignes dont vous n'avez pas besoin. Chaque ligne du code correspond à une propriété de fenêtre spécifique, vous pouvez donc inclure ou exclure des propriétés en fonction de vos besoins.

#### Q : Quels types de propriétés de fenêtre puis-je récupérer à l’aide d’Aspose.PDF pour .NET ?

R : En utilisant Aspose.PDF pour .NET, vous pouvez récupérer diverses propriétés de fenêtre d'un document PDF, notamment le centrage de la fenêtre, la définition de la mise en page, le contrôle de l'affichage des barres d'outils et des barres de menus, et bien plus encore.