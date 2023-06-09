---
title: Ajouter une info-bulle au texte
linktitle: Ajouter une info-bulle au texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des info-bulles au texte d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-text/add-tooltip-to-text/
---

Ce didacticiel vous guidera tout au long du processus d'ajout d'info-bulles au texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter des info-bulles au texte, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Créer un exemple de document avec du texte
 Créer un nouveau`Document` objet et ajouter des pages avec des fragments de texte. Dans le code fourni, deux fragments de texte sont ajoutés au document avec le texte d'info-bulle respectif.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Étape 5 : Ouvrez le document et recherchez les fragments de texte
 Chargez le document créé à l'aide de la`Document` constructeur et trouvez les fragments de texte qui ont besoin d'info-bulles en utilisant`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Étape 6 : Ajoutez des info-bulles aux fragments de texte
 Parcourez les fragments de texte extraits et créez des boutons invisibles à leurs positions. Attribuez le texte d'info-bulle souhaité au`AlternateName` propriété de la`ButtonField`. Ajoutez les champs de bouton au formulaire du document.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Étape 7 : Répétez l'opération pour des fragments de texte supplémentaires avec de longues info-bulles
Répétez les étapes 5 et 6 pour les fragments de texte avec de longues info-bulles. Modifiez les critères de recherche et le texte de l'info-bulle en conséquence.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Étape 8 : Enregistrez le document modifié
 Enregistrez le document PDF modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
document. Save(outputFile);
```

### Exemple de code source pour Ajouter une info-bulle au texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Créer un exemple de document avec du texte
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Ouvrir un document avec du texte
Document document = new Document(outputFile);
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accepter l'absorbeur pour les pages du document
document.Pages.Accept(absorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragments = absorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment fragment in textFragments)
{
	//Créer un bouton invisible sur la position du fragment de texte
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// La valeur AlternateName sera affichée sous forme d'info-bulle par une application de visualisation
	field.AlternateName = "Tooltip for text.";
	// Ajouter un champ de bouton au document
	document.Form.Add(field);
}
// Ensuite, il y aura un exemple de très longue info-bulle
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Définir un texte très long
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Enregistrer le document
document.Save(outputFile);
```

## Conclusion
Vous avez ajouté avec succès des info-bulles au texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.