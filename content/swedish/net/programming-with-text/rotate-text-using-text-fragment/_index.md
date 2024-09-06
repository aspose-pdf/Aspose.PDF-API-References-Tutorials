---
title: Rotera text med textfragment i PDF-fil
linktitle: Rotera text med textfragment i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du roterar text med textfragment i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 390
url: /sv/net/programming-with-text/rotate-text-using-text-fragment/
---
Denna handledning förklarar hur man använder Aspose.PDF för .NET för att rotera text med hjälp av textfragment i PDF-fil. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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

## Steg 5: Skapa textfragment

 Skapa flera`TextFragment` objekt, ställ in deras text och egenskaper och ange deras positioner på sidan:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Justera texten, positionerna och andra egenskaper efter önskemål.

## Steg 6: Skapa en TextBuilder och lägg till textfragment

 Skapa en`TextBuilder` objekt med hjälp av`pdfPage` och lägg till textfragmenten på PDF-sidan:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Steg 7: Spara PDF-dokumentet

 Spara det ändrade PDF-dokumentet till en fil med hjälp av`Save` metod:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Se till att byta ut`"TextFragmentTests_Rotated1_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för Rotate Text Using Text Fragment med Aspose.PDF för .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initiera dokumentobjekt
Document pdfDocument = new Document();
// Skaffa en speciell sida
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Skapa textfragment
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Ställ in textegenskaper
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Skapa ett roterat textfragment
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Ställ in textegenskaper
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Skapa ett roterat textfragment
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Ställ in textegenskaper
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// skapa TextBuilder-objekt
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Lägg till textfragmentet till PDF-sidan
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Spara dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du roterar text med hjälp av textfragment i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att skapa dokumentet till att spara den modifierade versionen. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera textrotation i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Rotera text med hjälp av textfragment"?

S: Handledningen "Rotera text med hjälp av textfragment" syftar till att guida dig genom processen att använda Aspose.PDF-biblioteket för .NET för att rotera text med hjälp av textfragment i ett PDF-dokument. Handledningen innehåller steg-för-steg-instruktioner och exempelkod för att uppnå denna funktionalitet.

#### F: Vad menas med "roterande text med hjälp av textfragment"?

S: Att rotera text med hjälp av textfragment hänvisar till möjligheten att tillämpa rotation på enskilda textfragment i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket. Denna teknik låter dig styra orienteringen av text i olika vinklar eller positioner i PDF-innehållet.

#### F: Varför skulle jag vilja rotera textfragment i ett PDF-dokument?

S: Att rotera textfragment i ett PDF-dokument kan vara användbart för olika ändamål, som att betona specifikt innehåll, skapa konstnärliga mönster eller förbättra layout och läsbarhet.

#### F: Hur ställer jag in projektet för handledningen?

S: Så här ställer du in projektet:

1. Skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE).
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.
3. Lägg till de nödvändiga direktiven till din C#-fil.

#### F: Hur skapar jag ett nytt PDF-dokument?

 S: För att skapa ett nytt PDF-dokument, initiera ett`Document`objekt från Aspose.PDF-biblioteket. Du kan använda det här objektet för att lägga till sidor och innehåll till PDF:en.

#### F: Hur roterar jag textfragment med hjälp av textfragment?

S: Så här roterar du textfragment med textfragment:

1.  Skapa`TextFragment` föremål.
2. Ställ in text och egenskaper för textfragmenten.
3. Ange positionerna för textfragmenten på sidan.
4.  Ställ in rotationsvinkeln med hjälp av`TextState.Rotation` egenskapen hos textfragmenten.
5.  Skapa en`TextBuilder`objekt och lägg till textfragmenten på PDF-sidan.

#### F: Kan jag använda olika rotationsvinklar på olika textfragment?

 A: Ja, du kan använda olika rotationsvinklar på olika`TextFragment` föremål. Varje textfragment kan ha sin egen rotationsvinkel specificerad med hjälp av`TextState.Rotation` egendom.

#### F: Hur sparar jag PDF-dokumentet med roterade textfragment?

 S: För att spara PDF-dokumentet med roterade textfragment, använd`Save` metod för`Document` objekt och ange önskad sökväg och namn för utdatafilen.