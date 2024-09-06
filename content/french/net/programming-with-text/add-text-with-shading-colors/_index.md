---
title: Ajouter du texte avec des couleurs d'ombrage dans un fichier PDF
linktitle: Ajouter du texte avec des couleurs d'ombrage dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter du texte avec des couleurs d'ombrage dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-text/add-text-with-shading-colors/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de texte avec des couleurs d'ombrage dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter du texte avec des couleurs d'ombrage, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Charger le document PDF
 Chargez le document PDF existant à l'aide de la`Document` constructeur et fournir le chemin vers le fichier de document.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Le code va ici...
}
```

## Étape 5 : Trouver le texte à modifier
 Utiliser`TextFragmentAbsorber` pour trouver le texte souhaité dans le document. Dans le code fourni, il recherche le texte "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Étape 6 : Définir la couleur d'ombrage du texte
 Créer un nouveau`Color` objet avec un espace colorimétrique de motif et spécifiez les couleurs d'ombrage du dégradé. Affectez cette couleur à l'`ForegroundColor` propriété de la`TextState` de la`TextFragment` objet.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Étape 7 : Appliquer une mise en forme de texte supplémentaire (facultatif)
 Vous pouvez appliquer une mise en forme supplémentaire au fragment de texte, comme le soulignement, en modifiant les propriétés du`TextState` objet.

```csharp
textFragment.TextState.Underline = true;
```

## Étape 8 : Enregistrez le document PDF modifié
 Enregistrez le document PDF modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Exemple de code source pour ajouter du texte avec des couleurs d'ombrage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
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
Vous avez ajouté avec succès du texte avec des couleurs d'ombrage à votre document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant se trouve désormais dans le chemin de fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif principal de ce tutoriel ?

R : Ce didacticiel vous guide tout au long du processus d'ajout de texte avec des couleurs d'ombrage à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce tutoriel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter du texte avec des couleurs d’ombrage, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment charger un document PDF existant ?

 A : À l'étape 4, vous chargerez un document PDF existant à l'aide de l'`Document` constructeur et en fournissant le chemin d'accès au fichier de document :

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Le code va ici...
}
```

#### Q : Comment puis-je trouver et modifier un texte spécifique dans le document PDF ?

 A : À l'étape 5, vous utiliserez le`TextFragmentAbsorber`pour trouver le texte souhaité dans le document. Vous pouvez ensuite modifier ses propriétés :

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### Q : Comment puis-je définir les couleurs d’ombrage du texte ?

 A : À l'étape 6, vous allez créer un nouveau`Color` objet avec un espace colorimétrique de motif et spécifiez les couleurs d'ombrage du dégradé. Affectez cette couleur à l'`ForegroundColor` propriété de la`TextState` de la`TextFragment` objet:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### Q : Puis-je appliquer une mise en forme de texte supplémentaire au texte modifié ?

 R : Oui, à l'étape 7, vous pouvez appliquer une mise en forme de texte supplémentaire telle que le soulignement en modifiant les propriétés du`TextState` objet:

```csharp
textFragment.TextState.Underline = true;
```

#### Q : Comment enregistrer le document PDF modifié ?

 A : À l'étape 8, vous enregistrerez le document PDF modifié à l'aide de l'`Save` méthode de la`Document` objet:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### Q : Quel est le principal point à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à améliorer votre document PDF en ajoutant du texte avec des couleurs d'ombrage à l'aide d'Aspose.PDF pour .NET. Cela peut être particulièrement utile pour mettre en évidence et souligner un contenu textuel spécifique dans vos fichiers PDF.