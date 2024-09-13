---
title: Sidnummer i sidhuvudet med hjälp av flytande låda
linktitle: Sidnummer i sidhuvudet med hjälp av flytande låda
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till sidnummer i din PDF-sidhuvud och sidfot med hjälp av en flytande låda med Aspose.PDF för .NET i denna steg-för-steg handledning.
type: docs
weight: 150
url: /sv/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Introduktion

När det gäller att hantera PDF-dokument programmatiskt framstår Aspose.PDF för .NET som ett exceptionellt verktyg. Det förenklar sättet vi skapar, redigerar och manipulerar PDF-filer i .NET-program. Oavsett om du genererar fakturor, rapporter eller vilken typ av dokument som helst, kan en elegant lägga till sidnummer förbättra professionalismen och organisationen av dina PDF-filer. I den här handledningen fördjupar vi oss i hur du lägger till sidnummer i sidhuvudet och sidfoten i din PDF med hjälp av en flytande ruta. Redo att börja? Låt oss gå!

## Förutsättningar

Innan vi börjar denna spännande resa in i PDF-manipulationsområdet, finns det några saker du behöver ha:

### .NET-miljöinställningar
Se till att du har en .NET-utvecklingsmiljö. Du kan använda Visual Studio, som är ett populärt val bland utvecklare för .NET-applikationer.

### Aspose.PDF-bibliotek
Installera Aspose.PDF-biblioteket. Du kan enkelt ladda ner den från hemsidan:

- [Ladda ner Aspose.PDF för .NET](https://releases.aspose.com/pdf/net/)

### Grundläggande kunskaper i C#-programmering
En grundläggande förståelse för C# hjälper dig att förstå begreppen och kodningsfragmenten som presenteras i denna handledning.

### Tillgång till dokumentationen
 Det är alltid fördelaktigt att ha[Aspose.PDF-dokumentation](https://reference.aspose.com/pdf/net/) praktiskt för referens och djupare utforskning av eventuella ytterligare funktioner.

## Importera paket

För att komma igång måste du importera de nödvändiga paketen i ditt projekt. Detta säkerställer att Aspose.PDF-sammansättningen är tillgänglig för användning i din kod. Så här gör du:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Låt oss nu dela upp processen att lägga till sidnummer med hjälp av en flytande låda i hanterbara steg. Följ med när vi går igenom.

## Steg 1: Konfigurera din dokumentmiljö

Låt oss börja med att ange katalogen där ditt PDF-dokument ska lagras. Detta är avgörande eftersom det dikterar var din utdatafil sparas.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`YOUR DOCUMENT DIRECTORY` med sökvägen som du väljer där du vill spara den utgående PDF-filen.

## Steg 2: Instantiera dokumentet

 Att skapa ett nytt PDF-dokument är nästa steg. Detta innebär att använda`Document` klass från Aspose.PDF-biblioteket.

```csharp
// Instantiera dokumentinstans
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Här skapar vi en ny instans av`Document` klass, som fungerar som vår duk för manipulation.

## Steg 3: Lägg till en ny sida

Låt oss nu lägga till en sida i vårt PDF-dokument. Varje PDF-fil behöver minst en sida, eller hur?

```csharp
// Lägg till en sida i PDF-dokumentet
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Det här kodavsnittet lägger till en ny sida i vårt dokument, vilket gör det redo att ta emot innehåll, inklusive vår flytande ruta med sidnummer.

## Steg 4: Skapa en flytande låda

 Därefter är det dags att skapa vår flytande box som kommer att hålla sidnumret. De`FloatingBox`klass låter oss placera innehåll fritt på sidan.

```csharp
// Initierar en ny instans av FloatingBox-klassen
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Här, parametrarna`(140, 80)` ange bredd och höjd på den flytande lådan. Du kan justera dessa värden baserat på dina layoutpreferenser.

## Steg 5: Placera den flytande lådan

 Positionering är nyckeln! Du vill bestämma var sidnumret ska visas på sidan. Du kommer att arbeta med`Left` och`Top` egenskaper för att ange positionen.

```csharp
// Flytande värde som anger styckets vänstra position
box1.Left = 2;
// Flytande värde som anger styckets topposition
box1.Top = 10;
```
Dessa värden dikterar placeringen av den flytande lådan på sidan. Experimentera gärna med dem för att se vad som ser bäst ut för ditt dokument.

## Steg 6: Lägg till text med sidnummermakrot

Nu kommer vi att lägga till en sträng som dynamiskt visar sidnumret. Det är här magin händer!

```csharp
// Lägg till makron till styckesamlingen i FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 I det här fallet,`($p/ $P)`är ett makro som visar det aktuella sidnumret (`$p`) och det totala antalet sidor (`$P`). Som ett resultat formaterar den texten så att den läses något som "Sida: 1/5".

## Steg 7: Lägg till den flytande lådan på sidan

Det är dags att lägga till Floating Box, tillsammans med sidnummertexten, på vår nyskapade sida.

```csharp
// Lägg till en floatingBox på sidan
page.Paragraphs.Add(box1);
```
Den här raden bäddar i huvudsak in din flytande box på sidan, vilket gör den till en del av dokumentets layout. 

## Steg 8: Spara ditt dokument

Slutligen, glöm inte att spara ditt arbete! Det sista steget är att spara ditt PDF-dokument med ett korrekt filnamn.

```csharp
// Spara dokumentet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Se till att den angivna sökvägen inkluderar ditt önskade filnamn. Nu är din fantastiska PDF med sidnummer skapad! 

## Slutsats

Och där har ni det, gott folk! Att lägga till sidnummer i sidhuvudet och sidfoten i din PDF med Aspose.PDF för .NET är så enkelt. Med bara några rader kod har du gett dig ut på en resa för att bemästra dokumentbehandlingen i dina applikationer. Tveka inte att experimentera med olika layouter och formatering – trots allt vet kreativiteten inga gränser! Är du redo att skapa det där professionella dokumentet? Ta tag i din kodningshatt och börja experimentera.

## FAQ's

### Kan jag anpassa utseendet på sidnummertexten?  
 Ja, du kan anpassa textegenskaper, såsom teckenstorlek, färg och stil genom att justera`TextFragment` fastigheter.

### Är Aspose.PDF gratis att använda?  
 Medan Aspose.PDF erbjuder en gratis provperiod, är det en betald produkt för produktionsanvändning. Du kan[köp den här](https://purchase.aspose.com/buy).

### Var kan jag hitta mer detaljerad dokumentation?  
 Du kan hitta omfattande dokumentation på[Aspose.PDF Dokumentationssida](https://reference.aspose.com/pdf/net/).

### Hur använder jag sidhuvuden och sidfötter på flera sidor?  
Du kan gå igenom alla sidor i ditt dokument och tillämpa den flytande rutan på var och en på samma sätt.

### Vad händer om jag behöver support för ytterligare funktioner?  
För ytterligare frågor eller support kan du besöka[Aspose Forum](https://forum.aspose.com/c/pdf/10).