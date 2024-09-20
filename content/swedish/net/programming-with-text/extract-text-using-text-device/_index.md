---
title: Extrahera text med hjälp av textenhet
linktitle: Extrahera text med hjälp av textenhet
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar text från ett PDF-dokument med hjälp av textenheten i Aspose.PDF för .NET.
type: docs
weight: 210
url: /sv/net/programming-with-text/extract-text-using-text-device/
---
## Introduktion

Att extrahera text från en PDF-fil kan vara svårt, särskilt när det gäller dokument som har olika format, inbäddade typsnitt eller komplexa layouter. Men med Aspose.PDF för .NET blir denna process en bris! Oavsett om du vill konvertera sidor i en PDF till vanlig text för vidare analys eller helt enkelt behöver extrahera specifika avsnitt, har Aspose.PDF dig täckt. I den här handledningen kommer vi att bryta ner steg-för-steg hur man extraherar text från en PDF med klassen TextDevice i Aspose.PDF. Vi kommer också att tillhandahålla tydliga förklaringar, så att du enkelt kan tillämpa samma metoder på dina egna projekt.

## Förutsättningar

Innan vi hoppar in i koden, se till att du har allt på plats för att följa med. Här är vad du behöver:

1.  Aspose.PDF för .NET: Ladda ner den senaste versionen från[Aspose.PDF för .NET nedladdningssida](https://releases.aspose.com/pdf/net/).
2. Utvecklingsmiljö: Visual Studio eller någon annan C#-utvecklingsmiljö.
3. .NET Framework: Se till att ditt projekt är inriktat på .NET Framework 4.x eller högre.
4. Inmatning av PDF-fil: En PDF-fil som du ska använda för textextraktion. Placera detta i en katalog på din maskin (vi kommer att hänvisa till detta som`YOUR DOCUMENT DIRECTORY`).

## Importera paket

Överst i koden måste du importera de nödvändiga namnrymden för att arbeta med Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Steg 1: Ladda ditt PDF-dokument

 Innan vi extraherar text måste vi ladda PDF-dokumentet i minnet. I det här steget öppnar du din PDF-fil med Aspose.PDF-filer`Document` klass. Detta ger dig tillgång till alla sidor och innehåll i filen.

```csharp
// Definiera sökvägen till ditt PDF-dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda PDF-dokumentet
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Här, vi använder`Document pdfDocument = new Document(dataDir + "input.pdf");` för att ladda PDF:en. De`dataDir` variabeln innehåller katalogsökvägen till din PDF-fil. Detta ger oss tillgång till hela dokumentet, vilket gör att vi kan gå igenom sidor och extrahera innehåll.

## Steg 2: Konfigurera en strängbyggare för textlagring

 Nu när dokumentet är laddat behöver vi ett sätt att lagra den extraherade texten. För detta kommer vi att använda en`StringBuilder` vilket möjliggör effektiv strängsammansättning.

```csharp
// StringBuilder för att hålla den extraherade texten
StringBuilder builder = new StringBuilder();
```

 Vi initierar en`StringBuilder`instans, som samlar in text som extraherats från varje sida. Det är ett mer effektivt sätt att hantera stora strängar jämfört med vanlig strängsammansättning i en slinga.

## Steg 3: Gå igenom PDF-sidor

 Därefter går vi igenom varje sida i PDF-dokumentet för att extrahera texten. Vi kommer att behandla varje sida individuellt med hjälp av`TextDevice` klass, som ansvarar för att konvertera PDF-innehållet till textformat.

```csharp
// Bläddra igenom alla sidor i PDF:en
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Bearbeta varje sida för textextraktion
}
```

Denna loop går igenom varje sida i PDF-filen (`pdfDocument.Pages` ). För varje sida kommer vi att extrahera texten och lägga till den i vår`StringBuilder`.

## Steg 4: Extrahera text från varje sida

 Nu ställer vi in textextraktionsprocessen för varje sida. Här skapar vi en`TextDevice` objekt och använd det för att bearbeta PDF-sidorna. De`TextDevice` extraherar rå eller formaterad text baserat på de extraheringsalternativ vi ställer in.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Skapa en textenhet för textextraktion
    TextDevice textDevice = new TextDevice();
    
    // Ställ in textextraktionsalternativ på "Rent" läge
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Extrahera text från den aktuella sidan och spara den i minnesströmmen
    textDevice.Process(pdfPage, textStream);

    // Konvertera minnesström till text
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Lägg till den extraherade texten till StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : Den`TextDevice` klass används för att extrahera text från PDF:en.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Detta alternativ extraherar den råa texten utan att behålla någon formatering som typsnitt eller positioner. Du kan också använda`TextFormattingMode.Raw` om du behöver mer kontroll över formateringen.
- `textDevice.Process(pdfPage, textStream);` : Detta bearbetar varje sida i PDF:en och lagrar den extraherade texten i en`MemoryStream`.
-  Slutligen konverterar vi texten från`MemoryStream` till en sträng och lägg till den i`StringBuilder`.

## Steg 5: Spara extraherad text till en fil

 Efter bearbetning av alla sidor lagras texten i`StringBuilder`. Det sista steget är att spara denna extraherade text till en fil.

```csharp
// Definiera utdatasökvägen för textfilen
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Spara den extraherade texten till en fil
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Detta skriver hela innehållet i`StringBuilder` till en textfil.
- Sökvägen för utdatafilen ställs in genom att lägga till ett filnamn (`"input_Text_Extracted_out.txt"` ) till`dataDir` väg.

## Slutsats

Att extrahera text från en PDF med Aspose.PDF för .NET är en enkel och effektiv process. Genom att följa stegen som beskrivs i den här guiden kan du enkelt öppna PDF-dokument, gå igenom sidor och extrahera text till en textfil. Detta är särskilt användbart för att bearbeta stora volymer PDF-data, utföra textanalys eller konvertera dokument för ytterligare manipulation.

Med Aspose.PDF är du inte begränsad till textextraktion – du kan hantera kommentarer, manipulera bilder eller till och med konvertera PDF-filer till andra format som HTML eller Word. Flexibiliteten och kraften i detta bibliotek gör det till ett ovärderligt verktyg för PDF-hantering i .NET-applikationer.

## FAQ's

### Kan Aspose.PDF extrahera text från bildbaserade PDF-filer?
Nej, Aspose.PDF är utformad för att extrahera text från innehållsbaserade PDF-filer. För bildbaserade PDF-filer behövs OCR-teknik.

### Behåller Aspose.PDF formatering när text extraheras?
Som standard extraheras texten utan formatering, men du kan justera extraheringsalternativ om du vill behålla en viss formatering.

### Kan jag extrahera text från ett specifikt sidintervall?
Ja, du kan ändra koden så att den går över ett visst intervall av sidor istället för alla sidor.

### Vilka är textextraktionslägena i Aspose.PDF?
Aspose.PDF tillhandahåller två lägen: Raw och Pure. Råläge försöker behålla den ursprungliga layouten, medan Pure-läget endast extraherar texten utan formatering.

### Är Aspose.PDF för .NET kompatibelt med .NET Core?
Ja, Aspose.PDF för .NET är helt kompatibelt med .NET Core och .NET Framework.