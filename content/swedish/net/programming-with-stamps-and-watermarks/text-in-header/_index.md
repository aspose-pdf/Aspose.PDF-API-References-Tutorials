---
title: Text i rubriken på PDF-filen
linktitle: Text i rubriken på PDF-filen
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till text i rubriken på PDF-filen med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-stamps-and-watermarks/text-in-header/
---
I den här handledningen ska vi lära oss hur du lägger till text i rubriken på PDF-filen med Aspose.PDF för .NET. Följ stegen nedan:

## Steg 1: Projektförberedelser

Se till att du har installerat Aspose.PDF för .NET och skapat ett C#-projekt.

## Steg 2: Importera namnutrymmen

Lägg till följande namnområden till din C#-källfil:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Öppna dokumentet

Öppna det befintliga PDF-dokumentet med den angivna sökvägen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa rubriktext

Skapa en ny textstämpel med texten du vill lägga till i rubriken:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Du kan anpassa texten genom att ändra dess egenskaper som toppmarginal, horisontell justering och vertikal justering.

## Steg 5: Lägg till rubriktext på alla sidor

Gå igenom alla sidor i PDF-dokumentet och lägg till textstämpeln i rubriken:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Steg 6: Spara PDF-dokumentet

När rubriktexten har lagts till på alla sidor, spara det uppdaterade PDF-dokumentet:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

### Exempel på källkod för Textin Header med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Skapa rubrik
TextStamp textStamp = new TextStamp("Header Text");

// Ställ in egenskaper för stämpeln
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Lägg till rubrik på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Spara uppdaterat dokument
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till text i rubriken på ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina rubriker genom att lägga till ytterligare text i dina PDF-dokument.

### Vanliga frågor för text i rubriken på PDF-filen

#### F: Vad är syftet med att lägga till text i rubriken på ett PDF-dokument?

S: Genom att lägga till text i rubriken på ett PDF-dokument kan du inkludera viktig information, såsom titlar, dokumentnamn, datum eller annan text som du vill ska visas konsekvent överst på varje sida.

#### F: Hur uppnår den medföljande C#-källkoden tillägg av text i rubriken på ett PDF-dokument?

S: Koden demonstrerar processen att öppna ett befintligt PDF-dokument, skapa en textstämpel med önskad rubriktext, anpassa textegenskaperna, lägga till textstämpeln på alla sidor och slutligen spara det uppdaterade PDF-dokumentet med den tillagda rubriktexten.

#### F: Kan jag ändra utseendet på rubriktexten, såsom teckensnitt, storlek, färg och justering?

 S: Ja, du kan anpassa utseendet på rubriktexten genom att ändra egenskaperna för`TextStamp`objekt. Kodexemplet inkluderar inställningsegenskaper som toppmarginal, horisontell justering och vertikal justering. Du kan också justera teckensnitt, storlek, färg och andra textrelaterade egenskaper.

#### F: Är det möjligt att lägga till olika text i varje sidas rubrik?

 S: Ja, du kan lägga till olika text i varje sidas rubrik genom att skapa separata`TextStamp` objekt med olika textinnehåll eller egenskaper och sedan lägga till dem på specifika sidor efter behov.

#### F: Hur säkerställer jag att rubriktexten visas konsekvent på varje sida i PDF-dokumentet?

S: Genom att använda en slinga som itererar genom alla sidor i PDF-dokumentet och lägga till samma textstämpel på varje sida, säkerställer du att rubriktexten visas konsekvent på varje sida.

#### F: Kan jag lägga till flera rader text eller formatera rubriktexten med radbrytningar?

 S: Ja, du kan lägga till flera rader text i rubriken genom att inkludera radbrytningar i textsträngen. Du kan till exempel använda flyktsekvensen`\n` för att indikera en radbrytning i texten.

#### F: Vad händer om jag vill lägga till olika innehåll i sidhuvudet och sidfoten i samma PDF-dokument?

S: För att lägga till olika innehåll i sidhuvuds- och sidfotssektionerna, skulle du följa liknande steg för båda sektionerna. Koden visar hur man lägger till text i rubriken; du kan använda en liknande metod för att lägga till text i sidfoten.

#### F: Är det möjligt att lägga till bilder eller andra element vid sidan av rubriktexten med detta tillvägagångssätt?

S: Även om den medföljande koden specifikt visar att du lägger till text i rubriken, kan du utöka tillvägagångssättet för att lägga till andra element som bilder, linjer, former eller annat innehåll till rubriksektionen med hjälp av Aspose.PDF-biblioteket.
