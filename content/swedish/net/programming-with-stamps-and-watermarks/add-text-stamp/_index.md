---
title: Lägg till textstämpel i PDF-fil
linktitle: Lägg till textstämpel i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en textstämpel i en PDF-fil med Aspose.PDF för .NET med vår steg-för-steg-guide och lyft dina dokumentpresentationer.
type: docs
weight: 50
url: /sv/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Introduktion

dagens digitala tidsålder är PDF-filer ett vanligt format för att dela och leverera dokument. Oavsett om du är en utvecklare, en innehållsskapare eller bara någon som vill förbättra sina PDF-filer, kan det vara en spelomvandlare att veta hur man manipulerar PDF-filer programmatiskt. En fiffig funktion du kanske vill använda dig av är möjligheten att lägga till textstämplar i dina PDF-filer. Att lägga till en textstämpel kan ge dina dokument en professionell touch eller förmedla viktig information, som "Prov", "Konfidentiellt" eller till och med en vattenstämpel.

## Förutsättningar

Innan vi hoppar in i koden finns det några förutsättningar för att säkerställa att du har allt korrekt inställt. Här är vad du behöver:

1.  Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat i ditt projekt. Om du inte har gjort det ännu kan du ladda ner det från[Aspose hemsida](https://releases.aspose.com/pdf/net/).
2. Visual Studio eller kompatibel IDE: Du behöver en utvecklingsmiljö för att skriva och köra din .NET-kod. Visual Studio är det vanligaste valet bland utvecklare.
3. Grundläggande kunskaper i C#: Bekantskap med C# och objektorienterade programmeringsprinciper hjälper dig att förstå exemplen bättre.
4. Exempel på PDF-fil: Du bör ha en PDF-fil redo att arbeta med. Du kan skapa en grundläggande PDF eller använda en befintlig PDF för att testa funktionen.

När du har löst dessa förutsättningar kan vi gå vidare till kodning!

## Importera paket

Låt oss nu importera de nödvändiga paketen. Detta steg är avgörande eftersom det gör klasserna och metoderna från Aspose-biblioteket tillgängliga i ditt projekt.

### Importera Aspose.PDF Assembly

För att komma igång måste du importera namnområdet Aspose.PDF. Överst i din C#-fil lägger du till följande med hjälp av direktiv:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Detta ger dig tillgång till klasser som är viktiga för att skapa och manipulera PDF-dokument.

Låt oss nu gå in på köttet i handledningen. Vi kommer att dela upp processen i tydliga och koncisa steg. Varje steg guidar dig genom koden för att lägga till en textstämpel till en PDF-fil.

## Steg 1: Konfigurera dokumentkatalogen

Först måste du upprätta katalogen där ditt PDF-dokument är lagrat. Det betyder att din kod måste veta var den PDF-fil du vill redigera kan hitta.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Förklaring: Byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där din PDF-fil (`AddTextStamp.pdf`) lagras. Den här sökvägen används senare för att öppna och spara den ändrade PDF-filen.

## Steg 2: Öppna PDF-dokumentet

 Därefter kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass från namnområdet Aspose.PDF.

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Förklaring: Här skapar vi en instans av`Document` klass och skickar vägen till vår PDF-fil. Detta kommer att ladda PDF-filen så att vi kan manipulera den.

## Steg 3: Skapa en textstämpel

Nu kommer vi att skapa en textstämpel som vi senare kommer att applicera på vårt PDF-dokument.

```csharp
// Skapa textstämpel
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Förklaring: The`TextStamp` objekt skapas med den text du vill visa. I det här fallet använder vi "Sample Stamp" som text för vår stämpel.

## Steg 4: Ställ in stämpelegenskaper

För att anpassa din stämpel kan vi ställa in olika egenskaper som bakgrundsfärg, position och rotation. Låt oss göra det nu:

```csharp
// Ställ in om stämpeln är bakgrund
textStamp.Background = true;

// Ange ursprung
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Rotera stämpeln
textStamp.Rotate = Rotation.on90;
```

Förklaring:
- Bakgrund: Ställer in detta till`true` betyder att stämpeln kommer att visas bakom innehållet i PDF-filen.
- XIndent & YIndent: Dessa egenskaper bestämmer positionen för stämpeln på sidan. I det här exemplet kommer stämpeln att placeras 100 enheter från sidans vänstra och övre kant.
- Rotera: Detta roterar stämpeln 90 grader. Du kan välja olika rotationsalternativ baserat på dina designkrav.

## Steg 5: Anpassa textegenskaper

Låt oss sedan bli kreativa genom att anpassa utseendet på texten i vår stämpel:

```csharp
// Ställ in textegenskaper
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Förklaring:
- Teckensnitt: Vi använder typsnittet Arial och gör det fetstilt och kursivt.
- FontSize: Den är inställd på 14 poäng.
- Förgrundsfärg: Använd RGB för att ställa in textfärgen till Aqua. Ändra gärna färgen för att passa dina varumärkes- eller designbehov!

## Steg 6: Lägg till stämpel på PDF-sidan

Nu är det dags att lägga till stämpeln på en specifik sida i PDF-dokumentet.

```csharp
// Lägg till stämpel på en viss sida
pdfDocument.Pages[1].AddStamp(textStamp);
```

Förklaring: I det här exemplet läggs stämpeln till på första sidan i PDF:en (sidorna är 1-indexerade). Justera sidnumret efter behov för ditt dokument.

## Steg 7: Spara den modifierade PDF-filen

Slutligen, låt oss spara dokumentet med den nyligen tillagda textstämpeln.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Förklaring: Vi definierar en ny sökväg för utdatafilen och sparar sedan det ändrade dokumentet. Efter att ha sparats skrivs sökvägen ut till konsolen, vilket bekräftar att åtgärden lyckades.

## Slutsats

Grattis! Du har framgångsrikt lagt till en textstämpel till en PDF-fil med Aspose.PDF för .NET. Med den här metoden kan du kommentera dina dokument effektivt, vilket förbättrar både deras professionalism och användbarhet. Oavsett om du lägger till vattenstämplar, signaturer eller enkla anteckningar, erbjuder Aspose-biblioteket kraftfulla verktyg för att enkelt manipulera dina PDF-filer.

## FAQ's

### Vad är en textstämpel i en PDF?
En textstämpel är en grafisk överlagring som innehåller text som kan placeras på ett PDF-dokument, ofta används för anteckningar eller vattenstämplar.

### Kan jag anpassa stämpeln med bilder?
Ja, Aspose.PDF stöder även att lägga till bildstämplar, vilket ger mer designflexibilitet.

### Vilka programmeringsspråk kan jag använda med Aspose.PDF?
Aspose.PDF är främst inriktat på .NET, men det finns versioner tillgängliga för andra språk som Java och Python.

### Hur får jag en tillfällig licens för Aspose.PDF?
 Du kan ansöka om en tillfällig licens genom att besöka[köplänk](https://purchase.aspose.com/temporary-license/) på deras hemsida.

### Var kan jag hitta support för Aspose.PDF?
 Support för Aspose.PDF finns på deras[supportforum](https://forum.aspose.com/c/pdf/10).