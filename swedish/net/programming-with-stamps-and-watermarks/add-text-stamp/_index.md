---
title: Lägg till textstämpel
linktitle: Lägg till textstämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en textstämpel till dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
I den här handledningen tar vi dig steg för steg om hur du lägger till en textstämpel till ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en anpassad textstämpel på en specifik sida i PDF-dokumentet.

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
// Lägg till textbuffert på specifik sida
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
