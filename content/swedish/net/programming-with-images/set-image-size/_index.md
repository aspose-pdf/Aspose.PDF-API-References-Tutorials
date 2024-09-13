---
title: Ställ in bildstorlek i PDF-fil
linktitle: Ställ in bildstorlek i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in bildstorleken i en PDF med Aspose.PDF för .NET. Den här steg-för-steg-guiden hjälper dig att ändra storlek på bilder, justera sidegenskaper och spara PDF-filer.
type: docs
weight: 270
url: /sv/net/programming-with-images/set-image-size/
---
## Introduktion

Att arbeta med PDF-filer är ett vanligt krav för många applikationer, och förmågan att manipulera element i en PDF-fil kan vara avgörande. Oavsett om du bygger en rapportgenerator eller lägger till dynamiskt innehåll i din PDF, är det en viktig funktion att kontrollera storleken på bilderna i ditt dokument. I den här handledningen går vi igenom hur du ställer in bildstorleken i en PDF-fil med Aspose.PDF för .NET. Detta kraftfulla bibliotek erbjuder omfattande kontroll över PDF-innehåll, och vi delar upp det steg för steg för att visa dig hur enkelt det kan vara. I slutet kommer du att ändra storlek på bilder och förstå hur den här funktionen kan förbättra dina PDF-arbetsflöden.


## Förutsättningar

Innan vi dyker in i koden finns det några saker du måste ha på plats för att följa med den här handledningen.

1.  Aspose.PDF för .NET: Se till att du har den senaste versionen av Aspose.PDF-biblioteket installerat. Du kan[ladda ner den här](https://releases.aspose.com/pdf/net/).
2. .NET Framework eller .NET Core: Se till att du har en arbetsmiljö med .NET Framework eller .NET Core inställd.
3. Grundläggande kunskaper om C#: Vi kommer att använda C# som vårt programmeringsspråk, så det är viktigt att känna till det.
4. Exempelbild: Du behöver en exempelbild för att bädda in i PDF:en. Du kan använda vilken bild du vill, men se till att den är tillgänglig i din projektkatalog.

## Importera paket

För att använda Aspose.PDF för .NET måste du först importera de nödvändiga namnrymden. Här är en enkel inställning:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu när vi har täckt grunderna, låt oss gå vidare till att skapa och ändra ett PDF-dokument.

## Steg 1: Initiera ditt PDF-dokument

 Det första vi behöver göra är att skapa ett nytt PDF-dokument. Vi kommer att använda`Document` klass från Aspose.PDF för att åstadkomma detta.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentobjekt
Document doc = new Document();
```
 
 Här instansierar vi en`Document` objekt, som kommer att representera vår PDF-fil. Vi anger också katalogen där våra filer finns med hjälp av`dataDir` variabel. Detta är utgångspunkten för att skapa alla PDF-filer med Aspose.PDF.

## Steg 2: Lägg till en ny sida i din PDF

När vi har vårt dokument klart måste vi lägga till en sida till det. Varje PDF måste ha minst en sida, så låt oss lägga till en.

```csharp
// Lägg till sida till sidor samling av PDF-fil
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Vi lägger till en ny sida i dokumentet med hjälp av`Pages.Add()` metod. Den här sidan kommer att fungera som den duk som vi ska placera vår bild på. Varje sida i en PDF är i princip ett tomt blad där du kan lägga till text, bilder eller annat innehåll.

## Steg 3: Skapa en bildinstans

 Nu är det dags att förbereda bilden som vi vill infoga i PDF:en. Aspose.PDF ger en`Image` klass för att hantera bilder.

```csharp
// Skapa en bildinstans
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Vi skapar en ny instans av`Image` klass. Detta objekt kommer att innehålla egenskaperna för bilden som vi vill lägga till i PDF-filen. Vi konfigurerar bildens storlek och typ i nästa steg.

## Steg 4: Ställ in bildstorlek (bredd och höjd)

Här kommer vi till kärnan i vår handledning: ställa in storleken på bilden. Aspose.PDF låter dig ange bildens bredd och höjd i punkter.

```csharp
// Ställ in bildbredd och höjd i punkter
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 De`FixWidth` och`FixHeight`egenskaper låter dig ställa in bildens exakta mått i punkter. I det här exemplet ändrar vi storleken på bilden till 100x100 punkter. Du kan justera dessa värden för att passa dina behov.

## Steg 5: Ange bildtyp

Beroende på vilket bildformat du arbetar med kan du behöva ställa in bildtypen. Aspose.PDF stöder olika bildformat, och här definierar vi filtypen.

```csharp
// Ställ in bildtyp som SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 I det här fallet lämnar vi filtypen som`Unknown` , vilket gör att biblioteket automatiskt kan identifiera bildtypen. Om du känner till den specifika filtypen kan du ställa in den (t.ex.`ImageFileType.Jpeg` för JPEG-bilder). Detta steg säkerställer att Aspose vet hur man hanterar bilden på rätt sätt.

## Steg 6: Ställ in sökvägen till din bildfil

Nu måste vi berätta för Aspose var man kan hitta bildfilen. Se till att din bild är tillgänglig i den angivna katalogen.

```csharp
// Sökväg för källfil
img.File = dataDir + "aspose-logo.jpg";
```
 
 Här ställer vi in sökvägen till bilden. Bilden, i det här fallet, finns i`dataDir` mapp och heter`aspose-logo.jpg`Se till att du ersätter detta med det faktiska namnet och platsen för din bildfil.

## Steg 7: Lägg till bilden på sidan

Med bilden konfigurerad och filsökvägen inställd kan vi nu lägga till bilden på vår sida.

```csharp
// Lägg till bilden i styckesamlingen
page.Paragraphs.Add(img);
```
 
 De`Paragraphs.Add()` metoden låter oss lägga till bilden på sidan. Tänk på`Paragraphs` samling som en lista över objekt som kommer att renderas på PDF-sidan. Vi kan lägga till flera element till den här samlingen, såsom bilder, text och former.

## Steg 8: Justera sidegenskaper

För att se till att vår bild passar bra kommer vi att justera sidstorleken. Detta säkerställer att siddimensionerna matchar innehållet vi lägger till.

```csharp
// Ställ in sidegenskaper
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Här ställer vi in sidans bredd och höjd till 800 punkter. Det här steget är valfritt men säkerställer att sidan rymmer den ändrade storleken på bilden. Du kan justera dessa värden baserat på dina specifika krav.

## Steg 9: Spara PDF-filen

Slutligen, efter att ha konfigurerat bilden och sidegenskaperna, kan vi spara PDF:en.

```csharp
//Spara den resulterande PDF-filen
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Vi sparar det ändrade dokumentet som`SetImageSize_out.pdf` i samma katalog. Den här filen kommer nu att innehålla den ändrade storleken på bilden du lade till.

## Slutsats

I den här handledningen tog vi upp hur man ställer in bildstorleken i en PDF med Aspose.PDF för .NET. Vi gick igenom att skapa ett dokument, lägga till en sida, konfigurera en bild och spara resultatet. Denna steg-för-steg-guide är bara början på vad du kan göra med Aspose.PDF för .NET. Nu när du har lärt dig hur du ändrar storlek på bilder, utforska gärna andra funktioner som textformatering, skapande av tabeller och till och med lägga till kommentarer till din PDF.

## FAQ's

### Kan jag använda olika bildformat med Aspose.PDF för .NET?  
Ja, Aspose.PDF stöder olika bildformat som JPEG, PNG, BMP och SVG.

### Hur bibehåller jag bildförhållandet?  
 Du kan behålla bildförhållandet genom att ställa in antingen`FixWidth` eller`FixHeight` medan den andra dimensionen inte är inställd.

### Kan jag lägga till flera bilder på en enda PDF-sida?  
Absolut! Upprepa bara processen att lägga till en bildinstans och lägg till var och en till`Paragraphs` samling.

### Är det möjligt att ställa in bildstorleken i andra enheter än punkter?  
Aspose.PDF fungerar främst med punkter, men du kan konvertera andra enheter som tum eller millimeter till punkter (1 tum = 72 punkter).

### Hur placerar jag en bild på en specifik plats på sidan?  
 Du kan ställa in`Image.LowerLeftX` och`Image.LowerLeftY` egenskaper för att placera bilden på sidan.