---
title: Göm sidnummer i innehållsförteckningen
linktitle: Göm sidnummer i innehållsförteckningen
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du döljer sidnummer i innehållsförteckningen med Aspose.PDF för .NET. Följ den här detaljerade guiden med kodexempel för att skapa professionella PDF-filer.
type: docs
weight: 220
url: /sv/net/programming-with-document/hidepagenumbersintoc/
---
## Introduktion

När du arbetar med PDF-filer kanske du ibland vill skapa en innehållsförteckning (TOC) men hålla det snyggt genom att dölja sidnumren. Kanske flyter dokumentet bättre utan dem, eller så är det ett estetiskt val. Oavsett din anledning, om du arbetar med Aspose.PDF för .NET, kommer denna handledning att visa dig exakt hur du döljer sidnummer i din innehållsförteckning.

## Förutsättningar

Innan vi sätter igång finns det några saker du behöver på plats. Här är en snabb checklista:

- Visual Studio installerad: Du behöver en fungerande version av Visual Studio för att koda med.
- Aspose.PDF för .NET Library: Se till att du har installerat Aspose.PDF för .NET-biblioteket.
  -  Ladda ner länk:[Aspose.PDF för .NET](https://releases.aspose.com/pdf/net/)
- Tillfällig licens: Om du testar funktionerna är det bra att ha en tillfällig licens.
  -  Tillfällig licens:[Skaffa det här](https://purchase.aspose.com/temporary-license/)

## Importera paket

Innan du hoppar in i koden, se till att du importerar följande namnrymder i ditt C#-projekt. Dessa kommer att tillhandahålla de nödvändiga klasserna och metoderna för att arbeta med PDF-dokument och skapa din innehållsförteckning (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Nu när din miljö är klar och paket har importerats, låt oss dela upp varje steg i processen. Vi kommer att täcka varje del av koden för att säkerställa tydlighet, så att du enkelt kan följa med.

## Steg 1: Initiera ditt PDF-dokument

Det första vi behöver göra är att skapa ett nytt PDF-dokument och lägga till en sida för innehållsförteckningen (TOC).


```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Detta är katalogen där din utdatafil kommer att sparas.
- Document(): Initierar ett nytt PDF-dokument.
- Pages.Add(): Lägger till en ny tom sida i dokumentet, som senare kommer att hålla din innehållsförteckning.

## Steg 2: Ställ in TOC-information och titel

Därefter kommer vi att definiera innehållsförteckningen information, inklusive inställning av titeln som kommer att visas överst i innehållsförteckningen.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Detta objekt innehåller all information om innehållsförteckningen.
- TextFragment: Representerar texten i TOC-titeln, här anger vi den som "Innehållsförteckning."
- FontStyle: Vi stilar TOC-titeln genom att ställa in storleken på 20 och göra den fet.
- tocPage.TocInfo: Vi tilldelar innehållsförteckningen information till sidan som kommer att visa innehållsförteckningen.

## Steg 3: Göm sidnummer i innehållsförteckningen

Nu till det roliga! Det är här vi konfigurerar innehållsförteckningen för att dölja sidnumren.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Detta är den magiska omkopplaren som döljer sidnumren. Ställ in den på`false`, och sidnumren visas inte i innehållsförteckningen.
- FormatArrayLength: Vi ställer in detta till 4, vilket indikerar att vi vill definiera formatering för fyra nivåer av TOC-rubriker.

## Steg 4: Anpassa TOC-formatering

För att lägga till mer stil till din innehållsförteckning kommer vi nu att definiera formatering för olika nivåer av rubriker.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Denna array styr formateringen av TOC-poster. Varje index representerar en annan rubriknivå.
- Marginal och textstil: Vi ställer in marginaler och använder teckensnittsstilar som fetstil, kursiv och understruken för varje rubriknivå.

## Steg 5: Lägg till rubriker i dokumentet

Slutligen, låt oss lägga till de faktiska rubrikerna som kommer att vara en del av innehållsförteckningen.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Rubrik och textsegment: Dessa representerar rubrikerna som kommer att visas i din innehållsförteckning. Varje nivå får sin egen rubrik.
- IsAutoSequence: Numrerar rubrikerna automatiskt.
- IsInList: Säkerställer att varje rubrik visas i innehållsförteckningen.

## Steg 6: Spara dokumentet

När allt är klart sparar du PDF-dokumentet till din angivna utdatafil.

```csharp
doc.Save(outFile);
```

Och det är det! Du har framgångsrikt skapat en PDF med en innehållsförteckning och sidnumren är dolda!

## Slutsats

Att skapa en innehållsförteckning i en PDF och dölja sidnummer kan verka knepigt, men med Aspose.PDF för .NET är det enkelt. Genom att följa den här steg-för-steg-guiden har du lärt dig hur du anpassar TOC-formatet, döljer sidnummer och använder olika stilar på dina rubriker. Nu kan du skapa professionella PDF-filer skräddarsydda efter dina exakta behov.

## FAQ's

### Kan jag visa sidnummer för specifika rubriker i innehållsförteckningen?
Nej, Aspose.PDF döljer eller visar sidnummer för hela innehållsförteckningen. Du kan inte selektivt dölja dem för specifika poster.

### Är det möjligt att lägga till fler nivåer i innehållsförteckningen?
 Ja, du kan öka`FormatArrayLength` för att definiera fler nivåer av TOC-rubriker.

### Hur kan jag ändra teckensnittet för alla innehållsförteckningsposter?
 Du kan ändra teckensnittet genom att ändra`TextState.Font` egendom för varje nivå i`FormatArray`.

### Kan jag infoga hyperlänkar i innehållsförteckningen?
 Ja, du kan länka varje innehållsförteckningspost till ett specifikt avsnitt i dokumentet med hjälp av`Heading.TocPage` egendom.

### Behöver jag en licens för Aspose.PDF?
Ja, en giltig licens krävs för produktionsanvändning. Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för att testa funktionerna.