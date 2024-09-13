---
title: Bild och sidnummer i sidhuvudsavsnittet
linktitle: Bild och sidnummer i sidhuvudsavsnittet
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en bild och sidnummer i sidhuvudet och sidfoten i din PDF-fil med Aspose.PDF för .NET i denna steg-för-steg handledning.
type: docs
weight: 110
url: /sv/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Introduktion

När det gäller att skapa PDF-dokument av professionell kvalitet är det viktigt att ha kontroll över mindre detaljer som sidhuvuden och sidfötter. Du vill att dina dokument ska se polerade och välorganiserade ut, eller hur? Tja, med Aspose.PDF för .NET kan du lägga till bilder och sidnummer sömlöst i ditt dokuments sidhuvud och sidfot. I den här handledningen kommer vi att guida dig genom varje steg, vilket gör det enkelt att följa med.

## Förutsättningar

Innan du dyker in i den här tutorialen, se till att du har sorterat följande:

1. .NET Framework: Du måste ha någon version av .NET Framework installerad på din dator. Om du inte har det kan du enkelt ladda ner det från Microsofts webbplats.
2.  Aspose.PDF för .NET: Eftersom vi kommer att använda Aspose.PDF, se till att du har det installerat i ditt projekt. Du kan ladda ner en testversion[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper om C#: Bekantskap med grundläggande C#-programmering kommer säkert att hjälpa dig att förstå koden utan mycket krångel.
4. En bildfil: Du behöver en bild som du vill ha i rubriken på ditt PDF-dokument, till exempel en logotyp. Spara den i en tillgänglig katalog. 
5. IDE: Använd en Integrated Development Environment (IDE) som du väljer, som Visual Studio, för att arbeta med ditt .NET-projekt.

När du har förutsättningarna redo är du redo att skapa en fantastisk PDF-fil!

## Importera paket

För att börja använda Aspose.PDF för .NET måste du importera de nödvändiga namnrymden. Överst i din C#-fil skulle du lägga till:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Dessa namnområden ger dig tillgång till de klasser som behövs för manipulering av PDF-filer.

Låt oss nu komma ner till den verkliga affären! Följ dessa steg för att skapa ditt PDF-dokument, med en bild i sidhuvudet och sidnummer i sidfoten.

## Steg 1: Ställ in din dokumentkatalog

Varje bra projekt börjar med organisation. Definiera din dokumentkatalog där du ska spara dina filer och var din bild finns. Så här gör du:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Kom ihåg att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där du vill spara din PDF och var din bild finns.

## Steg 2: Skapa ett nytt PDF-dokument

Därefter kommer vi att skapa ett nytt PDF-dokument där all magi kommer att hända:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Vid det här laget har du skapat ett tomt PDF-dokument. Spännande, eller hur?

## Steg 3: Lägg till en sida i dokumentet

En PDF handlar om sidor. Låt oss lägga till en ny sida i vårt dokument med:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Nu har du en duk där du kan börja designa!

## Steg 4: Skapa rubriksektionen

Din rubrik kommer att innehålla bilden (som en logotyp) du vill visa. Skapa rubriksektionen med följande kod:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Nu har du en rubrik som du kan anpassa!

## Steg 5: Lägg till en bild i rubriken

Nu kommer vi till det roliga! Du måste lägga till bilden i din rubrik. Skapa först ett bildobjekt:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Ställ in sökvägen till din bild:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Lägg slutligen till bilden i din rubrik:

```csharp
header.Paragraphs.Add(image1);
```

Grattis! Du har precis lagt till en bild i ditt PDF-huvud.

## Steg 6: Skapa sidfotssektionen

Låt oss nu arbeta med sidfoten. I likhet med rubrikprocessen skapar du ett sidfotsobjekt:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Det är här du ska placera ditt sidnummer. 

## Steg 7: Lägg till text i sidfoten

Skapa ett textfragment som innehåller sidnumret:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Lägg sedan till det här textfragmentet i sidfoten:

```csharp
footer.Paragraphs.Add(txt);
```

Ser ni hur lätt det var? Du har ställt in ditt sidnummer dynamiskt!

## Steg 8: Spara PDF-dokumentet

Det sista steget i vårt äventyr är att spara dokumentet. Använd det här kommandot för att spara din nyskapade PDF:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Och precis så är din PDF klar och laddad med en sidhuvudbild och sidnummer i sidfoten!

## Slutsats

Och där har du det! Du har precis skapat en PDF med en bild i sidhuvudet och dynamiska sidnummer i sidfoten med Aspose.PDF för .NET. Det är helt otroligt hur några rader kod kan resultera i en så polerad utdata. Oavsett om det är för en företagsrapport eller ett personligt dokument, kommer att lägga till dessa element ändra tonen och professionaliteten i din PDF.

## FAQ's

### Kan jag använda Aspose.PDF på vilken .NET-plattform som helst?
Ja, Aspose.PDF för .NET stöder flera .NET-plattformar inklusive .NET Framework, .NET Core och mer.

### Finns det en gratis testversion tillgänglig för Aspose.PDF?
 Absolut! Du kan ladda ner en gratis testversion[här](https://releases.aspose.com/).

### Vilka bildformat stöds för rubriker?
Aspose.PDF stöder de vanligaste bildformaten som JPG, PNG och BMP för sidhuvuden och sidfötter.

### Kan jag anpassa sidnummerformatet?
Ja, du kan enkelt anpassa sidfotens text och format enligt dina behov.

### Finns teknisk support tillgänglig?
 Ja, Aspose ger dedikerad support genom deras forum. Du kan söka hjälp[här](https://forum.aspose.com/c/pdf/10).