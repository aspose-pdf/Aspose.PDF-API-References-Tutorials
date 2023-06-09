---
title: Sök text och rita rektangel
linktitle: Sök text och rita rektangel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker efter text i en PDF, ritar rektanglar runt den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET.
type: docs
weight: 460
url: /sv/net/programming-with-text/search-text-and-draw-rectangle/
---

Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka efter specifik text i ett PDF-dokument, rita en rektangel runt den hittade texten och spara det ändrade dokumentet. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Byta ut`"SearchAndGetTextFromAll.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 5: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Byta ut`@"[\S]+"` med ditt önskade reguljära uttrycksmönster.

## Steg 6: Aktivera sökning i reguljära uttryck

Aktivera sökning efter reguljära uttryck genom att ställa in`TextSearchOptions` absorbatorns egenskaper:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Steg 7: Sök på alla sidor

Acceptera absorbenten för alla sidor i dokumentet:

```csharp
document.Pages.Accept(textAbsorber);
```

## Steg 8: Rita en rektangel runt den hittade texten

 Skapa en`PdfContentEditor` objekt och loop genom de hämtade textfragmenten, rita en rektangel runt varje textsegment:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Steg 9: Spara det ändrade dokumentet

Spara det ändrade dokumentet:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Se till att byta ut`"SearchTextAndDrawRectangle_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för Sök text och rita rektangel med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Skapa TextAbsorber-objekt för att hitta alla fraser som matchar det reguljära uttrycket
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter specifik text i ett PDF-dokument, ritar en rektangel runt den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att utföra de nödvändiga åtgärderna. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera text och rita rektanglar i PDF-filer.