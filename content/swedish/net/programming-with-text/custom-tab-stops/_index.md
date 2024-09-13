---
title: Anpassade flikstopp i PDF-fil
linktitle: Anpassade flikstopp i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar anpassade tabbstopp i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-text/custom-tab-stops/
---

Denna handledning guidar dig genom processen att skapa anpassade tabbstopp i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
kodfilen där du vill skapa anpassade tabbstopp, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa en ny dokumentinstans
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document _pdfdocument = new Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Steg 6: Skapa anpassade tabbstopp
 Skapa en`TabStops` objekt och lägg till anpassade tabbstopp till det. Ställ in inriktningstyp och ledartyp för varje tabbstopp.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Steg 7: Skapa textfragment med tabbstopp
 Skapa`TextFragment` objekt och skicka de anpassade tabbstoppen till dem. Använd specialtecknen`#$TAB` för att indikera tabbstopp i texten.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Steg 8: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för Custom Tab Stops med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Slutsats
Du har skapat ett PDF-dokument med anpassade tabbstopp med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.

### FAQ's

#### F: Vad är fokus för denna handledning?

S: Den här handledningen är inriktad på att guida dig genom processen att skapa anpassade tabbstopp i en PDF-fil med Aspose.PDF för .NET-biblioteket. Den medföljande C#-källkoden visar de nödvändiga stegen för att uppnå detta.

#### F: Vilka namnområden ska jag importera för den här handledningen?

S: I kodfilen där du vill skapa anpassade tabbstopp, importera följande namnområden i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Hitta raden i koden`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur skapar jag en ny dokumentinstans?

 S: I steg 4 kommer du att instansiera en ny`Document` objekt med den medföljande koden.

#### F: Hur lägger jag till en sida i dokumentet?

 S: I steg 5 lägger du till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling.

#### F: Hur skapar jag anpassade tabbstopp?

 S: I steg 6 skapar du en`TabStops` objekt och lägg till anpassade tabbstopp till det. Du kommer också att ställa in justering och ledartyper för varje tabbstopp.

#### F: Hur skapar jag textfragment med tabbstopp?

 S: I steg 7 skapar du`TextFragment` objekt och skicka de anpassade tabbstoppen till dem. Du kommer att använda specialtecknen`#$TAB` för att indikera tabbstopp i texten.

#### F: Hur sparar jag PDF-dokumentet?

 S: I steg 8 sparar du PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

#### F: Vad är det viktigaste med den här handledningen?

S: Genom att följa den här handledningen har du lärt dig hur du skapar ett PDF-dokument med anpassade tabbstopp med Aspose.PDF för .NET. Detta kan vara användbart för att organisera och anpassa text på ett strukturerat sätt.