---
title: Rotera text med hjälp av textstycke och Builder
linktitle: Rotera text med hjälp av textstycke och Builder
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du roterar text med hjälp av textstycke och builder i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 410
url: /sv/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

Denna handledning förklarar hur man använder Aspose.PDF för .NET för att rotera text med hjälp av textstycken och byggare. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Steg 3: Skapa PDF-dokumentet

 Initiera`Document` objekt för att skapa ett nytt PDF-dokument:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Lägg till en sida

 Hämta en viss sida från dokumentet med hjälp av`Pages.Add()` metod:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Steg 5: Skapa och rotera textstycken

 Skapa en`for` loop för att generera flera textstycken med olika rotationer:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Justera positions- och rotationsvärdena enligt dina krav.

## Steg 6: Skapa och konfigurera textfragment

 Skapa flera`TextFragment`objekt, ställ in deras text och egenskaper:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

Justera texten och andra egenskaper efter önskemål.

## Steg 7: Lägg till textfragment till stycket

 Lägg till de skapade textfragmenten till stycket med hjälp av`AppendLine` metod:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Steg 8: Skapa en TextBuilder och lägg till stycket

 Skapa en`TextBuilder` objekt med hjälp av`pdfPage` och lägg till textstycket till PDF-sidan:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Steg 9: Spara PDF-dokumentet

 Spara det ändrade PDF-dokumentet till en fil med hjälp av`Save` metod:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Se till att byta ut`"TextFragmentTests_Rotated4_out.pdf"` med önskat utdatafilnamn.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du roterar text med hjälp av textstycken och byggare i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att skapa dokumentet till att spara den modifierade versionen. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera textrotation i PDF-filer.

### Exempel på källkod för rotera text med hjälp av textstycke och byggare med Aspose.PDF för .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initiera dokumentobjekt
Document pdfDocument = new Document();
// Skaffa en speciell sida
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Ange rotation
	paragraph.Rotation = i * 90 + 45;
	// Skapa textfragment
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Skapa textfragment
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Skapa textfragment
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Ställ in textegenskaper
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Skapa textfragment
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Ställ in textegenskaper
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Skapa TextBuilder-objekt
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Lägg till textfragmentet till PDF-sidan
	textBuilder.AppendParagraph(paragraph);
}
// Spara dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```