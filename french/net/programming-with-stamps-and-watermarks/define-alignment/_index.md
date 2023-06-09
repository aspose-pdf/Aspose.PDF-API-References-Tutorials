---
title: Définir l'alignement
linktitle: Définir l'alignement
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir facilement l'alignement du texte dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-stamps-and-watermarks/define-alignment/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment définir l'alignement du texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour créer un tampon de texte centré dans le document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier un objet Document avec le fichier d'entrée
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Définir l'alignement

Maintenant que vous avez chargé le document PDF, vous pouvez définir l'alignement du tampon de texte. Voici comment:

```csharp
// Instanciez un objet FormattedText avec l'exemple de chaîne
FormattedText text = new FormattedText("This");

// Ajouter une nouvelle ligne de texte à FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// Créer un objet TextStamp à l'aide de FormattedText
TextStamp stamp = new TextStamp(text);

// Spécifiez l'alignement horizontal du tampon de texte comme centré
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Spécifiez l'alignement vertical du tampon de texte comme centré
stamp.VerticalAlignment = VerticalAlignment.Center;

// Spécifiez l'alignement horizontal du texte dans le TextStamp comme centré
stamp.TextAlignment = HorizontalAlignment.Center;

// Définir la marge supérieure pour l'objet tampon
stamp. TopMargin = 20;

// Ajouter l'objet tampon à la première page du document
doc.Pages[1].AddStamp(stamp);
```

Le code ci-dessus crée un tampon de texte centré à l'aide de la classe FormattedText pour spécifier le contenu et définit l'alignement horizontal et vertical du tampon de texte.

## Étape 4 : Enregistrer le document de sortie

Une fois que vous avez défini l'alignement du tampon de texte, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document mis à jour
doc.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour définir l'alignement à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Instancier l'objet Document avec le fichier d'entrée
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Instancier l'objet FormattedText avec un exemple de chaîne
FormattedText text = new FormattedText("This");

// Ajouter une nouvelle ligne de texte à FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// Créer un objet TextStamp à l'aide de FormattedText
TextStamp stamp = new TextStamp(text);

// Spécifiez l'alignement horizontal du tampon de texte comme étant aligné au centre
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Spécifiez l'alignement vertical du tampon de texte comme étant aligné au centre
stamp.VerticalAlignment = VerticalAlignment.Center;

// Spécifiez l'alignement horizontal du texte de TextStamp comme aligné au centre
stamp.TextAlignment = HorizontalAlignment.Center;

// Définir la marge supérieure pour l'objet tampon
stamp.TopMargin = 20;

// Ajouter l'objet tampon sur la première page du document
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Conclusion

Félicitation ! Vous avez appris à définir l'alignement du texte dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances pour créer des tampons de texte avec différents alignements dans vos documents PDF.
