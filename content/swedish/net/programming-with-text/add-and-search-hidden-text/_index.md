---
title: Lägg till och sök dold text i PDF-fil
linktitle: Lägg till och sök dold text i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att lägga till och söka i dold text i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-text/add-and-search-hidden-text/
---
I den här handledningen går vi igenom hur du lägger till och söker efter dold text i PDF-fil med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## 1. Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella hemsida.

## 2. Skapa PDF-dokumentet med dold text

För att komma igång, använd följande kod för att skapa ett nytt PDF-dokument som innehåller dold text:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Skapa ett dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Ställ in textegenskap - osynlig
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Var noga med att ange önskad sökväg och filnamn för PDF-dokumentet.

## 3. Sök efter text i dokumentet

Därefter kommer vi att söka i den dolda texten i PDF-dokumentet. Använd följande kod:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Gör något med fragmenten
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Detta kommer att söka i den dolda texten på den andra sidan av PDF-dokumentet och visa relevant information.

### Exempel på källkod för Lägg till och sök gömd text med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Skapa dokument med dold text
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Ställ in textegenskap - osynlig
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Sök efter text i dokumentet
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Gör något med fragment
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Slutsats

Grattis! Du har framgångsrikt lagt till och hittat dold text i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att manipulera och söka i dold text i PDF-filer.

### FAQ's

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett robust bibliotek som ger utvecklare möjlighet att skapa, manipulera och transformera PDF-dokument i .NET-applikationer.

#### F: Kan dold text användas för vattenmärkningsändamål?

A: Absolut! Dold text kan fungera som ett effektivt sätt att vattenmärka PDF-dokument och lägga till ett extra lager av säkerhet.

#### F: Är det möjligt att avslöja dold text i ett PDF-dokument?

S: Ja, processen att söka och avslöja dold text i ett PDF-dokument kan utföras med de tekniker som beskrivs i denna handledning.

#### F: Vilka andra funktioner erbjuder Aspose.PDF för .NET?

S: Utöver manipulering av dold text erbjuder Aspose.PDF för .NET ett brett utbud av funktioner, inklusive PDF-generering, konvertering, kryptering och mer.