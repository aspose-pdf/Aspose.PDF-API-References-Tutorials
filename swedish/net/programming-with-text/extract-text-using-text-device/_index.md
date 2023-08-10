---
title: Extrahera text med hjälp av textenhet
linktitle: Extrahera text med hjälp av textenhet
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar text från ett PDF-dokument med hjälp av textenheten i Aspose.PDF för .NET.
type: docs
weight: 210
url: /sv/net/programming-with-text/extract-text-using-text-device/
---

Denna handledning guidar dig genom processen att extrahera text från ett PDF-dokument med hjälp av textenheten i Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Öppna PDF-dokumentet
 Öppna ett befintligt PDF-dokument med hjälp av`Document` konstruktorn och skickar sökvägen till indata-PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Steg 5: Extrahera text med hjälp av Text Device
 Skapa en`StringBuilder` objekt för att hålla den extraherade texten. Iterera igenom varje sida i dokumentet och använd en`TextDevice` för att extrahera texten från varje sida.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Steg 6: Spara den extraherade texten
 Ange utdatafilens sökväg och spara den extraherade texten till en textfil med hjälp av`File.WriteAllText` metod.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Exempel på källkod för att extrahera text med hjälp av textenhet med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// Sträng för att hålla extraherad text
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Skapa textenhet
		TextDevice textDevice = new TextDevice();
		//Ställ in textextraktionsalternativ - ställ in textextraktionsläge (Raw eller Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konvertera en viss sida och spara text i strömmen
		textDevice.Process(pdfPage, textStream);
		// Konvertera en viss sida och spara text i strömmen
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Stäng minnesströmmen
		textStream.Close();
		// Få text från minnesströmmen
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Spara den extraherade texten i en textfil
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Slutsats
Du har extraherat text från ett PDF-dokument med hjälp av textenheten i Aspose.PDF för .NET. Den extraherade texten har sparats i den angivna utdatafilen.