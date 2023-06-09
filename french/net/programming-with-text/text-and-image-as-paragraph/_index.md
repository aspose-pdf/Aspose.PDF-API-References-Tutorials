---
title: Texte et image sous forme de paragraphe
linktitle: Texte et image sous forme de paragraphe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du texte et une image sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 530
url: /fr/net/programming-with-text/text-and-image-as-paragraph/
---

Ce didacticiel explique comment ajouter du texte et une image sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Étape 3 : Définissez le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de la`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : créer un nouveau document et une nouvelle page

 Créer un nouveau`Document` objet et ajouter une page à sa collection de pages :

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 5 : Créer un TextFragment et l'ajouter en tant que paragraphe

 Créer un`TextFragment`objet et ajoutez-le à la collection de paragraphes de la page :

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Étape 6 : Ajouter une image en tant que paragraphe en ligne

 Créé un`Aspose.Pdf.Image` objet et définissez-le comme un paragraphe en ligne afin qu'il apparaisse juste après le paragraphe précédent :

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Facultatif : définir la hauteur de l'image
image.FixWidth = 100; // Facultatif : définir la largeur de l'image
page.Paragraphs.Add(image);
```

 Remplacer`"aspose-logo.jpg"` avec le nom réel du fichier image et ajustez la hauteur et la largeur facultatives de l'image comme vous le souhaitez.

## Étape 7 : Ajouter un autre TextFragment en tant que paragraphe en ligne

 Réinitialisez le`TextFragment` objet avec un contenu différent et ajoutez-le en tant que paragraphe en ligne :

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

 Assurez-vous de remplacer`"TextAndImageAsParagraph_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour le texte et l'image en tant que paragraphe à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages de l'instance Document
Page page = doc.Pages.Add();
// Créer TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Ajouter un fragment de texte à la collection de paragraphes de l'objet Page
page.Paragraphs.Add(text);
// Créer une instance d'image
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Définissez l'image comme paragraphe en ligne afin qu'elle apparaisse juste après
// L'objet paragraphe précédent (TextFragment)
image.IsInLineParagraph = true;
// Spécifiez le chemin du fichier image
image.File = dataDir + "aspose-logo.jpg";
// Définir la hauteur de l'image (facultatif)
image.FixHeight = 30;
// Définir la largeur de l'image (facultatif)
image.FixWidth = 100;
//Ajouter une image à la collection de paragraphes de l'objet de page
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

Toutes nos félicitations! Vous avez appris avec succès comment ajouter du texte et une image sous forme de paragraphes en ligne dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la configuration du projet à l'enregistrement du document modifié. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour personnaliser la mise en page du texte et des images dans les fichiers PDF.