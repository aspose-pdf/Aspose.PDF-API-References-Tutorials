---
title: Text i sidfot av PDF-fil
linktitle: Text i sidfot av PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig att lägga till text i sidfoten i PDF-filen med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-stamps-and-watermarks/text-in-footer/
---
I den här handledningen kommer vi att lära oss hur du lägger till text i sidfoten i PDF-filen med Aspose.PDF för .NET. Följ stegen nedan:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa sidfotstext

Skapa en ny textstämpel med texten du vill lägga till i sidfoten:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Du kan anpassa texten genom att ändra dess egenskaper som bottenmarginal, horisontell justering och vertikal justering.

## Steg 5: Lägg till sidfotstext på alla sidor

Gå igenom alla sidor i PDF-dokumentet och lägg till textstämpeln i sidfoten:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Steg 6: Spara PDF-dokumentet

När sidfoten har lagts till på alla sidor, spara det uppdaterade PDF-dokumentet:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

### Exempel på källkod för Textin Footer med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Skapa sidfot
TextStamp textStamp = new TextStamp("Footer Text");

// Ställ in egenskaper för stämpeln
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Lägg till sidfot på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Spara uppdaterad PDF-fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till text i sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina sidfötter genom att lägga till ytterligare text i dina PDF-dokument.

### Vanliga frågor för text i sidfoten i PDF-filen

#### F: Vad är syftet med att lägga till text i sidfoten i ett PDF-dokument?

S: Genom att lägga till text i sidfoten i ett PDF-dokument kan du inkludera viktig information, såsom upphovsrättsmeddelanden, sidnummer, dokumentversion eller annan text som du vill ska visas konsekvent längst ned på varje sida.

#### F: Hur gör den medföljande C#-källkoden tillägg av text i sidfoten i ett PDF-dokument?

S: Koden demonstrerar processen att öppna ett befintligt PDF-dokument, skapa en textstämpel med önskad sidfotstext, anpassa textegenskaperna, lägga till textstämpeln på alla sidor och slutligen spara det uppdaterade PDF-dokumentet med den tillagda sidfotstexten.

#### F: Kan jag ändra utseendet på sidfotstexten, såsom teckensnitt, storlek, färg och justering?

 S: Ja, du kan anpassa utseendet på sidfotstexten genom att ändra egenskaperna för`TextStamp` objekt. Kodexemplet inkluderar inställningsegenskaper som bottenmarginal, horisontell justering och vertikal justering. Du kan också justera teckensnitt, storlek, färg och andra textrelaterade egenskaper.

#### F: Är det möjligt att lägga till olika texter i sidfoten på varje sida?

 S: Ja, du kan lägga till olika texter i sidfoten på varje sida genom att skapa separata`TextStamp` objekt med olika textinnehåll eller egenskaper och sedan lägga till dem på specifika sidor efter behov.

#### F: Hur säkerställer jag att sidfoten visas konsekvent på varje sida i PDF-dokumentet?

S: Genom att använda en slinga som itererar genom alla sidor i PDF-dokumentet och lägga till samma textstämpel på varje sida säkerställer du att sidfoten visas konsekvent på varje sida.

#### F: Kan jag lägga till flera rader text eller formatera sidfotstexten med radbrytningar?

 S: Ja, du kan lägga till flera rader text i sidfoten genom att inkludera radbrytningar i textsträngen. Du kan till exempel använda flyktsekvensen`\n` för att indikera en radbrytning i texten.

#### F: Vad händer om jag vill lägga till olika innehåll i sidhuvudet och sidfoten i samma PDF-dokument?

S: För att lägga till olika innehåll i sidhuvuds- och sidfotssektionerna, skulle du följa liknande steg för båda sektionerna. Koden visar hur man lägger till text i sidfoten; du kan använda ett liknande tillvägagångssätt för att lägga till text i rubriken.

#### F: Är det möjligt att lägga till bilder eller andra element vid sidan av sidfotstexten med detta tillvägagångssätt?

S: Även om den medföljande koden specifikt demonstrerar att lägga till text i sidfoten, kan du utöka tillvägagångssättet för att lägga till andra element som bilder, linjer, former eller annat innehåll till sidfotssektionen med hjälp av biblioteket Aspose.PDF.