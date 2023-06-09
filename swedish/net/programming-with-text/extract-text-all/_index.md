---
title: Extrahera text alla
linktitle: Extrahera text alla
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar all text från ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-text/extract-text-all/
---

Denna handledning guidar dig genom processen att extrahera all text från ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

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

## Steg 5: Extrahera all text
 Skapa en`TextAbsorber` objekt för att extrahera text från dokumentet. Acceptera sedan absorbenten för alla sidor.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Steg 6: Hämta den extraherade texten
 Få åtkomst till den extraherade texten från`TextAbsorber` objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Steg 7: Spara den extraherade texten
 Skapa en`TextWriter` och öppna filen där du vill spara den extraherade texten. Skriv den extraherade texten till filen och stäng strömmen.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exempel på källkod för extrahera text Alla med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Skapa TextAbsorber-objekt för att extrahera text
TextAbsorber textAbsorber = new TextAbsorber();
// Acceptera absorbenten för alla sidor
pdfDocument.Pages.Accept(textAbsorber);
// Hämta den extraherade texten
string extractedText = textAbsorber.Text;
// Skapa en författare och öppna filen
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Skriv en textrad till filen
tw.WriteLine(extractedText);
// Stäng strömmen
tw.Close();
```

## Slutsats
Du har framgångsrikt extraherat all text från ett PDF-dokument med Aspose.PDF för .NET. Den extraherade texten har sparats i den angivna utdatafilen.