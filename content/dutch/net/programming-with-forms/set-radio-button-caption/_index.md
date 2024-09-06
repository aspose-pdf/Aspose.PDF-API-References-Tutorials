---
title: Bijschrift voor keuzerondje instellen
linktitle: Bijschrift voor keuzerondje instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om het bijschrift voor een keuzerondje in een PDF-formulier in te stellen.
type: docs
weight: 280
url: /nl/net/programming-with-forms/set-radio-button-caption/
---
In deze handleiding leggen we stap voor stap uit hoe u de Aspose.PDF-bibliotheek voor .NET gebruikt om het bijschrift van een keuzerondje in een PDF-formulier te definiëren. We laten u zien hoe u toegang krijgt tot het keuzerondjeveld, een nieuwe keuzerondjeoptie maakt en het bijschrift van de knop aanpast.

## Stap 1: De documentdirectory configureren

 De eerste stap is het configureren van de documentdirectory waar het PDF-formulier zich bevindt waaraan u wilt werken. U kunt de`dataDir` variabele om het pad naar de directory op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zorg ervoor dat u deze vervangt`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het PDF-bronformulier laden

 In deze stap laden we het bron-PDF-formulier met behulp van de`Aspose.Pdf.Facades.Form` klasse van Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Zorg ervoor dat het PDF-bestand met het formulier aanwezig is in de opgegeven documentenmap.

## Stap 3: Het bijschrift van de keuzerondje bewerken

We doorlopen de namen van de formuliervelden en zoeken naar radioknopvelden. Als er een overeenkomend veld wordt gevonden, maken we een nieuwe radioknopoptie met een aangepast bijschrift en voegen deze toe aan het bestaande veld.

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
// Een TextParagraph-object maken
TextParagraph par = new TextParagraph();
// Alineapositie instellen
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Geef de modus voor tekstomloop op
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Voeg het nieuwe TextFragment toe aan de alinea
par.AppendLine(updatedFragment);
// Voeg de TextParagraph toe met behulp van TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Pas indien nodig het keuzerondje voor het bijschrift en andere instellingen aan.

## Stap 4: Het resulterende PDF-bestand opslaan

 Nu we klaar zijn met het aanpassen van het bijschrift van de keuzerondje, kunnen we de resulterende PDF opslaan met behulp van de`Save` methode van de`Document` klas.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor het resulterende PDF-bestand opgeeft.

### Voorbeeldbroncode voor Set Radio Button Caption met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Bron PDF-formulier laden
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
		// Alineapositie instellen
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Geef de modus voor tekstomloop op
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Nieuw TextFragment toevoegen aan alinea
		par.AppendLine(updatedFragment);
		// Voeg de TextParagraph toe met behulp van TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusie

In deze handleiding hebben we geleerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om het bijschrift voor een keuzerondje in een PDF-formulier in te stellen. Door de beschreven stappen te volgen, kunt u de opties voor keuzerondjes aanpassen en het bijschrift naar wens wijzigen. U kunt gerust de functies van Aspose.PDF voor .NET verder verkennen om de mogelijkheden voor het manipuleren van PDF-bestanden uit te breiden.

### Veelgestelde vragen

#### V: Kan ik Aspose.PDF voor .NET gebruiken om bijschriften voor keuzerondjes in een PDF-formulier in te stellen?

A: Ja, u kunt Aspose.PDF voor .NET gebruiken om bijschriften voor keuzerondjes in een PDF-formulier in te stellen. De meegeleverde voorbeeldbroncode laat zien hoe u toegang krijgt tot het keuzerondjeveld, een nieuwe keuzerondjeoptie met een aangepast bijschrift maakt en het bestaande veld bijwerkt.

#### V: Hoe kan ik het uiterlijk van het bijschrift van de keuzerondje aanpassen, bijvoorbeeld de lettergrootte en kleur?

 A: U kunt het uiterlijk van het bijschrift van de keuzerondje aanpassen door de eigenschappen van het bijschrift aan te passen.`TextFragment` gebruikt voor het bijschrift. U kunt bijvoorbeeld het lettertype, de lettergrootte, de kleur, de regelafstand en andere tekstopmaakopties instellen.

#### V: Is het mogelijk om meerdere keuzerondjes met verschillende bijschriften toe te voegen aan één keuzerondjesgroep?

A: Ja, u kunt meerdere radioknopopties met verschillende bijschriften toevoegen aan een enkele radioknopgroep. Elke optie vertegenwoordigt een andere keuze en gebruikers kunnen slechts één optie uit de groep selecteren.

#### V: Kan ik Aspose.PDF voor .NET gebruiken om andere formuliervelden in een PDF-document te wijzigen?

A: Ja, Aspose.PDF voor .NET biedt een uitgebreide set functies om verschillende formuliervelden in een PDF-document te manipuleren, zoals tekstvelden, selectievakjes, vervolgkeuzelijsten en meer. U kunt de bibliotheek gebruiken om waarden in te stellen, uiterlijken te wijzigen en interactiviteit toe te voegen aan formuliervelden.

#### V: Ondersteunt Aspose.PDF voor .NET het werken met PDF's die uit andere bronnen zijn gegenereerd, zoals gescande documenten?

A: Ja, Aspose.PDF voor .NET ondersteunt het werken met PDF's die zijn gegenereerd uit verschillende bronnen, waaronder gescande documenten. De bibliotheek biedt OCR-mogelijkheden (Optical Character Recognition) om tekst uit gescande PDF's te halen en de inhoud programmatisch te manipuleren.