---
title: Définir la légende du bouton radio
linktitle: Définir la légende du bouton radio
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour définir la légende d’un bouton radio dans un formulaire PDF.
type: docs
weight: 280
url: /fr/net/programming-with-forms/set-radio-button-caption/
---
Dans ce guide, nous vous expliquerons étape par étape comment utiliser la bibliothèque Aspose.PDF pour .NET pour définir la légende d'un bouton radio dans un formulaire PDF. Nous vous montrerons comment accéder au champ du bouton radio, créer une nouvelle option de bouton radio et personnaliser la légende du bouton.

## Étape 1 : Configuration du répertoire de documents

 La première étape consiste à configurer le répertoire de documents dans lequel se trouve le formulaire PDF sur lequel vous souhaitez travailler. Vous pouvez utiliser l'`dataDir` variable pour spécifier le chemin du répertoire.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 2 : Chargement du formulaire PDF source

 Dans cette étape, nous allons charger le formulaire PDF source à l'aide de l'`Aspose.Pdf.Facades.Form` classe d'Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Assurez-vous que le fichier PDF contenant le formulaire est présent dans le répertoire de documents spécifié.

## Étape 3 : Modification de la légende du bouton radio

Nous allons parcourir les noms des champs du formulaire et rechercher les champs de bouton radio. Si un champ correspondant est trouvé, nous créerons une nouvelle option de bouton radio avec une légende personnalisée et l'ajouterons au champ existant.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Créer un objet TextParagraph
TextParagraph par = new TextParagraph();
// Définir la position du paragraphe
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Spécifier le mode de retour à la ligne
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Ajoutez le nouveau TextFragment au paragraphe
par.AppendLine(updatedFragment);
// Ajoutez le TextParagraph à l'aide de TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personnalisez le bouton radio de légende et d’autres paramètres selon vos besoins.

## Étape 4 : enregistrement du PDF obtenu

 Maintenant que nous avons terminé de modifier la légende du bouton radio, nous pouvons enregistrer le PDF résultant à l'aide de l'`Save` méthode de la`Document` classe.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Assurez-vous de spécifier le chemin complet et le nom de fichier du PDF résultant.

### Exemple de code source pour définir la légende du bouton radio à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le formulaire PDF source
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Créer un objet TextParagraph
		TextParagraph par = new TextParagraph();
		// Définir la position du paragraphe
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Spécifier le mode de retour à la ligne
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Ajouter un nouveau fragment de texte au paragraphe
		par.AppendLine(updatedFragment);
		// Ajoutez le TextParagraph à l'aide de TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusion

Dans ce guide, nous avons appris à utiliser la bibliothèque Aspose.PDF pour .NET pour définir la légende d'un bouton radio dans un formulaire PDF. En suivant les étapes décrites, vous pouvez personnaliser les options du bouton radio et modifier la légende selon vos besoins. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.PDF pour .NET pour étendre les possibilités de manipulation des fichiers PDF.

### FAQ

#### Q : Puis-je utiliser Aspose.PDF pour .NET pour définir des légendes pour les boutons radio dans un formulaire PDF ?

R : Oui, vous pouvez utiliser Aspose.PDF pour .NET pour définir des légendes pour les boutons radio dans un formulaire PDF. L'exemple de code source fourni montre comment accéder au champ de bouton radio, créer une nouvelle option de bouton radio avec une légende personnalisée et mettre à jour le champ existant.

#### Q : Comment puis-je personnaliser l’apparence de la légende du bouton radio, comme la taille et la couleur de la police ?

 R : Vous pouvez personnaliser l'apparence de la légende du bouton radio en ajustant les propriétés du`TextFragment` utilisé pour la légende. Par exemple, vous pouvez définir la police, la taille de la police, la couleur, l'espacement des lignes et d'autres options de formatage du texte.

#### Q : Est-il possible d’ajouter plusieurs options de boutons radio avec des légendes différentes à un seul groupe de boutons radio ?

R : Oui, vous pouvez ajouter plusieurs options de boutons radio avec des légendes différentes à un seul groupe de boutons radio. Chaque option représentera un choix différent et les utilisateurs ne pourront sélectionner qu'une seule option du groupe.

#### Q : Puis-je utiliser Aspose.PDF pour .NET pour modifier d’autres champs de formulaire dans un document PDF ?

R : Oui, Aspose.PDF pour .NET fournit un ensemble complet de fonctionnalités permettant de manipuler divers champs de formulaire dans un document PDF, tels que des champs de texte, des cases à cocher, des listes déroulantes, etc. Vous pouvez utiliser la bibliothèque pour définir des valeurs, modifier l'apparence et ajouter de l'interactivité aux champs de formulaire.

#### Q : Aspose.PDF pour .NET prend-il en charge le travail avec des fichiers PDF générés à partir d’autres sources, telles que des documents numérisés ?

R : Oui, Aspose.PDF pour .NET prend en charge l'utilisation de fichiers PDF générés à partir de diverses sources, y compris des documents numérisés. La bibliothèque offre des fonctionnalités OCR (reconnaissance optique de caractères) pour extraire du texte à partir de fichiers PDF numérisés et manipuler le contenu par programmation.