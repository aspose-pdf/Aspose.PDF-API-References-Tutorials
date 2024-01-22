---
title: Texte et image sous forme de paragraphe dans un fichier PDF
linktitle: Texte et image sous forme de paragraphe dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter du texte et une image sous forme de paragraphes en ligne dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 530
url: /fr/net/programming-with-text/text-and-image-as-paragraph/
---
Ce didacticiel explique comment ajouter du texte et une image sous forme de paragraphes en ligne dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous d'avoir les éléments suivants :

- Connaissance de base du langage de programmation C#.
- Aspose.PDF pour la bibliothèque .NET installée. Vous pouvez l'obtenir sur le site Web Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Étape 3 : Définir le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Créer un nouveau document et une nouvelle page

 Créer un nouveau`Document` objet et ajoutez une page à sa collection de pages :

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 5 : Créez un TextFragment et ajoutez-le sous forme de paragraphe

 Créer un`TextFragment` objet et ajoutez-le à la collection de paragraphes de la page :

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Étape 6 : Ajouter une image en tant que paragraphe en ligne

 Créé un`Aspose.Pdf.Image` object et définissez-le comme paragraphe en ligne afin qu'il apparaisse juste après le paragraphe précédent :

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Facultatif : définir la hauteur de l'image
image.FixWidth = 100; // Facultatif : définir la largeur de l'image
page.Paragraphs.Add(image);
```

 Remplacer`"aspose-logo.jpg"` avec le nom réel du fichier image et ajustez la hauteur et la largeur facultatives de l’image comme vous le souhaitez.

## Étape 7 : ajouter un autre TextFragment en tant que paragraphe en ligne

 Réinitialisez le`TextFragment` objet avec un contenu différent et ajoutez-le sous forme de paragraphe en ligne :

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Étape 8 : Enregistrez le document PDF

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Assurez-vous de remplacer`"TextAndImageAsParagraph_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour le texte et l'image sous forme de paragraphe à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages de l'instance de document
Page page = doc.Pages.Add();
// Créer TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Ajouter un fragment de texte à la collection de paragraphes de l'objet Page
page.Paragraphs.Add(text);
// Créer une instance d'image
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Définir l'image comme paragraphe en ligne afin qu'elle apparaisse juste après
// L'objet paragraphe précédent (TextFragment)
image.IsInLineParagraph = true;
// Spécifier le chemin du fichier image
image.File = dataDir + "aspose-logo.jpg";
// Définir la hauteur de l'image (facultatif)
image.FixHeight = 30;
// Définir la largeur de l'image (facultatif)
image.FixWidth = 100;
// Ajouter une image à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(image);
// Réinitialiser l'objet TextFragment avec un contenu différent
text = new TextFragment(" Hello Again..");
// Définir TextFragment comme paragraphe en ligne
text.IsInLineParagraph = true;
// Ajouter TextFragment nouvellement créé à la collection de paragraphes de la page
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment ajouter du texte et une image sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la configuration du projet jusqu'à l'enregistrement du document modifié. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour personnaliser la disposition du texte et des images dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Texte et image sous forme de paragraphe dans un fichier PDF » ?

R : Le didacticiel « Texte et image en tant que paragraphe dans un fichier PDF » vise à guider les utilisateurs sur la manière d'ajouter du texte et des images sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le didacticiel fournit des instructions étape par étape et des exemples de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à ajouter du texte et des images sous forme de paragraphes en ligne ?

R : Ce didacticiel aide les utilisateurs à comprendre comment utiliser Aspose.PDF pour .NET pour incorporer du texte et des images sous forme de paragraphes en ligne dans un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent créer des fichiers PDF avec des mises en page personnalisées combinant texte et images.

#### Q : Quels prérequis sont requis pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permet d'utiliser les fonctionnalités de la bibliothèque pour travailler avec des documents PDF, des fragments de texte et des images.

#### Q : Puis-je utiliser ce didacticiel pour ajouter plusieurs paragraphes de texte et d'images dans un PDF ?

R : Oui, vous pouvez utiliser les exemples de code fournis pour ajouter plusieurs instances de paragraphes de texte et d'image dans le même document PDF. Ce didacticiel montre comment créer des paragraphes en ligne, facilitant ainsi l'inclusion de différentes combinaisons de texte et d'images.

#### Q : Comment puis-je spécifier le contenu et l'apparence des paragraphes de texte et des images ?

 R : Le didacticiel montre comment créer`TextFragment`objets pour représenter des paragraphes de texte et`Aspose.Pdf.Image` objets pour représenter des images. Vous pouvez personnaliser le contenu, les dimensions et l'apparence du texte et des images à l'aide des exemples de code fournis.

#### Q : Puis-je ajuster la disposition des paragraphes en ligne ?

 R : Oui, vous pouvez ajuster la disposition des paragraphes en ligne en contrôlant leur positionnement, leurs dimensions et leur ordre dans la page. Le didacticiel montre comment définir des attributs en ligne, tels que`IsInLineParagraph`, pour contrôler la disposition des paragraphes de texte et d’image.

#### Q : Comment puis-je enregistrer le document PDF modifié ?

 R : Pour enregistrer le document PDF modifié, vous pouvez utiliser le`Save` méthode du`Document` objet. Le didacticiel fournit des exemples de code qui montrent comment enregistrer le document PDF résultant.