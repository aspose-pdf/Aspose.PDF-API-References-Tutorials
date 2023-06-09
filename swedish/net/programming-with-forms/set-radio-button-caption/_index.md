---
title: Ställ in radioknappstext
linktitle: Ställ in radioknappstext
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att ställa in bildtexten för en alternativknapp i en PDF-form.
type: docs
weight: 280
url: /sv/net/programming-with-forms/set-radio-button-caption/
---

I den här guiden kommer vi att förklara steg för steg hur du använder Aspose.PDF-biblioteket för .NET för att definiera rubriken för en alternativknapp i en PDF-form. Vi visar dig hur du kommer åt alternativknappsfältet, skapar ett nytt alternativknappsalternativ och anpassar knapptexten.

## Steg 1: Konfigurera dokumentkatalogen

 Det första steget är att konfigurera dokumentkatalogen där PDF-formuläret du vill arbeta med finns. Du kan använda`dataDir`variabel för att ange katalogsökvägen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Laddar käll-PDF-formuläret

 I det här steget kommer vi att ladda käll-PDF-formuläret med hjälp av`Aspose.Pdf.Facades.Form`klass av Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Se till att PDF-filen som innehåller formuläret finns i den angivna dokumentkatalogen.

## Steg 3: Redigera alternativknapptexten

Vi går igenom formulärfältens namn och söker efter alternativknappsfält. Om ett matchande fält hittas skapar vi ett nytt alternativ med en anpassad bildtext och lägger till det i det befintliga fältet.

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
// Skapa ett TextParagraph-objekt
TextParagraph par = new TextParagraph();
// Ställ in styckeposition
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Ange radbrytningsläge
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Lägg till det nya TextFragmentet i stycket
par.AppendLine(updatedFragment);
// Lägg till TextParagraph med TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Anpassa alternativknappen för bildtexten och andra inställningar efter behov.

## Steg 4: Spara den resulterande PDF-filen

 Nu när vi är klara med att ändra alternativknappstexten kan vi spara den resulterande PDF-filen med hjälp av`Save` metod för`Document` klass.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Var noga med att ange den fullständiga sökvägen och filnamnet för den resulterande PDF-filen.

### Exempel på källkod för Set Radio Button Caption med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda käll-PDF-formulär
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
		// Skapa TextParagraph-objekt
		TextParagraph par = new TextParagraph();
		// Ställ in styckeposition
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Ange radbrytningsläge
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Lägg till nytt textfragment till stycket
		par.AppendLine(updatedFragment);
		// Lägg till TextParagraph med TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Slutsats

den här guiden lärde vi oss hur man använder Aspose.PDF-biblioteket för .NET för att ställa in bildtexten för en alternativknapp i en PDF-form. Genom att följa de beskrivna stegen kan du anpassa alternativen för alternativknapparna och ändra bildtexten efter behov. Utforska gärna funktionerna i Aspose.PDF för .NET ytterligare för att utöka möjligheterna att manipulera PDF-filer.