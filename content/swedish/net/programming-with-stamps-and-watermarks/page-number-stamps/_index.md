---
title: Sidnummerstämplar i PDF-fil
linktitle: Sidnummerstämplar i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till sidnummerstämplar i PDF-filer med Aspose.PDF för .NET genom vår lättanvända guide, komplett med kodexempel.
type: docs
weight: 160
url: /sv/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Introduktion

Har du någonsin råkat ut för att brottas med ett PDF-dokument och önskat att det hade sidnummer för enklare navigering? Oavsett om du är en student som delar anteckningar, en professionell som presenterar rapporter eller någon som hanterar flersidiga dokument, kan lägga till sidnummer verkligen förbättra tydligheten i dina PDF-filer. Lyckligtvis kan du med det kraftfulla Aspose.PDF för .NET-biblioteket enkelt lägga till sidnummerstämplar till dina PDF-dokument. I den här guiden går vi igenom hela processen steg-för-steg, för att säkerställa att du är utrustad med all den kunskap du behöver. Låt oss dyka in!

## Förutsättningar

Innan vi börjar med att lägga till sidnummerstämplar i dina PDF-dokument, se till att du har följande förutsättningar:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system. Du kommer att skriva och köra din kod här.
2. .NET Framework: Bekantskap med C#-programmering och .NET-ramverket är viktigt eftersom Aspose.PDF är designat för .NET-applikationer.
3.  Aspose.PDF Library: Du kan ladda ner Aspose.PDF-biblioteket från[Aspose PDF-versioner](https://releases.aspose.com/pdf/net/). 
4. Grundläggande förståelse för PDF-filer: Även om du inte behöver vara expert, kommer en grundläggande förståelse för hur PDF-filer fungerar att hjälpa dig att förstå handledningen bättre.

När du har ställt in dessa förutsättningar är du redo att börja stämpla sidnumren!

## Importera paket

Innan du dyker in i kodning måste du se till att de nödvändiga Aspose.PDF-paketen importeras till ditt projekt. Detta är avgörande för att utnyttja biblioteksfunktionerna sömlöst. Så här gör du:

### Skapa ett nytt projekt

1. Öppna Visual Studio.
2.  Klicka på`File` >`New` >`Project`.
3.  Välj en mall som passar för C# (t.ex. konsolapplikation), namnge den och klicka`Create`.

### Lägg till Aspose.PDF-referens

1. Högerklicka på projektnamnet i Solution Explorer.
2.  Klicka på`Manage NuGet Packages`.
3.  Leta efter`Aspose.PDF` och installera den senaste versionen.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Med biblioteket redo att rulla, låt oss hoppa in i kodningen!

Nu när vår miljö är konfigurerad är det dags att lägga till sidnummerstämplar i en PDF-fil. Vi kommer att dela upp denna process i tydliga steg för bättre förståelse.

## Steg 1: Ange dokumentkatalogen

Till att börja med måste du ange katalogen där din PDF-fil finns. Detta är utgångspunkten för ditt projekt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Uppdatera den här sökvägen
```

 Förklaring: Byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen som leder till katalogen som innehåller din PDF-fil. Detta är avgörande eftersom det talar om för din kod var den ska hitta filen du vill manipulera.

## Steg 2: Öppna dokumentet

Därefter öppnar vi det befintliga PDF-dokumentet som vi vill lägga till sidnummerstämplarna till.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Förklaring: Här använder vi`Document` klass tillhandahållen av Aspose.PDF för att öppna vår specifika PDF-fil. Se till att filnamnet matchar den faktiska filen du har i din katalog.

## Steg 3: Skapa en sidnummerstämpel

Nu kommer det roliga! Låt oss skapa en sidnummerstämpel att lägga till i vår PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Förklaring: The`PageNumberStamp`klass kommer att tillåta oss att skapa en stämpel som visar det aktuella sidnumret i förhållande till det totala antalet sidor i dokumentet.

## Steg 4: Konfigurera stämpeln

Nu måste du konfigurera dina stämpelinställningar. Det är här du designar hur stämpeln ser ut och beter sig.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Förklaring:
- `Background = false`: Detta betyder att stämpeln kommer att visas i förgrunden.
- `Format`: Här ställer du in formatet för att visa "Sida X av Y", där du dynamiskt hämtar det totala antalet sidor i dokumentet.
- `BottomMargin`: Justerar avståndet från botten av sidan.
- `HorizontalAlignment`: Centrerar stämpeln horisontellt.
- `StartingNumber`: Ställer in vad startsidans nummer blir, vanligtvis från 1.

## Steg 5: Ställ in textegenskaper

Därefter kan du anpassa hur texten i stämpeln ser ut.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Förklaring: Dessa attribut konfigurerar teckensnittstyp, teckenstorlek, stil (både fet och kursiv) och färgen på texten i stämpeln för att göra den visuellt tilltalande.

## Steg 6: Lägg till stämpeln på en specifik sida

Med din stämpel konfigurerad är det dags att lägga till den på en specifik sida i ditt dokument.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Förklaring: Den här raden lägger till stämpeln på första sidan i PDF-filen. Du kan justera`Pages[1]` index för andra sidor vid behov.

## Steg 7: Spara utdatadokumentet

Slutligen, spara det ändrade PDF-dokumentet så att dina ändringar är permanenta.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Förklaring: Du definierar utdatafilens sökväg och sparar dokumentet. Konsolen kommer att meddela dig att stämpeln har lagts till och var filen är sparad.

## Slutsats

Att lägga till sidnummerstämplar till dina PDF-filer med Aspose.PDF för .NET är inte bara enkelt utan också mycket anpassningsbart. Vi gick igenom skapandet av en sidnummerstämpel steg för steg, vilket säkerställer att du har tydlig vägledning på vägen. Du har nu kunskapen att förbättra dina PDF-dokument, vilket gör dem mer användarvänliga och professionella. 

## FAQ's

### Kan jag anpassa utseendet på sidnummer?  
Ja! Du kan ändra teckensnitt, storlek, färg och formatering av sidnumren som visas i guiden.

### Är Aspose.PDF gratis att använda?  
 Aspose.PDF erbjuder en gratis provperiod, men du behöver en licens för omfattande användning. Kolla in[köpsida](https://purchase.aspose.com/buy) för mer info.

### Vad händer om jag stöter på problem när jag implementerar?  
 Du kan besöka[Aspose Support Forum](https://forum.aspose.com/c/pdf/10) för hjälp.

### Hur kan jag generera sidnummer automatiskt för flera sidor?  
Guidens kod beräknar automatiskt det totala antalet sidor, vilket gör det enkelt att anpassa för flera sidor.

### Kan jag använda Aspose.PDF i andra programmeringsspråk?  
Medan den här guiden fokuserar på .NET, har Aspose bibliotek för Java, Python och mer.