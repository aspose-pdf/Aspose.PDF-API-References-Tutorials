---
title: Extrahera kolumntext i PDF-fil
linktitle: Extrahera kolumntext i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du extraherar kolumntext i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-text/extract-columns-text/
---
Denna handledning guidar dig genom processen att extrahera kolumntext i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill extrahera kolumntext, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Öppna PDF-dokumentet
 Öppna ett befintligt PDF-dokument med hjälp av`Document`konstruktorn och skickar sökvägen till indata-PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Steg 5: Justera teckenstorleken
Minska teckensnittsstorleken på textfragmenten med en faktor 0,7 för att förbättra läsbarheten och bättre representera kolumnär text.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Steg 6: Extrahera text från kolumner
 Spara det ändrade PDF-dokumentet i en minnesström och ladda om det som ett nytt dokument. Använd sedan`TextAbsorber` klass för att extrahera text från kolumnerna.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Steg 7: Spara den extraherade texten
Spara den extraherade texten till en textfil på den angivna sökvägen för utdatafilen.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Exempel på källkod för Extrahera kolumntext med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Måste minska teckensnittsstorleken med minst 70 %
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Slutsats
Du har framgångsrikt extraherat kolumntext från ett PDF-dokument med Aspose.PDF för .NET. Den extraherade texten har sparats i den angivna utdatafilen.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning erbjuder en steg-för-steg-guide för att extrahera kolumner med text från en PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden ger en praktisk demonstration av de nödvändiga procedurerna.

#### F: Vilka namnområden ska jag importera?

S: I kodfilen där du tänker extrahera textkolumner, inkludera följande med hjälp av direktiv i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Lokalisera linjen`string dataDir = "YOUR DOCUMENT DIRECTORY";` i koden och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur öppnar jag ett befintligt PDF-dokument?

 S: I steg 4 öppnar du ett befintligt PDF-dokument med hjälp av`Document` konstruktor och tillhandahåller sökvägen till PDF-inmatningsfilen.

#### F: Varför justeras teckensnittsstorleken?

S: Steg 5 innebär att teckensnittsstorleken på textfragment minskas med en faktor på 0,7. Denna justering förbättrar läsbarheten och representerar kolumnformad text mer exakt.

#### F: Hur extraherar jag text från kolumner?

 S: Steg 6 består av att spara det modifierade PDF-dokumentet i en minnesström, ladda om det som ett nytt dokument och sedan använda`TextAbsorber` klass för att extrahera text från kolumnerna.

#### F: Vad är syftet med att spara den extraherade texten?

S: I steg 7 sparar du den extraherade texten till en textfil på den angivna sökvägen för utdatafilen.

#### F: Varför minska teckenstorleken innan extrahering?

S: Att minska teckenstorleken hjälper till att säkerställa att den extraherade texten justeras ordentligt i kolumnerna, vilket ger en mer exakt representation av den ursprungliga layouten.

#### F: Vad är nyckeln till den här handledningen?

S: Genom att följa denna handledning har du skaffat dig de kunskaper och färdigheter som behövs för att extrahera kolumner med text från ett PDF-dokument med Aspose.PDF för .NET. Den resulterande texten har sparats i den angivna utdatafilen.