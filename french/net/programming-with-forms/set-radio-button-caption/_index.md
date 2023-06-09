---
title: Définir la légende du bouton radio
linktitle: Définir la légende du bouton radio
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour définir la légende d'un bouton radio dans un formulaire PDF.
type: docs
weight: 280
url: /fr/net/programming-with-forms/set-radio-button-caption/
---

Dans ce guide, nous expliquerons étape par étape comment utiliser la bibliothèque Aspose.PDF pour .NET pour définir la légende d'un bouton radio dans un formulaire PDF. Nous allons vous montrer comment accéder au champ du bouton radio, créer une nouvelle option de bouton radio et personnaliser la légende du bouton.

## Etape 1 : Configuration du répertoire de documents

 La première étape consiste à configurer le répertoire de documents dans lequel se trouve le formulaire PDF sur lequel vous souhaitez travailler. Vous pouvez utiliser le`dataDir`variable pour spécifier le chemin du répertoire.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Chargement du formulaire PDF source

 Dans cette étape, nous allons charger le formulaire PDF source en utilisant le`Aspose.Pdf.Facades.Form`classe de Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Assurez-vous que le fichier PDF contenant le formulaire est présent dans le répertoire de documents spécifié.

## Étape 3 : Modification de la légende du bouton radio

Nous allons parcourir les noms des champs de formulaire et rechercher les champs de bouton radio. Si un champ correspondant est trouvé, nous créerons une nouvelle option de bouton radio avec une légende personnalisée et l'ajouterons au champ existant.

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
// Spécifier le mode retour à la ligne
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Ajouter le nouveau TextFragment au paragraphe
par.AppendLine(updatedFragment);
// Ajouter le TextParagraph à l'aide de TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personnalisez le bouton radio de légende et d'autres paramètres selon vos besoins.

## Étape 4 : Enregistrer le PDF résultant

 Maintenant que nous avons fini de modifier la légende du bouton radio, nous pouvons enregistrer le PDF résultant en utilisant le`Save` méthode de la`Document` classe.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Assurez-vous de spécifier le chemin d'accès complet et le nom de fichier du PDF résultant.

### Exemple de code source pour définir la légende du bouton radio à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
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
		// Ajouter un nouveau TextFragment au paragraphe
		par.AppendLine(updatedFragment);
		// Ajouter le TextParagraph à l'aide de TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusion

Dans ce guide, nous avons appris à utiliser la bibliothèque Aspose.PDF pour .NET pour définir la légende d'un bouton radio dans un formulaire PDF. En suivant les étapes décrites, vous pouvez personnaliser les options du bouton radio et modifier la légende selon vos besoins. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.PDF pour .NET afin d'élargir les possibilités de manipulation des fichiers PDF.