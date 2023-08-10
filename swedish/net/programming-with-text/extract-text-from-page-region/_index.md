---
title: Extrahera text från sidregion
linktitle: Extrahera text från sidregion
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar text från en specifik region på en sida i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-text/extract-text-from-page-region/
---

Denna handledning guidar dig genom processen att extrahera text från en specifik region på en sida i ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

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
 Skapa en`TextAbsorber`objekt för att extrahera text från dokumentet. Konfigurera`TextSearchOptions` för att begränsa sökningen till en specifik sidregion definierad av en rektangel.

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
// Skapa en skribent och öppna filen
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Skriv en textrad till filen
tw.WriteLine(extractedText);
// Stäng strömmen
tw.Close();
```

## Slutsats
Du har framgångsrikt extraherat text från en specifik region på en sida i ett PDF-dokument med Aspose.PDF för .NET. Den extraherade texten har sparats i den angivna utdatafilen.