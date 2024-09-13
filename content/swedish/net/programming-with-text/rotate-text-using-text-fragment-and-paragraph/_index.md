---
title: Rotera text med hjälp av textfragment och stycke
linktitle: Rotera text med hjälp av textfragment och stycke
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du roterar text med textfragment och stycke i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 400
url: /sv/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Denna handledning förklarar hur man använder Aspose.PDF för .NET för att rotera text med hjälp av textfragment och stycke. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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

## Steg 5: Skapa textfragment

 Skapa flera`TextFragment` objekt, ställ in deras text och egenskaper och ange rotationsvinkeln:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Justera texten, rotationsvinkeln och andra egenskaper efter önskemål.

## Steg 6: Lägg till textfragment på sidan

 Lägg till de skapade textfragmenten på sidan genom att lägga till dem i`Paragraphs` samling:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Steg 7: Spara PDF-dokumentet

 Spara det ändrade PDF-dokumentet till en fil med hjälp av`Save` metod:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Se till att byta ut`"TextFragmentTests_Rotated3_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för Rotera text med hjälp av textfragment och stycke med Aspose.PDF för .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initiera dokumentobjekt
Document pdfDocument = new Document();
// Skaffa en speciell sida
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Skapa textfragment
TextFragment textFragment1 = new TextFragment("main text");
// Ställ in textegenskaper
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Skapa textfragment
TextFragment textFragment2 = new TextFragment("rotated text");
// Ställ in textegenskaper
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ställ in rotation
textFragment2.TextState.Rotation = 315;
// Skapa textfragment
TextFragment textFragment3 = new TextFragment("rotated text");
// Ställ in textegenskaper
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ställ in rotation
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Spara dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du roterar text med hjälp av textfragment och stycken i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att skapa dokumentet till att spara den modifierade versionen. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera textrotation i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Rotera text med hjälp av textfragment och stycke"?

S: Handledningen "Rotera text med hjälp av textfragment och stycke" syftar till att guida dig genom processen att använda Aspose.PDF-biblioteket för .NET för att rotera text med både textfragment och stycken i ett PDF-dokument. Handledningen innehåller steg-för-steg-instruktioner och exempelkod för att uppnå denna funktionalitet.

#### F: Hur skiljer sig denna handledning från de tidigare handledningarna för textrotation?

S: Denna handledning kombinerar användningen av textfragment och stycken för att uppnå textrotation i ett PDF-dokument. Den visar hur man roterar textfragment individuellt och sedan lägger till dem på en sidas`Paragraphs` samling för att uppnå en mer omfattande textrotationseffekt.

#### F: Vilka är fördelarna med att använda textfragment och stycken för textrotering?

S: Att använda textfragment och stycken tillsammans ger större flexibilitet vid textrotation. Textfragment möjliggör individuella rotations- och formateringsinställningar, medan stycken ger struktur för att ordna och placera textfragment på en sida.

#### F: Kan jag använda olika rotationsvinklar på olika textfragment inom samma stycke?

 A: Ja, du kan använda olika rotationsvinklar på olika`TextFragment` föremål inom samma stycke. Varje textfragment kan ha sin egen rotationsvinkel specificerad med hjälp av`TextState.Rotation` egendom.

#### F: Är det möjligt att uppnå komplexa textrotationseffekter med den här metoden?

S: Ja, genom att kombinera textfragment med olika rotationsvinklar och ordna dem i stycken kan du uppnå komplexa och anpassade textrotationseffekter, vilket förstärker dina PDF-dokuments visuella tilltalande.

#### F: Vilka steg är involverade i att rotera text med hjälp av textfragment och stycken?

S: Stegen inkluderar:

1. Konfigurera projektet genom att skapa ett nytt C#-projekt och lägga till en referens till Aspose.PDF för .NET-biblioteket.
2. Skapa PDF-dokumentet och lägga till en sida.
3. Skapa textfragment, ställa in deras egenskaper och ange rotationsvinklar.
4.  Lägga till textfragment på sidan med hjälp av`Paragraphs` samling.
5. Sparar det ändrade PDF-dokumentet.

#### F: Kan jag använda rotation på hela stycken?

 S: Ja, du kan använda rotation på hela stycken genom att ställa in`TextState.Rotation` styckets egendom. Detta kommer att rotera alla textfragment i det stycket.