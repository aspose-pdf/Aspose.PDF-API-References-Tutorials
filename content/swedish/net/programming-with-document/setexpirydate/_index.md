---
title: Ställ in utgångsdatum i PDF-fil
linktitle: Ställ in utgångsdatum i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in ett utgångsdatum i PDF-filer med Aspose.PDF för .NET. Förbättra dokumentsäkerheten med denna steg-för-steg-guide.
type: docs
weight: 300
url: /sv/net/programming-with-document/setexpirydate/
---
## Introduktion

dagens digitala tidsålder är det viktigare än någonsin att hantera och säkra dokument. Tänk dig att skicka ut en PDF som automatiskt blir otillgänglig efter ett visst datum. Låter som magi, eller hur? Tja, med Aspose.PDF för .NET kan du enkelt ställa in ett utgångsdatum för dina PDF-filer. Den här funktionen är särskilt användbar för känsliga dokument som måste begränsas efter en viss period. I den här handledningen går vi igenom processen att ställa in ett utgångsdatum i en PDF-fil steg för steg. Så ta tag i din kodningshatt och låt oss dyka in!

## Förutsättningar

Innan vi sätter igång finns det några saker du måste ha på plats:

1. Utvecklingsmiljö: Se till att du har en .NET-utvecklingsmiljö inrättad. Detta kan vara Visual Studio eller någon annan IDE som stöder .NET.
2.  Aspose.PDF för .NET: Du måste ha Aspose.PDF-biblioteket installerat. Om du inte har gjort det ännu kan du ladda ner det från[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper om C#: Denna handledning förutsätter att du har en grundläggande förståelse för C#-programmering. Om du är ny på C#, oroa dig inte! Vi kommer att hålla det enkelt och okomplicerat.

## Importera paket

För att komma igång med Aspose.PDF måste du importera de nödvändiga namnrymden i ditt C#-projekt. Så här kan du göra det:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Dessa namnrymder ger dig tillgång till de kärnfunktioner som krävs för att arbeta med PDF-dokument i Aspose.PDF.

## Steg 1: Konfigurera din dokumentkatalog

Först och främst måste du ange sökvägen till din dokumentkatalog. Det är här din utdata-PDF kommer att sparas. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där du vill spara din PDF-fil. Det är som att säga till ditt program, "Hej, det är här jag förvarar mina filer!"

## Steg 2: Instantiera dokumentobjektet

 Därefter måste du skapa en ny instans av`Document` klass. Det här är din arbetsyta där du kommer att skapa din PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Tänk på`Document` objekt som ett tomt pappersark. Du kan lägga till innehåll som du vill!

## Steg 3: Lägg till en sida till PDF-filen

Nu när du har konfigurerat ditt dokument är det dags att lägga till en sida till det. Det är dit ditt innehåll kommer att gå.

```csharp
doc.Pages.Add();
```

Du har precis skapat en ny sida i din PDF. Det är som att lägga till en ny sida i din anteckningsbok där du kan skriva ner dina tankar.

## Steg 4: Lägg till text på sidan

Låt oss göra den här sidan lite mer intressant genom att lägga till lite text. Vi lägger till ett enkelt "Hello World"-meddelande.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Denna kodrad lägger till ett textfragment på första sidan i din PDF. Det är som att skriva en titel överst på din sida!

## Steg 5: Skapa JavaScript för utgångsdatum

Nu kommer det roliga! Du skapar en JavaScript-åtgärd som kontrollerar utgångsdatumet för PDF:en. Om det aktuella datumet överskrider utgångsdatumet kommer ett meddelande att varna användaren.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Här är vad som händer:
- Du anger utgångsår och månad.
- Du får dagens datum.
- Du jämför dagens datum med utgångsdatumet.
- Om dagens datum har passerat utgångsdatumet dyker ett meddelande upp!

## Steg 6: Ställ in JavaScript som PDF Open Action

Nu måste du ställa in JavaScript-åtgärden som öppen åtgärd för ditt PDF-dokument. Det betyder att JavaScript kommer att köras så snart PDF-filen öppnas.

```csharp
doc.OpenAction = javaScript;
```

Den här raden talar om för PDF:en att köra JavaScript när någon öppnar den. Det är som att ställa in en påminnelse som slocknar så fort du öppnar din kalender!

## Steg 7: Spara PDF-dokumentet

Äntligen är det dags att spara ditt PDF-dokument med funktionen för utgångsdatum. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Den här raden sparar din PDF i den angivna katalogen med namnet "SetExpiryDate_out.pdf". Det är som att sätta ditt färdiga konstverk i en ram!

## Slutsats

Och där har du det! Du har framgångsrikt skapat en PDF-fil med ett utgångsdatum med Aspose.PDF för .NET. Denna funktion förbättrar inte bara säkerheten utan säkerställer också att känslig information hålls under kontroll. Oavsett om du skickar ut kontrakt, rapporter eller andra viktiga dokument, kan det vara en spelförändring att sätta ett utgångsdatum.

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument i .NET-applikationer.

### Kan jag använda Aspose.PDF gratis?
 Ja, du kan använda en gratis testversion av Aspose.PDF. Du kan ladda ner den[här](https://releases.aspose.com/).

### Hur köper jag Aspose.PDF?
Du kan köpa Aspose.PDF genom att besöka[köpsidan](https://purchase.aspose.com/buy).

### Vad händer om jag behöver stöd?
Om du har några frågor eller behöver hjälp kan du besöka[Aspose supportforum](https://forum.aspose.com/c/pdf/10).

### Kan jag få en tillfällig licens för Aspose.PDF?
 Ja, du kan begära en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).