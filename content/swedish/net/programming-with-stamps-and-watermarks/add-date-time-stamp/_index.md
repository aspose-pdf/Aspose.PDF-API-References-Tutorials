---
title: Lägg till datum Tidstämpel i PDF-fil
linktitle: Lägg till datum Tidstämpel i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en datum- och tidsstämpel till dina PDF-filer med Aspose.PDF för .NET med denna steg-för-steg-guide. Perfekt för att förbättra dokumentets äkthet.
type: docs
weight: 10
url: /sv/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Introduktion

När det kommer till att hantera dokument, särskilt PDF-filer, kan det vara en förändring av spelet att lägga till en datum- och tidsstämpel. Oavsett om du arbetar med juridiska dokument, projektrapporter eller fakturor, ger en tidsstämpel inte bara äkthet utan ger också en tydlig registrering av när dokumentet skapades eller ändrades. I den här guiden går vi igenom processen att lägga till en datum- och tidsstämpel till en PDF-fil med hjälp av Aspose.PDF-biblioteket för .NET. 

Den här artikeln är utformad för att vara enkel och lätt att följa, så även om du är ny på programmering eller Aspose.PDF-biblioteket, kommer du att kunna implementera den här funktionen med tillförsikt. Låt oss dyka in!

## Förutsättningar

Innan vi sätter igång finns det några förutsättningar du måste ha på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på din dator. Det är här du ska skriva och köra din kod.
2. Aspose.PDF för .NET: Du måste ladda ner och installera Aspose.PDF-biblioteket. Du kan hitta den senaste versionen[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper om C#: Bekantskap med C#-programmering hjälper dig att förstå exemplen bättre, men oroa dig inte om du precis har börjat; vi förklarar allt steg för steg.
4.  En PDF-fil: Ha ett exempel på en PDF-fil redo. För vårt exempel använder vi en fil med namnet`AddTextStamp.pdf`.

När du har dessa förutsättningar är du redo att börja lägga till datum- och tidsstämplar till dina PDF-filer!

## Importera paket

Till att börja med måste du importera de nödvändiga namnrymden i ditt C#-projekt. Så här gör du:

### Skapa ett nytt projekt

1. Öppna Visual Studio: Starta din Visual Studio-applikation.
2. Skapa ett nytt projekt: Välj "Skapa ett nytt projekt" från startskärmen.
3. Välj Console App: Välj "Console App (.NET Framework)" från listan över projektmallar.
4.  Namnge ditt projekt: Ge ditt projekt ett namn, till exempel`PDFDateTimeStamp`.

### Lägg till Aspose.PDF-referens

1. Högerklicka på Referenser: I Solution Explorer, högerklicka på mappen "Referenser" i ditt projekt.
2. Välj "Lägg till referens": Välj "Lägg till referens" från snabbmenyn.
3. Bläddra efter Aspose.PDF: Navigera till platsen där du laddade ner Aspose.PDF och välj den. Klicka på "OK" för att lägga till det i ditt projekt.

### Importera nödvändiga namnområden

 Överst på din`Program.cs` fil måste du importera följande namnområden:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Nu när vi har allt inställt, låt oss dela upp processen att lägga till en datum- och tidsstämpel i en PDF-fil i tydliga, hanterbara steg.

## Steg 1: Ställ in dokumentkatalogen

Först måste du ange katalogen där din PDF-fil finns. Detta är avgörande eftersom koden kommer att leta efter PDF:en i den här katalogen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersätt med din faktiska väg
```

 Se till att byta ut`YOUR DOCUMENT DIRECTORY` med den faktiska sökvägen till din PDF-fil.

## Steg 2: Öppna PDF-dokumentet

Därefter öppnar du PDF-dokumentet där du vill lägga till tidsstämpeln. 

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Denna kodrad initierar`Document` klass och laddar din PDF-fil i`pdfDocument` objekt.

## Steg 3: Skapa datum och tidsstämpel

Nu är det dags att skapa datum- och tidsstämpeln. Du kommer att formatera den så att den visas på ett specifikt sätt. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Här,`DateTime.Now` hämtar aktuellt datum och tid, och`ToString` formaterar den till önskat format.

## Steg 4: Skapa en textstämpel

Med datum- och tidssträngen redo kan du nu skapa en textstämpel som kommer att läggas till din PDF.

```csharp
// Skapa textstämpel
TextStamp textStamp = new TextStamp(annotationText);
```

 Den här raden skapar en ny instans av`TextStamp` med den formaterade datum- och tidssträngen.

## Steg 5: Ställ in egenskaper för stämpeln

Du kan anpassa stämpelns utseende och position. Så här ställer du in dess egenskaper:

```csharp
// Ställ in egenskaper för stämpeln
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

I det här steget ställer vi in marginalerna och anpassar stämpeln till det nedre högra hörnet av PDF-sidan.

## Steg 6: Lägg till stämpeln i PDF:en

Nu är det dags att lägga till textstämpeln i ditt PDF-dokument. 

```csharp
// Lägger till stämpel på frimärkssamling
pdfDocument.Pages[1].AddStamp(textStamp);
```

Den här raden lägger till stämpeln på första sidan i PDF-filen. Du kan ändra sidnumret om du vill placera det på en annan sida.

## Steg 7: Skapa en fritextkommentar (valfritt)

Om du vill lägga till en kommentar till stämpeln kan du skapa en`FreeTextAnnotation` enligt följande:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Detta valfria steg skapar en fritextkommentar som kan ge ytterligare sammanhang eller information om stämpeln.

## Steg 8: Konfigurera anteckningsgränsen

Om du vill anpassa gränsen för din kommentar kan du också göra det:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Det här kodavsnittet ställer in gränsbredden till 0, vilket gör den osynlig och lägger till anteckningen i PDF-filen.

## Steg 9: Spara PDF-dokumentet

Slutligen måste du spara det ändrade PDF-dokumentet. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Ange utdatafilens namn
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Den här raden sparar PDF-filen med den tillagda tidsstämpeln till en ny fil. Du kan kontrollera din angivna katalog för att se utdata.

## Slutsats

Grattis! Du har framgångsrikt lagt till en datum- och tidsstämpel till en PDF-fil med Aspose.PDF för .NET. Denna enkla men effektiva funktion kan förbättra dina dokument, göra dem mer professionella och ge en tydlig bild av när de skapades eller ändrades. 

## FAQ's

### Kan jag anpassa datumformatet i tidsstämpeln?
 Ja, du kan ändra`ToString`metod för att ändra datumformatet efter dina önskemål.

### Är Aspose.PDF gratis att använda?
 Aspose.PDF erbjuder en gratis provperiod, men för alla funktioner måste du köpa en licens. Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).

### Kan jag lägga till flera tidsstämplar i en PDF?
 Absolut! Du kan skapa flera`TextStamp` instanser och lägg till dem på olika sidor eller positioner i PDF-filen.

### Vad händer om jag inte har Visual Studio?
Du kan använda vilken C# IDE eller textredigerare som helst, men för att köra och felsöka ditt projekt rekommenderas Visual Studio.

### Var kan jag hitta fler exempel på användning av Aspose.PDF?
 Du kan utforska fler exempel och handledningar i[Aspose.PDF-dokumentation](https://reference.aspose.com/pdf/net/).