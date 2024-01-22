---
title: Stel het bijschrift van de keuzerondje in
linktitle: Stel het bijschrift van de keuzerondje in
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET gebruikt om het bijschrift voor een keuzerondje in een PDF-formulier in te stellen.
type: docs
weight: 280
url: /nl/net/programming-with-forms/set-radio-button-caption/
---
In deze handleiding leggen we stap voor stap uit hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om het bijschrift van een keuzerondje in een PDF-formulier te definiëren. We laten u zien hoe u toegang krijgt tot het keuzerondjeveld, een nieuwe keuzerondje kunt maken en het knopbijschrift kunt aanpassen.

## Stap 1: De documentmap configureren

 De eerste stap is het configureren van de documentmap waarin het PDF-formulier staat waaraan u wilt werken. U kunt gebruik maken van de`dataDir` variabele om het mappad op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het bron-PDF-formulier laden

 In deze stap laden we het bron-PDF-formulier met behulp van de`Aspose.Pdf.Facades.Form` klasse van Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Zorg ervoor dat het PDF-bestand met het formulier aanwezig is in de opgegeven documentenmap.

## Stap 3: Het bijschrift van het keuzerondje bewerken

We doorlopen de veldnamen van het formulier en zoeken naar keuzerondjevelden. Als er een overeenkomend veld wordt gevonden, maken we een nieuwe keuzerondje met een aangepast bijschrift en voegen we dit toe aan het bestaande veld.

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
// Maak een TextParagraph-object
TextParagraph par = new TextParagraph();
// Stel de alineapositie in
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Geef de woordomloopmodus op
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Voeg het nieuwe TextFragment toe aan de alinea
par.AppendLine(updatedFragment);
// Voeg de TextParagraph toe met TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Pas indien nodig het keuzerondje voor het bijschrift en andere instellingen aan.

## Stap 4: De resulterende PDF opslaan

 Nu we klaar zijn met het aanpassen van het bijschrift van de keuzerondjes, kunnen we de resulterende PDF opslaan met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor de resulterende PDF opgeeft.

### Voorbeeldbroncode voor Set Radio Button Caption met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Bron-PDF-formulier laden
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
		// Maak een TextParagraph-object
		TextParagraph par = new TextParagraph();
		// Stel de alineapositie in
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Geef de tekstomloopmodus op
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Voeg een nieuw tekstfragment toe aan de alinea
		par.AppendLine(updatedFragment);
		// Voeg de TextParagraph toe met TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusie

In deze handleiding hebben we geleerd hoe we de Aspose.PDF-bibliotheek voor .NET kunnen gebruiken om het bijschrift voor een keuzerondje in een PDF-formulier in te stellen. Door de beschreven stappen te volgen, kunt u de opties voor de keuzerondjes aanpassen en het bijschrift indien nodig wijzigen. Voel je vrij om de functies van Aspose.PDF voor .NET verder te verkennen om de mogelijkheden voor het manipuleren van PDF-bestanden uit te breiden.

### Veelgestelde vragen

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om bijschriften voor keuzerondjes in een PDF-formulier in te stellen?

A: Ja, u kunt Aspose.PDF voor .NET gebruiken om bijschriften voor keuzerondjes in PDF-vorm in te stellen. De meegeleverde voorbeeldbroncode laat zien hoe u toegang krijgt tot het keuzerondjeveld, een nieuwe keuzerondjeoptie met een aangepast bijschrift kunt maken en het bestaande veld kunt bijwerken.

#### Vraag: Hoe kan ik het uiterlijk van het bijschrift van het keuzerondje aanpassen, zoals lettergrootte en kleur?

 A: U kunt het uiterlijk van het bijschrift van de keuzerondjes aanpassen door de eigenschappen van het`TextFragment` gebruikt voor het onderschrift. U kunt bijvoorbeeld het lettertype, de lettergrootte, de kleur, de regelafstand en andere opties voor tekstopmaak instellen.

#### Vraag: Is het mogelijk om meerdere keuzerondjes met verschillende bijschriften toe te voegen aan een enkele keuzerondjesgroep?

A: Ja, u kunt meerdere keuzerondjes met verschillende bijschriften toevoegen aan een enkele keuzerondjesgroep. Elke optie vertegenwoordigt een andere keuze en gebruikers kunnen slechts één optie uit de groep selecteren.

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om andere formuliervelden in een PDF-document te wijzigen?

A: Ja, Aspose.PDF voor .NET biedt een uitgebreide reeks functies voor het manipuleren van verschillende formuliervelden in een PDF-document, zoals tekstvelden, selectievakjes, vervolgkeuzelijsten en meer. U kunt de bibliotheek gebruiken om waarden in te stellen, het uiterlijk te wijzigen en interactiviteit aan formuliervelden toe te voegen.

#### Vraag: Ondersteunt Aspose.PDF voor .NET het werken met PDF's die zijn gegenereerd uit andere bronnen, zoals gescande documenten?

A: Ja, Aspose.PDF voor .NET ondersteunt het werken met PDF's die zijn gegenereerd uit verschillende bronnen, inclusief gescande documenten. De bibliotheek biedt OCR-mogelijkheden (Optical Character Recognition) om tekst uit gescande PDF's te extraheren en de inhoud programmatisch te manipuleren.