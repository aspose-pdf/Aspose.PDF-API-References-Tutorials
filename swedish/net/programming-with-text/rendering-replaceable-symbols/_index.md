---
title: Återgivning av utbytbara symboler
linktitle: Återgivning av utbytbara symboler
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du renderar utbytbara symboler i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 310
url: /sv/net/programming-with-text/rendering-replaceable-symbols/
---

den här handledningen kommer vi att förklara hur man renderar utbytbara symboler i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att skapa en PDF, lägga till ett textfragment med nyradsmarkörer, ställa in textegenskaper, placera texten och spara PDF:en med den medföljande C#-källkoden.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där du vill spara den genererade PDF-filen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till din önskade katalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett PDF-dokument och en sida

 Därefter skapar vi ett nytt PDF-dokument och lägger till en sida till det med hjälp av`Document` klass och`Page` klass från Aspose.PDF-biblioteket.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Steg 3: Lägg till textfragment med Newline Markers

 Vi skapar en`TextFragment` objekt och ställ in dess text så att den inkluderar nyradsmarkörer (`Environment.NewLine`) för att representera flera textrader.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Steg 4: Ställ in egenskaper för textfragment

Vi kan ställa in olika egenskaper för textfragmentet om så önskas, såsom teckenstorlek, teckensnitt, bakgrundsfärg och förgrundsfärg.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Steg 5: Skapa textstycke och position

 Vi skapar en`TextParagraph` objekt, lägg till textfragmentet till stycket och ställ in styckets position på sidan.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Steg 6: Lägg till textstycke på sidan

 Vi skapar en`TextBuilder`objekt med sidan och lägg till textstycket i textbyggaren.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Steg 7: Spara PDF-dokumentet

Slutligen sparar vi PDF-dokumentet till den angivna utdatafilen.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Exempel på källkod för att rendera utbytbara symboler med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initiera nytt TextFragment med text som innehåller obligatoriska nyradsmarkörer
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Ställ in egenskaper för textfragment om det behövs
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Skapa TextParagraph-objekt
TextParagraph par = new TextParagraph();
// Lägg till nytt textfragment till stycket
par.AppendLine(textFragment);
// Ställ in styckeposition
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Skapa TextBuilder-objekt
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Lägg till TextParagraph med TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen har du lärt dig hur du renderar utbytbara symboler i ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa den steg-för-steg-guide och köra den medföljande C#-koden kan du skapa en PDF, lägga till text med nyradsmarkörer, ställa in textegenskaper, placera texten på sidan och spara PDF:en.