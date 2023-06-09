---
title: Lägg till ritning
linktitle: Lägg till ritning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till ritningar med Aspose.PDF för .NET. Följ den här steg-för-steg-guiden för att skapa attraktiva PDF-dokument med ritfunktioner.
type: docs
weight: 10
url: /sv/net/programming-with-graphs/add-drawing/
---

Applikationsutveckling kräver ofta att man lägger till funktioner som ritningar och grafik för att göra dokument mer attraktiva och informativa. I den här artikeln kommer vi att guida dig steg för steg för att förklara C#-källkoden för att lägga till ritning till programmering med grafik med Aspose.PDF för .NET.

Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Se också till att du har grundläggande kunskaper i C#-programmering.

## Steg 1: Introduktion till Aspose.PDF för .NET och dess funktioner

Aspose.PDF är ett kraftfullt och mångsidigt bibliotek för att skapa, manipulera och konvertera PDF-filer i .NET-applikationer. Den erbjuder ett brett utbud av funktioner för att arbeta med PDF-dokument, inklusive att lägga till ritningar, grafik, text, etc.

## Steg 2: Förstå källkoden för att lägga till ritningar med Aspose.PDF

Den medföljande källkoden använder Aspose.PDF-biblioteket för att skapa en enkel ritning i ett PDF-dokument. Vi kommer nu att undersöka varje steg i koden i detalj.

## Steg 3: Konfigurera dokumentkatalogen och initiera variablerna

I källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Du kan ändra variabeln "dataDir" för att indikera önskad katalog.

Dessutom initierar koden variabler för färgkomponenterna alfa, röd, grön och blå.

## Steg 4: Skapa ett färgobjekt med Alpha RGB

Följande kodrad skapar ett färgobjekt med de angivna alfa-, röd-, grön- och blåvärdena:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

Detta gör det möjligt att definiera en färg med en alfakanal, vilket innebär att färgen kan vara delvis transparent.

## Steg 5: Instantiera ett dokumentobjekt

För att börja arbeta med Aspose.PDF måste vi skapa en instans av klassen Document. Detta representerar vårt PDF-dokument.

```csharp
Document document = new Document();
```

## Steg 6: Lägga till en sida i PDF-filen

Vi måste lägga till en sida i PDF-filen där vi vill visa vår ritning.

```csharp
Page page = document.Pages.Add();
```

## Steg 7: Skapa ett grafobjekt med dimensioner

I det här steget skapar vi ett Graph-objekt med specificerade dimensioner. Detta objekt kommer att fungera som en behållare för vår ritning.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## Steg 8: Ställ in gränsen för ritobjektet

Vi kan ställa in gränsen för Drawing-objektet med klassen BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

Detta kommer att sätta en svart ram runt vår ritning.

## Steg 9: Lägga till grafobjektet på sidan

Nu lägger vi till grafobjektet till styckesamlingen i klassen Page-instans.

```csharp
page.Paragraphs.Add(graph);
```

## Steg 10: Skapa ett rektangelobjekt med dimensioner

Vi skapar ett rektangelobjekt med specificerade mått. Denna rektangel kommer att läggas till vår ritning.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## Steg 11: Skapa ett GraphInfo-objekt för Rectangle-instansen

Vi måste skapa ett GraphInfo-objekt för Rectangle-instansen för att konfigurera dess grafegenskaper.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## Steg 12: Konfigurera färginformation för GraphInfo-objektet

Vi kan konfigurera färginformationen för GraphInfo-objektet med hjälp av egenskaperna Color och FillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

Detta kommer att ställa in rektangelns kantfärg till röd och fyllningsfärgen till den angivna alfafärgen.

## Steg 13: Lägga till rektangelformen till grafobjektet

Nu lägger vi till rektangelformen till formsamlingen för grafobjektet.

```csharp
graph.Shapes.Add(rectangle);
```
## Steg 14: Spara PDF-fil och visa framgångsmeddelande

Slutligen sparar vi PDF-filen och visar ett meddelande om att ritningen har lagts till.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### Exempel på källkod för Add Drawing med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// Skapa färgobjekt med Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // Tillhandahåll alfakanal
// Instantiera dokumentobjekt
Document document = new Document();
// Lägg till sida till sidor samling av PDF-fil
Page page = document.Pages.Add();
// Skapa Graph-objekt med vissa dimensioner
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// Ställ in ram för ritobjekt
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// Lägg till grafobjekt till styckesamlingen av sidinstansen
page.Paragraphs.Add(graph);
// Skapa rektangelobjekt med vissa dimensioner
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// Skapa graphInfo-objekt för Rectangle-instans
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// Ställ in färginformation för GraphInfo-instansen
graphInfo.Color = (Aspose.Pdf.Color.Red);
// Ställ in fyllningsfärg för GraphInfo
graphInfo.FillColor = (alphaColor);
// Lägg till rektangelform till formsamling av grafobjekt
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// Spara PDF-fil
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## Slutsats

I den här artikeln lärde vi oss hur man lägger till ritning i programmering med grafik med Aspose.PDF för .NET. Vi följde en steg-för-steg-guide för att förstå källkoden och de olika stegen som ingår i att lägga till en ritning till en PDF-fil. Med de kraftfulla funktionerna i Aspose.PDF kan du skapa attraktiva och interaktiva PDF-dokument i dina .NET-applikationer.