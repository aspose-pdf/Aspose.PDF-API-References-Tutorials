---
title: Lägg till datum Tidstämpel i PDF-fil
linktitle: Lägg till datum Tidstämpel i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en datum- och tidsstämpel i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
den här artikeln tar vi dig steg för steg om hur du lägger till en datum- och tidsstämpel i PDF-fil med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en datum- och tidsstämpel till en befintlig PDF-fil.

## Krav

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 1: Sätta upp miljön

Innan du kan lägga till en datum- och tidsstämpel i ett PDF-dokument måste du konfigurera din utvecklingsmiljö. Här är stegen att följa:

1. Öppna din favorit-IDE (Integrated Development Environment).
2. Skapa ett nytt C#-projekt.
3. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET.

## Steg 2: Lägga till Aspose.PDF-biblioteket

Aspose.PDF-biblioteket för .NET krävs för att arbeta med PDF-dokument i ditt projekt.

## Steg 3: Laddar PDF-dokumentet

Det första steget för att lägga till en datum- och tidsstämpel är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 4: Skapa datum- och tidsstämpel

Nu när du har laddat upp dokumentet

  PDF kan du skapa datum- och tidsstämpeln att lägga till. Så här gör du:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Skapa en textbuffert
TextStamp textStamp = new TextStamp(annotationText);
```

Koden ovan skapar en ny textbuffert som innehåller aktuellt datum och tid.

## Steg 5: Konfigurera stämpelegenskaper

Innan du lägger till stämpeln i PDF-dokumentet kan du konfigurera olika egenskaper för stämpeln, såsom marginal, horisontell och vertikal justering, etc. Så här gör du:

```csharp
// Ställ in buffertegenskaper
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Du kan anpassa dessa egenskaper efter dina behov.

## Steg 6: Lägg till stämpel till PDF

Nu när datum- och tidsstämpeln är klar kan du lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till frimärket i sidans frimärkssamling
pdfDocument.Pages[1].AddStamp(textStamp);
```

Koden ovan lägger till stämpeln på första sidan i PDF-dokumentet. Du kan ange en annan sida om det behövs.

## Steg 7: Spara utdatadokumentet

När du har lagt till datum- och tidsstämpeln kan du spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Lägg till datum och tidsstämpel med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Skapa textstämpel
TextStamp textStamp = new TextStamp(annotationText);

// Ställ in egenskaper för stämpeln
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Lägger till stämpel på frimärkssamling
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en datum- och tidsstämpel med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap på dina egna projekt för att lägga till datum- och tidsstämplar till PDF-dokument.

### Vanliga frågor för att lägga till datum och tidsstämpel i PDF-fil

#### F: Vad är syftet med att lägga till en datum- och tidsstämpel i ett PDF-dokument med Aspose.PDF för .NET?

S: Att lägga till en datum- och tidsstämpel i ett PDF-dokument ökar dess informationsvärde genom att ange när dokumentet ändrades eller skapades. Den här funktionen är användbar för att spåra dokumentändringar och tillhandahålla en referenspunkt för dokumenthistorik.

#### F: Kan jag anpassa formatet på datum- och tidsstämpeln för att matcha specifika krav?

 S: Ja, du kan anpassa formatet för datum- och tidsstämpeln enligt dina önskemål. Den medföljande C#-källkoden använder`DateTime.Now.ToString()` metod för att generera tidsstämpeln i ett specifikt format. Du kan ändra den här koden för att formatera tidsstämpeln efter behov.

#### F: Är det möjligt att lägga till datum och tidsstämpel på en specifik plats på en PDF-sida?

 S: Absolut, du kan justera placeringen av datum- och tidsstämpeln på PDF-sidan genom att ändra egenskaperna för`TextStamp` objekt. Koden som tillhandahålls i handledningen visar hur man ställer in egenskaper som marginal, justering och vertikal positionering.

#### F: Kan jag lägga till flera datum- och tidsstämplar på olika sidor i samma PDF-dokument?

 S: Ja, du kan lägga till flera datum- och tidsstämplar på olika sidor i samma PDF-dokument. Upprepa helt enkelt processen att skapa en`TextStamp` objekt och konfigurera dess egenskaper för varje önskad sida.

#### F: Hur kan jag ändra teckensnitt, storlek eller färg på datum- och tidsstämpeltexten?

 S: För att ändra teckensnitt, storlek eller färg på datum- och tidsstämpeltexten kan du anpassa egenskaperna för`DefaultAppearance` objekt som används för att skapa`TextStamp`. Justera teckensnittsnamn, storlek och färgvärden för att uppnå önskat utseende.

#### F: Är det möjligt att lägga till andra typer av anteckningar eller stämplar till ett PDF-dokument med Aspose.PDF för .NET?

S: Ja, Aspose.PDF för .NET tillhandahåller ett brett utbud av anteckningstyper som du kan lägga till i PDF-dokument, inklusive textkommentarer, stämplar, linjer, former och mer. Du kan utforska Aspose.PDF-dokumentationen för ytterligare information om hur du arbetar med anteckningar.

#### F: Finns det några begränsningar eller överväganden när du lägger till en datum- och tidsstämpel i ett PDF-dokument?

S: Även om det är enkelt att lägga till en datum- och tidsstämpel, överväg faktorer som dokumentets layout och befintligt innehåll. Se till att stämpelns placering inte skymmer viktig information eller påverkar dokumentets läsbarhet.

#### F: Hur kan jag integrera den här metoden i mina egna projekt för att lägga till datum- och tidsstämplar i PDF-dokument?

S: För att integrera denna metod, följ de medföljande stegen och justera koden så att den passar ditt projekts struktur. Du kan lägga till datum- och tidsstämplar i befintliga PDF-dokument för att förbättra deras användbarhet och ge en tydlig tidslinje för ändringar.

#### F: Kan jag automatisera processen att lägga till datum- och tidsstämplar i flera PDF-dokument?

S: Ja, du kan automatisera processen att lägga till datum- och tidsstämplar till flera PDF-dokument genom att skapa ett skript eller program som itererar genom en lista med dokument och tillämpar samma stämplingsprocess på var och en.