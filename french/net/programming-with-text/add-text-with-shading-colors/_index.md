---
title: Ajouter du texte avec des couleurs d'ombrage
linktitle: Ajouter du texte avec des couleurs d'ombrage
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du texte avec des couleurs d'ombrage à un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-text/add-text-with-shading-colors/
---

Ce didacticiel vous guidera tout au long du processus d'ajout de texte avec des couleurs d'ombrage à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter du texte avec des couleurs d'ombrage, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Chargez le document PDF
 Chargez le document PDF existant à l'aide de la`Document` constructeur et indiquez le chemin d'accès au fichier de document.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Le code va ici...
}
```

## Étape 5 : Rechercher le texte à modifier
 Utiliser`TextFragmentAbsorber` pour trouver le texte souhaité dans le document. Dans le code fourni, il recherche le texte "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Étape 6 : Définir la couleur d'ombrage du texte
 Créer un nouveau`Color`objet avec un espace colorimétrique de motif et spécifiez les couleurs d'ombrage du dégradé. Attribuez cette couleur au`ForegroundColor` propriété de la`TextState` de la`TextFragment` objet.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Étape 7 : Appliquer une mise en forme de texte supplémentaire (facultatif)
 Vous pouvez appliquer une mise en forme supplémentaire au fragment de texte, comme le soulignement, en modifiant les propriétés du`TextState` objet.

```csharp
textFragment.TextState.Underline = true;
```

## Étape 8 : Enregistrez le document PDF modifié
 Enregistrez le document PDF modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Exemple de code source pour Ajouter du texte avec des couleurs d'ombrage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Créer une nouvelle couleur avec l'espace colorimétrique du motif
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusion
Vous avez ajouté avec succès du texte avec des couleurs d'ombrage à votre document PDF en utilisant Aspose.PDF pour .NET. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.