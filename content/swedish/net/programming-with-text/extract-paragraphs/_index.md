---
title: Extrahera stycken i PDF-fil
linktitle: Extrahera stycken i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar stycken i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 160
url: /sv/net/programming-with-text/extract-paragraphs/
---
Denna handledning guidar dig genom processen att extrahera stycken i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill extrahera stycken, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Öppna PDF-dokumentet
 Öppna ett befintligt PDF-dokument med hjälp av`Document`konstruktorn och skickar sökvägen till indata-PDF-filen.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 5: Extrahera stycken
 Instantiera`ParagraphAbsorber` klass och använd dess`Visit` metod för att extrahera stycken från dokumentet.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Steg 6: Iterera genom stycken
Gå igenom de extraherade styckena för att komma åt textinnehållet. Använd kapslade loopar för att gå igenom avsnitt och linjer inom varje stycke.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Exempel på källkod för extrahera stycken med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Öppna en befintlig PDF-fil
Document doc = new Document(dataDir + "input.pdf");
// Instantiera ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Slutsats
Du har framgångsrikt extraherat stycken från ett PDF-dokument med Aspose.PDF för .NET. De extraherade styckena har visats i konsolfönstret.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att extrahera stycken från en PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden ger praktiska steg för att uppnå denna uppgift.

#### F: Vilka namnområden ska jag importera?

S: I kodfilen där du tänker extrahera stycken, inkludera följande med hjälp av direktiv i början av filen:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Lokalisera linjen`string dataDir = "YOUR DOCUMENT DIRECTORY";` i koden och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur öppnar jag ett befintligt PDF-dokument?

 S: I steg 4 öppnar du ett befintligt PDF-dokument med hjälp av`Document` konstruktor och tillhandahåller sökvägen till PDF-inmatningsfilen.

#### F: Hur extraherar jag stycken från dokumentet?

 S: Steg 5 innebär att skapa en instans av`ParagraphAbsorber` klass och använda dess`Visit` metod för att extrahera stycken från PDF-dokumentet.

#### F: Hur upprepar jag de extraherade styckena?

S: Steg 6 guidar dig genom att gå igenom de extraherade styckena. Kapslade slingor används för att korsa sektioner och linjer inom varje stycke, för att i slutändan komma åt och visa textinnehållet.

#### F: Vad är nyckeln till den här handledningen?

S: Genom att följa denna handledning har du lärt dig hur du extraherar stycken från ett PDF-dokument med Aspose.PDF för .NET. De extraherade styckena har visats i konsolfönstret, vilket ger dig värdefull inblick i dokumentets innehållsstruktur.