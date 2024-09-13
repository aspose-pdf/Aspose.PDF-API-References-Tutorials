---
title: Skapa fylld rektangel
linktitle: Skapa fylld rektangel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar en fylld rektangel i en PDF med Aspose.PDF för .NET med denna steg-för-steg handledning. Perfekt för utvecklare på alla nivåer.
type: docs
weight: 50
url: /sv/net/programming-with-graphs/create-filled-rectangle/
---
## Introduktion

Har du någonsin velat skapa visuellt tilltalande PDF-filer programmatiskt? I så fall är du på rätt plats! I den här handledningen kommer vi att dyka in i världen av Aspose.PDF för .NET, ett kraftfullt bibliotek som låter dig manipulera PDF-dokument med lätthet. Idag kommer vi att fokusera på att skapa en fylld rektangel i en PDF-fil. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att leda dig genom varje steg på ett vänligt och engagerande sätt. Så ta tag i din kodningshatt och låt oss komma igång!

## Förutsättningar

Innan vi går in i koden finns det några saker du måste ha på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på din dator. Det är en fantastisk IDE för .NET-utveckling.
2.  Aspose.PDF för .NET: Du måste ladda ner och installera Aspose.PDF-biblioteket. Du kan hitta den[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper om C#: Lite bekantskap med C#-programmering hjälper dig att förstå kodavsnitten bättre.

## Importera paket

För att komma igång måste du importera nödvändiga paket i ditt C#-projekt. Så här kan du göra det:

### Skapa ett nytt projekt

Öppna Visual Studio och skapa ett nytt C#-projekt. Du kan välja en konsolapplikation för enkelhetens skull.

### Lägg till Aspose.PDF-referens

1. Högerklicka på ditt projekt i Solution Explorer.
2. Välj "Hantera NuGet-paket."
3. Sök efter "Aspose.PDF" och installera den senaste versionen.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nu när vi har allt inrättat, låt oss dyka in i koden!

## Steg 1: Konfigurera din dokumentkatalog

Först och främst måste du ange sökvägen där din PDF ska sparas. Detta är avgörande eftersom det talar om för programmet var filen ska skapas.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen på din maskin där du vill spara PDF:en.

## Steg 2: Skapa en dokumentinstans

 Därefter skapar vi en instans av`Document`klass. Den här klassen representerar PDF-dokumentet du kommer att arbeta med.

```csharp
// Skapa dokumentinstans
Document doc = new Document();
```

Den här raden initierar ett nytt PDF-dokument som vi kan manipulera.

## Steg 3: Lägg till en sida i dokumentet

Låt oss nu lägga till en sida i vårt dokument. Varje PDF-fil behöver minst en sida, eller hur?

```csharp
// Lägg till sida till sidor samling av PDF-fil
Page page = doc.Pages.Add();
```

Den här koden lägger till en ny sida i dokumentet, så att vi kan rita former på det.

## Steg 4: Skapa en grafinstans

 För att rita former måste vi skapa en`Graph` exempel. Se en graf som en duk där du kan rita olika former.

```csharp
// Skapa Graph-instans
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Här skapar vi en graf med en bredd på 100 och en höjd på 400.

## Steg 5: Lägg till grafen på sidan

Nu när vi har vår graf, låt oss lägga till den på sidan vi skapade tidigare.

```csharp
// Lägg till grafobjekt till styckesamling av sidinstanser
page.Paragraphs.Add(graph);
```

Denna linje fäster grafen på sidan, vilket gör den redo för ritning.

## Steg 6: Skapa en rektangelinstans

Därefter skapar vi en rektangel som vi vill fylla med färg.

```csharp
// Skapa rektangelinstans
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

I den här koden definierar vi rektangelns position och storlek. Parametrarna representerar x- och y-koordinaterna, bredd och höjd.

## Steg 7: Ange fyllningsfärg

Låt oss nu välja en färg för vår rektangel. Vi fyller den med rött för det här exemplet.

```csharp
// Ange fyllningsfärg för Graph-objektet
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Denna linje ställer in fyllningsfärgen för rektangeln till röd. Du kan välja vilken färg du vill!

## Steg 8: Lägg till rektangeln i grafen

Med vår rektangel redo är det dags att lägga till den i grafen.

```csharp
// Lägg till rektangelobjekt i formsamlingen av Graph-objekt
graph.Shapes.Add(rect);
```

Denna kod lägger till rektangeln till grafen, vilket gör den till en del av vår ritning.

## Steg 9: Spara PDF-dokumentet

Slutligen måste vi spara vårt dokument i den angivna katalogen.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
```

 Denna kod sparar PDF-filen med namnet`CreateFilledRectangle_out.pdf` i katalogen du angav tidigare.

## Steg 10: Bekräftelsemeddelande

För att låta oss veta att allt gick smidigt kan vi skriva ut ett bekräftelsemeddelande.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Den här raden kommer att mata ut ett meddelande i konsolen som bekräftar att den fyllda rektangeln har skapats framgångsrikt.

## Slutsats

Och där har du det! Du har framgångsrikt skapat en fylld rektangel i ett PDF-dokument med Aspose.PDF för .NET. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för PDF-manipulering, så att du kan skapa fantastiska dokument programmatiskt. Oavsett om du genererar rapporter, fakturor eller någon annan typ av PDF, har Aspose.PDF dig täckt.

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument programmatiskt.

### Kan jag använda Aspose.PDF gratis?
 Ja, Aspose erbjuder en gratis testversion som du kan använda för att utforska bibliotekets funktioner. Du kan ladda ner den[här](https://releases.aspose.com/).

### Finns det något sätt att få support för Aspose.PDF?
 Absolut! Du kan få support via Aspose-forumet[här](https://forum.aspose.com/c/pdf/10).

### Hur kan jag köpa Aspose.PDF?
 Du kan köpa Aspose.PDF genom att besöka köpsidan[här](https://purchase.aspose.com/buy).

### Vilka typer av former kan jag skapa med Aspose.PDF?
Du kan skapa olika former, inklusive rektanglar, cirklar, linjer och mer, med hjälp av biblioteket Aspose.PDF.