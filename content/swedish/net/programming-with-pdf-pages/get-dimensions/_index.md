---
title: Hämta PDF-sidans dimensioner
linktitle: Hämta PDF-sidans dimensioner
second_title: Aspose.PDF för .NET API Referens
description: I den här handledningen förklarar vi hur man får PDF-sidadimensioner och utför manipulationer med Aspose.PDF för .NET. Detaljerade steg tillhandahålls för att guida dig genom processen.
type: docs
weight: 60
url: /sv/net/programming-with-pdf-pages/get-dimensions/
---
den här handledningen går vi igenom steg-för-steg-processen för att få siddimensioner i en PDF-fil med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du får dimensionerna på en sida i en PDF-fil med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där din PDF-fil finns. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet
 Sedan kan du öppna PDF-filen med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt sökväg till PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Steg 3: Lägg till en tom sida (om det behövs)
 Om PDF-dokumentet redan innehåller sidor kan du hoppa till en befintlig sida med hjälp av indexet`1` (första sidan har ett index på 1). Annars kan du lägga till en ny sida i dokumentet.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Steg 4: Få sidmått
 Du kan nu få sidmåtten med hjälp av`GetPageRect()` metod för`Page` objekt. Denna metod returnerar en`Rectangle` objekt som innehåller sidans dimensioner. Du kan komma åt bredd och höjd med hjälp av`Width` och`Height` egenskaper.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Steg 5: Rotera sidan
 Om du vill rotera sidan kan du använda`Rotate` egendom av`Page`objekt. I det här exemplet roteras sidan 90 grader.

```csharp
page. Rotate = Rotate. on90;
```

## Steg 6: Få sidmått igen
 Efter sidrotation kan du få sidmåtten igen med hjälp av`GetPageRect()` metod.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Exempel på källkod för Get Dimensions med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Lägger till en tom sida till pdf-dokument
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Få information om sidhöjd och bredd
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Rotera sidan i 90 graders vinkel
page.Rotate = Rotation.on90;
// Få information om sidhöjd och bredd
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Slutsats
I den här handledningen lärde vi oss hur man får dimensionerna på en sida i en PDF-fil med Aspose.PDF för .NET. Genom att följa de angivna stegen kan du enkelt extrahera siddimensioner och utföra andra PDF-manipuleringsoperationer. Aspose.PDF för .NET erbjuder stor flexibilitet för att arbeta med PDF-filer och låter dig utveckla kraftfulla och skräddarsydda lösningar.

Utforska gärna dokumentationen för Aspose.PDF ytterligare för att upptäcka alla funktioner som erbjuds av detta bibliotek.

### Vanliga frågor om mått på PDF-sidor

#### F: Hur kan jag få mått på en specifik sida i en PDF-fil?

S: För att få måtten på en specifik sida i en PDF-fil kan du använda`GetPageRect()` metod för`Page` objekt i Aspose.PDF för .NET. Denna metod returnerar en`Rectangle` objekt som innehåller dimensionerna (bredd och höjd) på sidan.

####  F: Vad betyder`GetPageRect(true)` method do in the provided C# source code?

 A: Den`GetPageRect(true)` metod i den medföljande C#-källkoden returnerar sidans dimensioner efter att ha tillämpat eventuella rotationer. Om sidan roteras kommer metoden att returnera dimensionerna för den roterade sidan, som kan skilja sig från de ursprungliga måtten.

#### F: Kan jag få mått på alla sidor i PDF-dokumentet med Aspose.PDF för .NET?

 S: Ja, du kan få måtten på alla sidor i PDF-dokumentet genom att iterera genom`Pages` samling av`Document` objekt och använda`GetPageRect(true)` metod för varje sida.

#### F: Hur kan jag bestämma orienteringen för en sida (stående eller liggande) baserat på dess dimensioner?

S: För att bestämma orienteringen på en sida baserat på dess dimensioner kan du jämföra sidans bredd och höjd. Om bredden är större än höjden är sidan i liggande riktning, och om höjden är större än bredden är sidan i stående riktning.

#### F: Kan jag ändra dimensionerna på en sida med Aspose.PDF för .NET?

 S: Ja, du kan ändra dimensionerna på en sida i Aspose.PDF för .NET. Efter att ha fått`Rectangle` objekt som representerar sidmåtten kan du justera bredd och höjd enligt dina krav och sedan tillämpa ändringarna på sidan.