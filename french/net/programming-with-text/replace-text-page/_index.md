---
title: Remplacer la page de texte
linktitle: Remplacer la page de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplacer du texte sur une page spécifique d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 370
url: /fr/net/programming-with-text/replace-text-page/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour remplacer du texte sur une page spécifique d'un document PDF. Le code source C# fourni illustre le processus étape par étape.

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
```

## Étape 3 : Chargez le document PDF

 Définissez le chemin d'accès à votre répertoire de documents PDF et chargez le document à l'aide de la`Document` classe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Rechercher et remplacer du texte

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Remplacer`"text"` avec le texte réel que vous souhaitez rechercher et remplacer.

## Étape 5 : Spécifiez la page cible

 Acceptez l'absorbeur pour une page particulière en accédant au`Pages` collecte de la`pdfDocument` objet et en appelant le`Accept` méthode:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Remplacer`2` par le numéro de page où vous souhaitez remplacer le texte. Notez que les numéros de page sont basés sur zéro, donc`0` représente la première page.

## Étape 6 : Récupérer les fragments de texte extraits

 Obtenez les fragments de texte extraits à l'aide de la`TextFragments` propriété de la`TextFragmentAbsorber` objet:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Étape 7 : parcourir les fragments de texte

Parcourez les fragments de texte récupérés et mettez à jour le texte et les autres propriétés comme vous le souhaitez :

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 Dans l'extrait de code ci-dessus, remplacez`"New Phrase"`avec le texte de remplacement que vous souhaitez utiliser. Vous pouvez également personnaliser d'autres propriétés telles que la police, la taille de la police, la couleur de premier plan et la couleur d'arrière-plan.

## Étape 8 : Enregistrez le PDF modifié

 Enregistrez le document PDF modifié dans un nouveau fichier à l'aide de la`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 Assurez-vous de remplacer`"ReplaceTextPage_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour Remplacer la page de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepter l'absorbeur pour une page particulière
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Mettre à jour le texte et d'autres propriétés
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment remplacer du texte sur une page spécifique d'un document PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, du chargement du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour automatiser le remplacement de texte dans les fichiers PDF.