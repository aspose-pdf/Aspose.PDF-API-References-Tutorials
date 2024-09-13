---
title: Texte et image sous forme de paragraphe dans un fichier PDF
linktitle: Texte et image sous forme de paragraphe dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter du texte et une image sous forme de paragraphes en ligne dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 530
url: /fr/net/programming-with-text/text-and-image-as-paragraph/
---
Ce tutoriel explique comment ajouter du texte et une image sous forme de paragraphes en ligne dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre le processus étape par étape.

## Prérequis

Avant de poursuivre le didacticiel, assurez-vous de disposer des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Étape 3 : définir le chemin d’accès au répertoire du document

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de l'`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Créer un nouveau document et une nouvelle page

 Créer un nouveau`Document` objet et ajouter une page à sa collection de pages :

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 5 : Créez un fragment de texte et ajoutez-le en tant que paragraphe

 Créer un`TextFragment` objet et l'ajouter à la collection de paragraphes de la page :

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Étape 6 : ajouter une image sous forme de paragraphe en ligne

 Créer un`Aspose.Pdf.Image` objet et définissez-le comme paragraphe en ligne afin qu'il apparaisse juste après le paragraphe précédent :

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Facultatif : définir la hauteur de l'image
image.FixWidth = 100; // Facultatif : définir la largeur de l'image
page.Paragraphs.Add(image);
```

 Remplacer`"aspose-logo.jpg"` avec le nom du fichier image réel et ajustez la hauteur et la largeur facultatives de l'image comme vous le souhaitez.

## Étape 7 : ajouter un autre TextFragment en tant que paragraphe en ligne

 Réinitialiser le`TextFragment` objet avec un contenu différent et l'ajouter en tant que paragraphe en ligne :

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Étape 8 : Enregistrez le document PDF

Enregistrez le document PDF modifié :

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Assurez-vous de remplacer`"TextAndImageAsParagraph_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour le texte et l'image sous forme de paragraphe à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages de l'instance de document
Page page = doc.Pages.Add();
// Créer un fragment de texte
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
// Ajoutez le TextFragment nouvellement créé à la collection de paragraphes de la page
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusion

Félicitations ! Vous avez appris avec succès à ajouter du texte et une image sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la configuration du projet à l'enregistrement du document modifié. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour personnaliser la mise en page du texte et des images dans les fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Texte et image sous forme de paragraphe dans un fichier PDF » ?

R : Le didacticiel « Texte et image en tant que paragraphe dans un fichier PDF » vise à guider les utilisateurs sur la façon d'ajouter du texte et des images sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le didacticiel fournit des instructions étape par étape et des exemples de code C# pour illustrer le processus.

#### Q : Comment ce didacticiel aide-t-il à ajouter du texte et des images sous forme de paragraphes en ligne ?

R : Ce didacticiel aide les utilisateurs à comprendre comment utiliser Aspose.PDF pour .NET pour incorporer du texte et des images sous forme de paragraphes en ligne dans un document PDF. En suivant les étapes et les exemples de code fournis, les utilisateurs peuvent créer des fichiers PDF avec des mises en page personnalisées qui combinent du texte et des images.

#### Q : Quels sont les prérequis nécessaires pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web d'Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Pour commencer, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Cela vous permet d'utiliser les fonctionnalités de la bibliothèque pour travailler avec des documents PDF, des fragments de texte et des images.

#### Q : Puis-je utiliser ce didacticiel pour ajouter plusieurs paragraphes de texte et d’image dans un PDF ?

R : Oui, vous pouvez utiliser les exemples de code fournis pour ajouter plusieurs instances de paragraphes de texte et d'images dans le même document PDF. Ce didacticiel montre comment créer des paragraphes en ligne, ce qui facilite l'inclusion de différentes combinaisons de texte et d'images.

#### Q : Comment spécifier le contenu et l’apparence des paragraphes de texte et des images ?

 A : Le didacticiel montre comment créer`TextFragment`objets pour représenter des paragraphes de texte et`Aspose.Pdf.Image` objets pour représenter des images. Vous pouvez personnaliser le contenu, les dimensions et l'apparence du texte et des images à l'aide des exemples de code fournis.

#### Q : Puis-je ajuster la mise en page des paragraphes en ligne ?

 R : Oui, vous pouvez ajuster la mise en page des paragraphes en ligne en contrôlant leur positionnement, leurs dimensions et leur ordre dans la page. Le didacticiel montre comment définir des attributs en ligne, tels que`IsInLineParagraph`, pour contrôler la mise en page des paragraphes de texte et d'image.

#### Q : Comment enregistrer le document PDF modifié ?

 R : Pour enregistrer le document PDF modifié, vous pouvez utiliser le`Save` méthode de la`Document` objet. Le didacticiel fournit des exemples de code qui montrent comment enregistrer le document PDF résultant.