---
title: Extrahera text från sidregion i PDF-fil
linktitle: Extrahera text från sidregion i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du extraherar text från en specifik region på en sida i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-text/extract-text-from-page-region/
---
Denna handledning guidar dig genom processen att extrahera text från en specifik region på en sida i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill extrahera text, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Öppna PDF-dokumentet
 Öppna ett befintligt PDF-dokument med hjälp av`Document` konstruktorn och skickar sökvägen till indata-PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Steg 5: Extrahera text från en sidregion
 Skapa en`TextAbsorber` objekt för att extrahera text från dokumentet. Konfigurera`TextSearchOptions` för att begränsa sökningen till en specifik sidregion definierad av en rektangel.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Steg 6: Hämta den extraherade texten
 Få åtkomst till den extraherade texten från`TextAbsorber` objekt.

```csharp
string extractedText = absorb.Text;
```

## Steg 7: Spara den extraherade texten
 Skapa en`TextWriter` och öppna filen där du vill spara den extraherade texten. Skriv den extraherade texten till filen och stäng strömmen.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exempel på källkod för att extrahera text från sidregion med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Skapa TextAbsorber-objekt för att extrahera text
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Acceptera absorbenten för första sidan
pdfDocument.Pages[1].Accept(absorber);
// Hämta den extraherade texten
string extractedText = absorber.Text;
// Skapa en författare och öppna filen
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Skriv en textrad till filen
tw.WriteLine(extractedText);
// Stäng strömmen
tw.Close();
```

## Slutsats
Du har framgångsrikt extraherat text från en specifik region på en sida i ett PDF-dokument med Aspose.PDF för .NET. Den extraherade texten har sparats i den angivna utdatafilen.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att extrahera text från en specifik region på en sida i en PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden ger steg-för-steg-instruktioner för att utföra denna uppgift.

#### F: Vilka namnområden ska jag importera?

S: I kodfilen där du tänker extrahera text, inkludera följande med hjälp av direktiv i början av filen:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Lokalisera linjen`string dataDir = "YOUR DOCUMENT DIRECTORY";` i koden och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur öppnar jag ett befintligt PDF-dokument?

 S: I steg 4 öppnar du ett befintligt PDF-dokument med hjälp av`Document` konstruktor och tillhandahåller sökvägen till PDF-inmatningsfilen.

#### F: Hur extraherar jag text från en specifik sidregion?

 S: Steg 5 innebär att skapa en`TextAbsorber`objekt för att extrahera text från PDF-dokumentet. Du kommer sedan att konfigurera`TextSearchOptions` för att definiera ett specifikt rektangulärt område på sidan med hjälp av koordinater.

#### F: Hur kommer jag åt den extraherade texten?

 S: Steg 6 guidar dig genom att komma åt den extraherade texten från`TextAbsorber` objekt.

#### F: Hur sparar jag den extraherade texten till en fil?

 S: I steg 7 skapar du en`TextWriter`, öppna filen där du vill spara den extraherade texten, skriv den extraherade texten till filen och stäng sedan strömmen.

#### F: Vad är nyckeln till den här handledningen?

S: Genom att följa denna handledning har du lärt dig hur du extraherar text från en specifik region på en sida i ett PDF-dokument med Aspose.PDF för .NET. Den extraherade texten har sparats i en specificerad utdatafil, så att du kan rikta in och analysera det önskade textinnehållet exakt.