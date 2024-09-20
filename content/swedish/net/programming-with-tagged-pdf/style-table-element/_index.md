---
title: Stil bordselement
linktitle: Stil bordselement
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar och utformar ett tabellelement i Aspose.PDF för .NET med steg-för-steg-instruktioner, anpassad stil och PDF/UA-kompatibilitet.
type: docs
weight: 170
url: /sv/net/programming-with-tagged-pdf/style-table-element/
---
## Introduktion

I den här artikeln kommer vi att dyka in i hur man skapar och stilar ett tabellelement med Aspose.PDF för .NET. Du lär dig hur du strukturerar en tabell, tillämpar anpassade stilar och validerar PDF/UA-kompatibiliteten för ditt dokument. I slutet av denna handledning kommer du att kunna skapa professionella tabeller i dina PDF-filer med lätthet!

## Förutsättningar

Innan du hoppar in i handledningen måste du se till att du har följande:

1. Visual Studio eller liknande IDE installerad på din maskin.
2. .NET Framework eller .NET Core SDK för att köra programmet.
3.  Aspose.PDF för .NET-bibliotek laddas ner och refereras till i ditt projekt. Du kan hämta den senaste versionen från[här](https://releases.aspose.com/pdf/net/).
4.  En giltig Aspose-licens eller en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för att låsa upp bibliotekets fulla funktionalitet.

## Importera paket

För att börja, importera de nödvändiga namnrymden till ditt projekt:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dessa namnområden täcker grundläggande PDF-operationer, taggat innehåll, tabeller och textformatering.

Låt oss nu bryta ner processen för att skapa och styla en tabell i Aspose.PDF. Vi går igenom varje avsnitt i detalj så att du kan följa med.

## Steg 1: Skapa ett nytt PDF-dokument och ställ in taggat innehåll

I det här första steget skapar vi ett tomt PDF-dokument och ställer in dess taggade innehåll.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa ett nytt PDF-dokument
Document document = new Document();

// Konfigurera taggat innehåll
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Vi börjar med att skapa en ny`Document` objekt, som representerar vår PDF. De`TaggedContent`objekt används för att hantera dokumentets struktur, vilket säkerställer överensstämmelse med tillgänglighetsstandarder. Vi ställer in titeln och språket för dokumentet för korrekt taggning.

## Steg 2: Definiera rotelementet

Därefter skapar vi rotstrukturelementet, som fungerar som behållaren för allt innehåll i vår PDF.

```csharp
// Hämta rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;
```

 De`RootElement` fungerar som basbehållare för alla strukturerade element, inklusive vårt bord. Det hjälper till att upprätthålla dokumentets strukturella hierarki, vilket är viktigt för både organisation och tillgänglighet.

## Steg 3: Skapa och utforma tabellelementet

 Nu när rotelementet är konfigurerat skapar vi en`TableElement` och tillämpa stilar som bakgrundsfärg, ramar och justering.

```csharp
// Skapa tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Styla bordet
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Vi skapar en`TableElement` , som definierar vår tabellstruktur. De`BackgroundColor`, `Border` , och`Alignment` egenskaper gör att vi kan anpassa utseendet på tabellen. De`Broken` egenskapen säkerställer att om tabellen går sönder över sidor, så bryter den vertikalt.

## Steg 4: Ställ in tabellmått och cellformat

I det här steget kommer vi att definiera antalet kolumner, cellutfyllnad och andra viktiga tabellegenskaper.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Vi anger kolumnbredderna för att säkerställa att varje kolumn i tabellen är jämnt fördelad. De`DefaultCellBorder`, `DefaultCellPadding` , och`DefaultCellTextState` definiera standardstilarna för cellerna, inklusive ramar, utfyllnad, textfärg och teckenstorlek.

## Steg 5: Lägg till upprepade rader och anpassade stilar

Vi kan också definiera stilar för repeterande rader och andra specifika tabellelement som sidhuvuden och sidfötter.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 De`RepeatingRowsCount` säkerställer att de tre första raderna upprepas om tabellen sträcker sig över flera sidor. Vi ställer in`RepeatingRowsStyle` för att tillämpa en anpassad bakgrundsfärg på dessa rader.

## Steg 6: Lägg till bordshuvud-, kropps- och fotelement

Låt oss nu skapa tabellhuvuden, brödtexten och sidfotssektionerna och fylla dem med innehåll.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Skapa rubrikrad
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Fyll tabellkroppen
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Bordet är uppdelat i tre delar: huvud, kropp och fot. Vi skapar först rubrikraden med hjälp av`TableTHElement`och lägg till kolumnrubriker. Sedan fyller vi tabellen med`TableTDElement`, fylla varje cell med en etikett som inkluderar dess position.

## Steg 7: Spara dokumentet

Slutligen sparar vi PDF-dokumentet i den angivna katalogen.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StyleTableElement.pdf");
```

Detta steg avslutar processen för att skapa dokument genom att spara PDF-filen med den formaterade tabellen.

## Steg 8: Validera PDF/UA-efterlevnad

När du har sparat dokumentet är det viktigt att se till att det överensstämmer med PDF/UA-standarder (Universal Accessibility).

```csharp
// Kontrollera PDF/UA-kompatibilitet
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Här laddar vi om dokumentet och validerar det mot PDF/UA-standarder. Efterlevnad säkerställer att din PDF uppfyller tillgänglighetskraven, vilket gör den lämplig för ett brett spektrum av användare.

## Slutsats

Med Aspose.PDF för .NET är det enkelt och intuitivt att skapa och utforma tabeller i dina PDF-dokument. Genom att följa stegen som beskrivs i den här handledningen kan du bygga tabeller med anpassade stilar och säkerställa att dina PDF-filer uppfyller tillgänglighetsstandarder. Oavsett om du genererar rapporter eller skapar strukturerade dokument är tabeller ett kraftfullt verktyg för att presentera data tydligt.

## FAQ's

### Kan jag lägga till bilder i tabellceller?
 Ja, du kan infoga bilder i tabellceller med hjälp av`Image` element.

### Hur justerar jag kolumnbredderna dynamiskt?
 Du kan ställa in`ColumnAdjustment` egendom till`AutoFitToWindow` för att justera kolumnbredder automatiskt baserat på innehåll.

### Är PDF/UA-efterlevnad obligatorisk för alla dokument?
Även om det inte är obligatoriskt, rekommenderas det för dokument som kräver höga tillgänglighetsstandarder.

### Kan jag använda olika stilar på specifika rader?
 Ja, du kan anpassa enskilda rader eller celler genom att justera deras`TextState` eller`BackgroundColor`.

### Vad är fördelen med att använda taggat innehåll?
Taggat innehåll förbättrar dokumenttillgängligheten och hjälper till att säkerställa överensstämmelse med standarder som PDF/UA.