---
title: Stiltabellrad
linktitle: Stiltabellrad
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du formaterar tabellrader i en PDF med Aspose.PDF för .NET med en steg-för-steg-guide för att förbättra din dokumentformatering med lätthet.
type: docs
weight: 180
url: /sv/net/programming-with-tagged-pdf/style-table-row/
---
## Introduktion

När det gäller att skapa välstrukturerade och vackert formaterade PDF-dokument är Aspose.PDF för .NET en god lösning. Oavsett om du automatiserar rapporter, fakturor eller skapar dynamiska tabeller, är formatering av tabeller med olika stilar nyckeln till ett snyggt dokument. I den här handledningen kommer vi att dyka djupt in i att utforma en tabellrad med Aspose.PDF för .NET. Och oroa dig inte, jag guidar dig steg-för-steg, precis som ett gott samtal över kaffe!

## Förutsättningar

Innan vi hoppar in i det roliga, låt oss se till att du har alla dina ankor på rad. Du behöver:

1. Aspose.PDF för .NET Library  
    Om du inte redan har det kan du hämta det från[här](https://releases.aspose.com/pdf/net/) . Du kan också få en[gratis provperiod](https://releases.aspose.com/) för att komma igång.
2. Utvecklingsmiljö  
   Konfigurera Visual Studio eller valfri C# IDE. Du behöver också .NET installerat, men jag antar att du redan är bekant med det.
3. Grundläggande kunskaper i C# och .NET  
   En god förståelse för C# kommer att göra den här handledningen till en lek. Men oroa dig inte, jag kommer att förklara varje steg i detalj!

## Importera paket

Innan vi kan börja arbeta med Aspose.PDF måste vi importera de nödvändiga namnrymden. Se till att du inkluderar följande i ditt C#-projekt:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dessa är viktiga för att skapa och utforma tabellen, och naturligtvis för att arbeta med taggat innehåll för efterlevnad.

Låt oss nu dela upp uppgiften steg för steg, så att du kan styla dina tabellrader som ett proffs!

## Steg 1: Skapa ett nytt PDF-dokument

Först och främst: låt oss skapa ett helt nytt PDF-dokument. Detta dokument kommer att innehålla alla formaterade tabellrader.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa dokument
Document document = new Document();
```

 Här initierar vi helt enkelt en ny`Document` objekt som kommer att representera vår PDF-fil. Se till att ställa in katalogsökvägen där du ska spara dina utdatafiler.

## Steg 2: Arbeta med taggat innehåll

För att strukturera din PDF för tillgänglighet arbetar vi med taggat innehåll. Detta hjälper till att skapa strukturerade element som tabeller, vilket säkerställer att de är kompatibla med tillgänglighetsstandarder som PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Här ställer vi in titeln och språket för PDF:s taggade innehåll. Det är som att ge din PDF ett namn och tala om för den vilket språk den ska tala!

## Steg 3: Definiera tabellstrukturen

Låt oss sedan definiera strukturen för tabellen vi ska skapa. Varje tabell behöver ett sidhuvud, en brödtext och en sidfot – ungefär som ett välorganiserat blogginlägg!

```csharp
// Få rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;

// Skapa tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Det vi gör här är att skapa en tabell med en rubrik (`THead`), kropp (`TBody`), och sidfot (`TFoot`). Dessa element kommer att hålla våra rader.

## Steg 4: Lägg till tabellrubrikraden

Tabeller utan rubriker är som böcker utan titlar. Låt oss skapa rubrikraden först för att ge kontext för data.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Här går vi igenom och lägger till tre rubrikceller (`TableTHElement`), vilket ger var och en en beskrivande text. Enkelt, eller hur?

## Steg 5: Lägg till stilade kroppsrader

Nu kommer det roliga – styling av raderna! Låt oss skapa sju rader med anpassade stilar. Vi ställer in bakgrundsfärger, ramar, stoppning och textjustering.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Bakgrundsfärg: Vi använde en ljus guldröd gul för den professionella men ändå varma touchen.
- Kanter: Varje rad får en mörkgrå yttre kant och blå cellkanter för en skarp look.
- Höjd och stoppning: Radhöjderna är inställda och stoppning läggs till för ett rent utseende.
- Sidbrytningar: För att göra tabellen mer läsbar börjar varannan rad på en ny sida.

## Steg 6: Lägg till sidfotsraden

I likhet med sidhuvudet förankrar sidfoten bordet. Låt oss skapa en.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Vi går helt enkelt igenom tre sidfotsceller och lägger till lite text. Den alternativa texten för sidfoten är "Foot Row" för att göra den tillgänglig.

## Steg 7: Spara PDF-dokumentet

Nu när bordet är klart är det dags att rädda ditt mästerverk!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Precis så sparas din PDF med alla vackra tabellrader som vi just stylat.

## Steg 8: Validera PDF/UA-efterlevnad

För att säkerställa att vår PDF följer tillgänglighetsstandarder kommer vi att validera den för PDF/UA-kompatibilitet.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Detta säkerställer att din PDF uppfyller PDF/UA-standarden, vilket gör den tillgänglig för alla. Tillgänglighet är namnet på spelet!

## Slutsats

Och där har du det! Med bara några rader kod har du skapat en fullständigt utformad tabell i en PDF med Aspose.PDF för .NET. Från sidhuvuden till sidfötter, vi har formaterat varje rad, lagt till tillgänglighetselement och till och med validerat dokumentet för överensstämmelse. Oavsett om du arbetar med företagsrapporter, presentationer eller bara har roligt med PDF-filer, har den här guiden dig täckt. Nu, fortsätt och börja styla dina bord som ett proffs!

## FAQ's

### Kan jag ändra tabellens teckensnittsstil också?  
 Ja! Du kan ändra teckensnittsstilen med hjälp av`TextState` objekt för varje cell, vilket möjliggör fullständig anpassning.

### Hur lägger jag till fler kolumner i min tabell?  
 Justera bara`colCount`variabel och lägg till fler celler i slingorna för sidhuvuden, brödtext och sidfötter.

### Vad händer om jag inte ställer in radhöjden?  
Om du inte ställer in radhöjden justeras tabellen automatiskt baserat på innehållet.

### Kan jag använda detta för ett dynamiskt antal rader?  
Absolut! Du kan hämta data från en databas eller någon annan källa och dynamiskt justera rad- och kolumnantal.

### Är Aspose.PDF för .NET gratis att använda?  
 Aspose.PDF för .NET är en licensierad produkt, men du kan prova den med en[gratis provperiod](https://releases.aspose.com/) eller skaffa en[tillfällig licens](https://purchase.aspose.com/temporary-license/).