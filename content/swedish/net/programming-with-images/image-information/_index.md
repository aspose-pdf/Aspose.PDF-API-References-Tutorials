---
title: Bildinformation i PDF-fil
linktitle: Bildinformation i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig att extrahera bildinformation från PDF-filer med Aspose.PDF för .NET med vår omfattande steg-för-steg-guide.
type: docs
weight: 160
url: /sv/net/programming-with-images/image-information/
---
## Introduktion

PDF-filer finns överallt nuförtiden – praktiskt taget alla professionella och personliga dokument hittar någon gång till det här formatet. Oavsett om det är en rapport, en broschyr eller en e-bok, att förstå hur man interagerar med dessa filer programmatiskt erbjuder en myriad av möjligheter. Ett vanligt krav är att extrahera bildinformation från PDF-filer. I den här guiden kommer vi att dyka ner i hur du använder Aspose.PDF-biblioteket för .NET för att extrahera viktiga detaljer om bilder inbäddade i ett PDF-dokument.

## Förutsättningar

Innan vi går in i det snåriga med kodning finns det några förutsättningar som du måste ha på plats:

1. Utvecklingsmiljö: Du behöver en .NET-utvecklingsmiljö. Detta kan vara Visual Studio eller någon annan .NET-kompatibel IDE.
2.  Aspose.PDF-bibliotek: Se till att du har tillgång till Aspose.PDF-biblioteket. Du kan ladda ner den från[Aspose hemsida](https://releases.aspose.com/pdf/net/). 
3. Grundläggande C#-kunskaper: Bekantskap med C# och objektorienterade programmeringskoncept hjälper dig att följa handledningen utan ansträngning.
4. PDF-dokument: Ha ett exempel på PDF-dokument till hands som innehåller bilder för att testa din kod. 

## Importera paket

För att komma igång med att använda Aspose.PDF-biblioteket måste du importera de nödvändiga namnområdena till din C#-fil. Här är en snabb sammanfattning:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Dessa namnområden ger dig tillgång till de klasser och metoder som krävs för att manipulera PDF-filer och extrahera bilddata.

Nu när du har ställt in allt är det dags att dela upp detta i hanterbara steg. Vi kommer att skriva ett C#-program som laddar ett PDF-dokument, går igenom varje sida och extraherar måtten och upplösningen för varje bild i dokumentet.

## Steg 1: Initiera dokumentet

 I det här steget kommer vi att initiera PDF-dokumentet med hjälp av sökvägen till din PDF-fil. Du bör byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där din PDF-fil finns.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda käll-PDF-filen
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Vi skapar en`Document` objekt som laddar PDF-filen från den angivna katalogen. Detta gör att vi kan arbeta med innehållet i filen.

## Steg 2: Ställ in standardupplösning och initiera datastrukturer

Därefter ställer vi in en standardupplösning för bilderna, vilket är användbart för beräkningar. Vi kommer också att förbereda en array för bildnamn och en stack för att hantera grafiska tillstånd.

```csharp
// Definiera standardupplösningen för bilden
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definiera arraylistobjekt som kommer att innehålla bildnamn
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 De`defaultResolution` variabel hjälper oss att beräkna upplösningen på bilder korrekt. De`graphicsState`stack fungerar som ett sätt att lagra det aktuella grafiska tillståndet för dokumentet när vi stöter på transformationsoperatorer.

## Steg 3: Bearbeta varje operatör på sidan

Vi går nu igenom alla operatorer på dokumentets första sida. Det är här de tunga lyften sker. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Processoperatörer...
}
```
Varje operatör i en PDF-fil är ett kommando som talar om för renderaren hur man hanterar grafiska element, inklusive bilder.

## Steg 4: Hantera GSave/GRestore-operatörer

Inne i slingan kommer vi att hantera grafik spara och återställa kommandon för att hålla reda på ändringar som gjorts i det grafiska tillståndet.

```csharp
if (opSaveState != null) 
{
    // Spara tidigare tillstånd
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Återställ tidigare tillstånd
    graphicsState.Pop();
}
```
`GSave` sparar det aktuella grafiska tillståndet, medan`GRestore` återställer det senast sparade tillståndet, vilket gör att vi kan återställa alla transformationer vid bearbetning av bilder.

## Steg 5: Hantera transformationsmatriser

Därefter hanterar vi sammankopplingen av transformationsmatriser när vi tillämpar transformationer på bilder.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
När en transformationsmatris tillämpas multiplicerar vi den med den aktuella matrisen som är lagrad i det grafiska tillståndet så att vi kan hålla reda på eventuell skalning eller översättning som tillämpas på bilden.

## Steg 6: Extrahera bildinformation

Slutligen bearbetar vi ritoperatören för bilder och extraherar nödvändig information, som mått och upplösningar.

```csharp
else if (opDo != null) 
{
    // Handle Do-operatör som ritar objekt
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Mata ut informationen
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Här kontrollerar vi om operatören är ansvarig för att rita en bild. Om det är det, får vi motsvarande XImage-objekt, beräknar dess skalade dimensioner och upplösning och skriver ut nödvändig information.

## Slutsats

Grattis! Du har precis skapat ett fungerande exempel på hur man extraherar bildinformation från en PDF-fil med Aspose.PDF för .NET. Denna funktion kan vara otroligt användbar för utvecklare som behöver analysera eller manipulera PDF-dokument för olika applikationer, såsom rapportering, dataextraktion eller till och med anpassade PDF-visare. 


## FAQ's

### Vad är Aspose.PDF-biblioteket?
Aspose.PDF-biblioteket är ett kraftfullt verktyg för att skapa, manipulera och konvertera PDF-filer i .NET-applikationer.

### Kan jag använda biblioteket gratis?
 Ja, Aspose erbjuder en gratis provperiod. Du kan ladda ner den[här](https://releases.aspose.com/).

### Vilka typer av bildformat kan extraheras?
Biblioteket stöder olika bildformat, inklusive JPEG, PNG och TIFF, så länge de är inbäddade i PDF:en.

### Används Aspose för kommersiella ändamål?
 Ja, du kan använda Aspose-produkter kommersiellt. För licensiering, besök[köpsidan](https://purchase.aspose.com/buy).

### Hur får jag support för Aspose?
 Du kan komma åt supportforumet[här](https://forum.aspose.com/c/pdf/10).