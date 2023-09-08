---
title: Lägg till textstämpel i PDF-fil
linktitle: Lägg till textstämpel i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en textstämpel i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
I den här handledningen tar vi dig steg för steg om hur du lägger till en textstämpel i PDF-fil med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en anpassad textstämpel på en specifik sida i PDF-filen.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa textbufferten

Nu när du har laddat upp PDF-dokumentet kan du skapa textstämpeln att lägga till. Så här gör du:

```csharp
// Skapa textbufferten
TextStamp textStamp = new TextStamp("Example Stamp");
```

Koden ovan skapar en ny textbuffert som innehåller den angivna texten.

## Steg 4: Konfigurera textstämpelegenskaper

Innan du lägger till textstämpeln i PDF-dokumentet kan du konfigurera olika egenskaper för stämpeln, såsom bakgrund, position, rotation, teckensnitt, storlek, etc. Så här gör du:

```csharp
// Konfigurera egenskaper för textbuffert
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Du kan anpassa dessa egenskaper efter dina behov.

## Steg 5: Lägg till textstämpel till PDF

Nu när textstämpeln är klar kan du lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
//Lägg till textbuffert på specifik sida
pdfDocument.Pages[1].AddStamp(textStamp);
```

Koden ovan lägger till textstämpeln på första sidan i PDF-dokumentet. Du kan ange en annan sida om det behövs.

## Steg 6: Spara utdatadokumentet

När du har lagt till textstämpeln kan du spara det redigerade PDF-dokumentet. Här är hur:

```csharp
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

Koden ovan sparar det modifierade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Lägg till textstämpel med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Skapa textstämpel
TextStamp textStamp = new TextStamp("Sample Stamp");

// Ställ in om stämpeln är bakgrund
textStamp.Background = true;

// Ange ursprung
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Rotera stämpeln
textStamp.Rotate = Rotation.on90;

// Ställ in textegenskaper
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Lägg till stämpel på en viss sida
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en textstämpel med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap på dina egna projekt för att lägga till anpassade textstämplar till PDF-dokument.

### Vanliga frågor för att lägga till textstämpel i PDF-fil

#### F: Vad är syftet med att lägga till en textstämpel i en PDF-fil med Aspose.PDF för .NET?

S: Genom att lägga till en textstämpel kan du placera anpassad text på en specifik sida i ett PDF-dokument. Den här funktionen är användbar för att lägga till etiketter, kommentarer, vattenstämplar eller annan textinformation för att förbättra dokumentets innehåll och ge ytterligare sammanhang.

#### F: Kan jag anpassa utseendet på textstämpeln, som typsnitt, storlek, färg och rotation?

 S: Ja, du kan helt anpassa utseendet på textstämpeln. Den medföljande C#-källkoden visar hur man ställer in olika egenskaper för`TextStamp` objekt, inklusive teckensnitt, teckenstorlek, teckensnitt, textfärg, bakgrundsfärg och rotation.

#### F: Är det möjligt att lägga till flera textstämplar på olika sidor i samma PDF-dokument?

S: Absolut, du kan lägga till flera textstämplar på olika sidor i samma PDF-dokument. Handledningens tillhandahållna kod låter dig ange målsidan för att lägga till textstämpeln, vilket gör den mångsidig för olika sidor i dokumentet.

#### F: Hur anger jag positionen för textstämpeln i PDF-dokumentet?

 S: Du kan anpassa positionen för textstämpeln genom att ändra`XIndent` och`YIndent` egenskaper hos`TextStamp` objekt. Dessa egenskaper definierar koordinaterna för frimärkets övre vänstra hörn i förhållande till sidans ursprung.

#### F: Kan jag använda den här metoden på befintliga PDF-dokument för att lägga till textstämplar?

S: Ja, du kan använda den här metoden på befintliga PDF-dokument för att lägga till textstämplar. Handledningens medföljande kod visar hur man laddar ett befintligt PDF-dokument och lägger till en textstämpel på en specifik sida.

#### F: Kan jag lägga till både bakgrunds- och förgrundsfärger till textstämpeln?

 S: Ja, du kan lägga till både bakgrunds- och förgrundsfärger till textstämpeln. Genom att ställa in`Background` egendom till`true` , kan du tillhandahålla en färgad bakgrund för textstämpeln. Dessutom kan du ställa in`TextState.ForegroundColor` egenskap för att ange färgen på själva texten.

#### F: Hur kan jag säkerställa att textstämpeln inte skymmer det underliggande innehållet i PDF-dokumentet?

 S: När du lägger till en textstämpel, var uppmärksam på dess placering för att säkerställa att den inte hindrar viktig information eller negativt påverkar dokumentets läsbarhet. Du kan justera`XIndent` och`YIndent` egenskaper för att placera textstämpeln på rätt sätt.

#### F: Kan jag använda den här metoden för att lägga till andra stämplar än text, som bilder eller logotyper?

S: Denna specifika handledning fokuserar på att lägga till textstämplar, men du kan på liknande sätt lägga till andra typer av stämplar, såsom bilder eller logotyper, med Aspose.PDF för .NET. Processen involverar att skapa lämpligt stämpelobjekt och konfigurera dess egenskaper.

#### F: Hur kan jag automatisera processen att lägga till textstämplar till flera PDF-dokument?

S: Du kan automatisera processen att lägga till textstämplar till flera PDF-dokument genom att skapa ett skript eller program som itererar genom en lista med dokument och tillämpar samma textstämplingsprocess på var och en.