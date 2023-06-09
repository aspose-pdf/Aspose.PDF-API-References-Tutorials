---
title: Extraire le texte de l'annotation de tampon
linktitle: Extraire le texte de l'annotation de tampon
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire facilement du texte à partir d'une annotation de tampon dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment extraire du texte d'une annotation de tampon dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour extraire le texte d'une annotation de tampon spécifique sur une page donnée du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "test.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Extraire le texte de l'annotation du tampon

Maintenant que vous avez chargé le document PDF, vous pouvez extraire le texte de l'annotation de tampon spécifique. Voici comment:

```csharp
// Récupérer l'annotation du tampon
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Créer un absorbeur de texte
TextAbsorber ta = new TextAbsorber();

// Visitez l'apparence de l'annotation
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Afficher le texte extrait
Console.WriteLine(ta.Text);
```

Le code ci-dessus récupère l'annotation de tampon à partir de la page spécifiée du document PDF, puis utilise un absorbeur de texte pour extraire le texte de l'apparence de l'annotation. Le texte extrait est ensuite affiché dans la sortie.

### Exemple de code source pour Extraire le texte de l'annotation de tampon à l'aide d'Aspose.PDF pour .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Conclusion

Félicitation ! Vous avez appris à extraire du texte d'une annotation de tampon dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser cette méthode pour extraire du texte d'autres annotations dans vos documents PDF.
