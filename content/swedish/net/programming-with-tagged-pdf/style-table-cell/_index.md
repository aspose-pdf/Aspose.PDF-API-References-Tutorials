---
title: Stiltabellcell
linktitle: Stiltabellcell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du formaterar tabellceller i en PDF med Aspose.PDF för .NET med denna detaljerade handledning. Följ instruktionerna för att skapa och formatera vackra PDF-tabeller.
type: docs
weight: 160
url: /sv/net/programming-with-tagged-pdf/style-table-cell/
---
## Introduktion

Att skapa professionella PDF-tabeller kan vara svårt, men med Aspose.PDF för .NET är det förvånansvärt enkelt! Oavsett om du utformar sidhuvuden, sidfötter eller specifika tabellceller, ger detta kraftfulla bibliotek dig alla verktyg du behöver för att skapa vackert formaterade PDF-dokument. I den här handledningen går vi igenom hur man formaterar tabellceller i ett PDF-dokument med Aspose.PDF för .NET. Oroa dig inte – vi delar upp allt i steg som är lätta att följa.

## Förutsättningar

Innan du dyker in i koden, se till att du har följande förutsättningar:

1. Aspose.PDF för .NET: Ladda ner och installera den senaste versionen av Aspose.PDF från[här](https://releases.aspose.com/pdf/net/).
2. IDE (som Visual Studio): Konfigurera en .NET-utvecklingsmiljö.
3. Grundläggande kunskaper i C#-programmering: Lite förtrogenhet med C# krävs.
4.  Aspose.PDF-licens: Skaffa en tillfällig eller fullständig licens för att låsa upp alla funktioner i biblioteket. Du kan få en gratis provperiod[här](https://purchase.aspose.com/temporary-license/).

## Importera paket

Innan du börjar, se till att importera de nödvändiga namnrymden. Du behöver följande i ditt projekt:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu när allt är klart, låt oss hoppa in i steg-för-steg-guiden!

Vi ska skapa en tabell i ett PDF-dokument och utforma dess celler. Varje steg kommer att förklara processen i detalj.

## Steg 1: Skapa ett nytt PDF-dokument

 Det första steget är att skapa ett nytt PDF-dokument. I Aspose.PDF kan du initiera en ny`Document` objekt, som representerar din PDF-fil.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa ett nytt PDF-dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Här initierar vi ett PDF-dokument och ställer in dess titel och språk. Detta ger ditt dokument en ordentlig struktur, vilket är viktigt för PDF/UA-efterlevnad.

## Steg 2: Ställ in tabellstrukturen

Tabeller i PDF-filer definieras inom strukturelement. Låt oss skapa tabellen och definiera tabellens rader och kolumner.

```csharp
// Hämta rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;

// Skapa ett tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Vi har nu definierat bordets huvud (`TableTHeadElement`), kropp (`TableTBodyElement`), och fot (`TableTFootElement`) avsnitt. Du kan tänka på dessa som skelettet på ditt bord.

## Steg 3: Style rubrikcellerna

Att styla rubrikcellerna gör att de sticker ut. Här tillämpar vi bakgrundsfärger, ramar och textjustering.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

I det här steget går vi igenom varje rubrikcell, vilket ger den en grön-gul bakgrund, en grå ram och en högerjusterad text. Du kan justera dessa egenskaper för att matcha din önskade design.

## Steg 4: Fyll och styla tabellkroppen

Tabellkroppen innehåller de faktiska uppgifterna. Så här kan du utforma varje cell med specifika marginaler, ramar och textinställningar.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 I det här steget fyller vi tabellkroppen med fyra rader och utformar varje cell med gul bakgrund och centrerad, fet blå text. Vi använder också`MarginInfo`klass för att definiera vadderingen runt texten.

## Steg 5: Stil sidfoten

För att ge tabellen en komplett struktur lägger vi till och stylar sidfotscellerna, precis som vi gjorde med sidhuvudet.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Sidfotssektionen är utformad på samma sätt som sidhuvudet, vilket gör det enkelt för läsare att följa tabellens struktur.

## Steg 6: Spara och validera PDF-dokumentet

Slutligen sparar vi PDF-dokumentet och kontrollerar om det är PDF/UA-kompatibelt.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StyleTableCell.pdf");

// Kontrollerar PDF/UA-efterlevnad
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Vi sparar PDF-filen och använder`Validate` metod för att säkerställa att den uppfyller tillgänglighetsstandarder (PDF/UA-överensstämmelse).

## Slutsats

Att styla tabeller i en PDF med Aspose.PDF för .NET är både kraftfullt och flexibelt. Med några rader kod kan du skapa anpassade tabelldesigner som gör att dina PDF-dokument sticker ut. Från att anpassa cellkanter och bakgrunder till att säkerställa tillgänglighetsefterlevnad, Aspose.PDF gör det enkelt att skapa polerade PDF-filer.

## FAQ's

### Kan jag tillämpa olika stilar på enskilda tabellceller?  
Ja, du kan utforma enskilda celler genom att anpassa`TableTDElement` fastigheter.

### Hur kan jag slå samman tabellceller?  
 Du kan använda`ColSpan` och`RowSpan` egenskaper för att slå samman celler i en tabell.

### Är det möjligt att skapa en PDF/UA-kompatibel tabell?  
 Ja, som visas i den här guiden kan du säkerställa PDF/UA-efterlevnad genom att validera ditt dokument med hjälp av`Validate` metod.

### Kan jag använda olika typsnitt i tabellcellerna?  
 Absolut! Du kan ange olika teckensnitt med hjälp av`TextState` objekt för varje cell.

### Hur laddar jag ner Aspose.PDF för .NET?  
 Du kan ladda ner den från[släpper sida](https://releases.aspose.com/pdf/net/).