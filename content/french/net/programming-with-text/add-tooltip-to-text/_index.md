---
title: Ajouter une info-bulle au texte dans un fichier PDF
linktitle: Ajouter une info-bulle au texte dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter des info-bulles au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-text/add-tooltip-to-text/
---
Ce didacticiel vous guidera tout au long du processus d'ajout d'info-bulles au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter des info-bulles au texte, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Créer un exemple de document avec du texte
 Créer un nouveau`Document` objet et ajoutez des pages avec des fragments de texte. Dans le code fourni, deux fragments de texte sont ajoutés au document avec le texte d'info-bulle correspondant.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Étape 5 : Ouvrez le document et recherchez les fragments de texte
 Chargez le document créé à l'aide du`Document` constructeur et trouvez les fragments de texte qui nécessitent des info-bulles en utilisant`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Étape 6 : Ajouter des info-bulles aux fragments de texte
 Parcourez les fragments de texte extraits et créez des boutons invisibles à leurs positions. Attribuez le texte d'info-bulle souhaité au`AlternateName` propriété du`ButtonField`. Ajoutez les champs du bouton au formulaire du document.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Étape 7 : Répétez l'opération pour des fragments de texte supplémentaires avec de longues info-bulles
Répétez les étapes 5 et 6 pour les fragments de texte comportant de longues info-bulles. Modifiez les critères de recherche et le texte de l'info-bulle en conséquence.

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
 Enregistrez le document PDF modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
document. Save(outputFile);
```

### Exemple de code source pour Ajouter une info-bulle au texte à l’aide d’Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
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
// Acceptez l'absorbeur pour les pages du document
document.Pages.Accept(absorber);
// Obtenez les fragments de texte extraits
TextFragmentCollection textFragments = absorber.TextFragments;
// Parcourez les fragments
foreach (TextFragment fragment in textFragments)
{
	// Créer un bouton invisible sur la position du fragment de texte
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// La valeur AlternateName sera affichée sous forme d'info-bulle par une application de visualisation
	field.AlternateName = "Tooltip for text.";
	// Ajouter un champ de bouton au document
	document.Form.Add(field);
}
// Le prochain sera un extrait d'une très longue info-bulle
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
Vous avez ajouté avec succès des info-bulles au texte d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

## FAQ

#### Q : Quel est l'objet de ce didacticiel ?

R : Ce didacticiel se concentre sur l'ajout d'info-bulles au texte d'un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms doivent être importés pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter des info-bulles au texte, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Dans le code, recherchez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment puis-je créer un exemple de document avec du texte ?

 R : À l'étape 4, vous allez créer un nouveau`Document` objet et ajouter des pages avec des fragments de texte. Le code fourni ajoute deux fragments de texte avec le texte d'info-bulle correspondant.

#### Q : Comment puis-je ouvrir le document et trouver les fragments de texte ?

 R : À l'étape 5, vous chargerez le document créé à l'aide du`Document` constructeur et recherchez les fragments de texte nécessitant des info-bulles à l'aide du`TextFragmentAbsorber`.

#### Q : Comment puis-je ajouter des info-bulles aux fragments de texte ?

 R : À l'étape 6, vous parcourirez les fragments de texte extraits et créerez des boutons invisibles à leurs positions. Le texte de l'info-bulle est attribué au`AlternateName` propriété du`ButtonField`qui est ajouté au formulaire du document.

#### Q : Comment puis-je répéter le processus pour des fragments de texte supplémentaires comportant de longues info-bulles ?

R : Pour les fragments de texte avec de longues info-bulles, répétez les étapes 5 et 6. Modifiez les critères de recherche et le texte de l'info-bulle en conséquence.

#### Q : Comment puis-je enregistrer le document modifié ?

 R : À l'étape 8, vous enregistrerez le document PDF modifié à l'aide du`Save` méthode du`Document` objet.

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris comment améliorer votre document PDF en ajoutant des info-bulles au texte à l'aide d'Aspose.PDF pour .NET. Cela peut fournir des informations supplémentaires précieuses aux lecteurs lorsqu'ils interagissent avec le contenu PDF.