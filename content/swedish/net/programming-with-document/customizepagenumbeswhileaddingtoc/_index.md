---
title: Anpassa sidnummer medan du lägger till innehållsförteckning
linktitle: Anpassa sidnummer medan du lägger till innehållsförteckning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du anpassar sidnummer samtidigt som du lägger till en innehållsförteckning till dina PDF-dokument med Aspose.PDF för .NET i denna omfattande handledning.
type: docs
weight: 100
url: /sv/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Introduktion

dokumenthanteringens värld är PDF-filer enastående. De är det bästa formatet för att dela och bevara dokument på olika plattformar. Men vad händer när du vill förbättra dina PDF-dokument med funktioner som en innehållsförteckning (TOC)? Det är där Aspose.PDF för .NET kommer in i bilden! Detta kraftfulla bibliotek tillåter utvecklare att manipulera PDF-filer med lätthet, vilket gör det möjligt för dem att lägga till, ändra och anpassa innehåll utan ansträngning. I den här handledningen kommer vi att dyka in i hur du anpassar sidnummer samtidigt som du lägger till en innehållsförteckning till dina PDF-dokument med Aspose.PDF för .NET. Så ta tag i din kodningshatt och låt oss komma igång!

## Förutsättningar

Innan vi går in i koden finns det några saker du måste ha på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på din dator. Det här blir vår utvecklingsmiljö.
2. Aspose.PDF för .NET: Du måste ladda ner och installera Aspose.PDF-biblioteket. Du kan hitta den[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper i C#: Bekantskap med C#-programmering hjälper dig att förstå kodavsnitten bättre.
4. Ett exempel på PDF-fil: Ha ett exempel på en PDF-fil redo som vi kan arbeta med. Du kan skapa en enkel eller ladda ner en befintlig PDF.

## Importera paket

För att komma igång måste vi importera de nödvändiga paketen. Öppna ditt Visual Studio-projekt och lägg till en referens till Aspose.PDF-biblioteket. Du kan göra detta genom att använda NuGet Package Manager:

1. Högerklicka på ditt projekt i Solution Explorer.
2. Välj "Hantera NuGet-paket."
3. Sök efter "Aspose.PDF" och installera den.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

När du har installerat biblioteket kan du börja koda!

## Steg 1: Konfigurera din dokumentkatalog

Först och främst måste vi ställa in vår dokumentkatalog. Det är här vi kommer att lagra våra in- och utdata PDF-filer. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

 det här utdraget, ersätt`YOUR DOCUMENT DIRECTORY` med den faktiska sökvägen där dina PDF-filer finns. Detta hjälper oss att ladda den befintliga PDF-filen och spara den modifierade versionen.

## Steg 2: Ladda den befintliga PDF-filen

Nu när vi har ställt in vår dokumentkatalog, låt oss ladda den befintliga PDF-filen. 

```csharp
Document doc = new Document(inFile);
```

 Här skapar vi en ny`Document` objekt genom att skicka ingångsfilens sökväg. Detta gör att vi kan manipulera PDF-innehållet programmatiskt.

## Steg 3: Infoga en ny sida för innehållsförteckningen

Därefter måste vi skapa en ny sida i vår PDF där innehållsförteckningen kommer att finnas.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Denna rad infogar en ny sida i början av dokumentet. TOC kommer att visas på denna sida.

## Steg 4: Skapa innehållsförteckningsinformation

Låt oss nu skapa ett objekt för att representera TOC-informationen.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 I detta steg skapar vi en`TocInfo` objekt och ställ in dess titel till "Innehållsförteckning". Vi anpassar även teckenstorlek och stil. De`PageNumbersPrefix` är satt till "P", vilket kommer att prefixa sidnumren i innehållsförteckningen.

## Steg 5: Lägg till rubriker i innehållsförteckningen

Nu kommer det roliga! Vi går igenom sidorna i dokumentet och lägger till rubriker i vår innehållsförteckning.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 I denna loop skapar vi en ny`Heading` objekt för varje sida. Vi ställer in målsidan för varje rubrik och anger texten som ska visas, vilket är "Sida X" där X är sidnumret. Slutligen lägger vi till rubriken på TOC-sidan.

## Steg 6: Spara det uppdaterade dokumentet

Efter att ha lagt till alla nödvändiga rubriker är det dags att spara vårt uppdaterade dokument.

```csharp
doc.Save(outFile);
```

Den här raden sparar den ändrade PDF-filen med innehållsförteckningen inkluderad. Du kan nu öppna utdatafilen och se din anpassade innehållsförteckning!

## Slutsats

Och där har du det! Du har framgångsrikt anpassat sidnummer samtidigt som du lagt till en innehållsförteckning till ditt PDF-dokument med Aspose.PDF för .NET. Detta kraftfulla bibliotek gör det enkelt att manipulera PDF-filer, och med bara några rader kod kan du förbättra dina dokument avsevärt. Oavsett om du skapar rapporter, e-böcker eller någon annan typ av PDF kan en innehållsförteckning förbättra navigeringen avsevärt för dina läsare. Så vad väntar du på? Dyk in i Aspose.PDF och börja skapa fantastiska PDF-filer idag!

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument programmatiskt.

### Kan jag använda Aspose.PDF gratis?
 Ja, Aspose erbjuder en gratis testversion som du kan använda för att utforska bibliotekets funktioner. Du kan ladda ner den[här](https://releases.aspose.com/).

### Hur får jag support för Aspose.PDF?
 Du kan få support genom att besöka Aspose-forumet[här](https://forum.aspose.com/c/pdf/10).

### Finns det en tillfällig licens?
 Ja, du kan begära en tillfällig licens för Aspose.PDF[här](https://purchase.aspose.com/temporary-license/).

### Var kan jag köpa Aspose.PDF för .NET?
 Du kan köpa Aspose.PDF för .NET[här](https://purchase.aspose.com/buy).