---
title: Ta bort teckensnitt och optimera PDF-filer
linktitle: Ta bort teckensnitt och optimera PDF-filer
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att få Unembed Fonts och optimera PDF-filer. En steg-för-steg-guide.
type: docs
weight: 370
url: /sv/net/programming-with-document/unembedfonts/
---
Aspose.PDF för .NET är ett kraftfullt bibliotek som ger ett brett utbud av funktioner för att arbeta med PDF-dokument. En av dess funktioner är att få inbäddade typsnitt från ett PDF-dokument. Detta kan vara användbart om du behöver extrahera teckensnitt från ett PDF-dokument och använda dem i andra applikationer.

vi kommer att tillhandahålla en steg-för-steg-guide för att förklara följande C#-källkod för get unembed fonts-funktionen i Aspose.PDF för .NET.

## Steg 1: Ställ in sökvägen till dokumentkatalogen

Innan vi börjar måste vi ställa in sökvägen till katalogen där vårt PDF-dokument finns. Vi kommer att lagra denna sökväg i en variabel som heter "dataDir".

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersätt "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 2: Öppna PDF-dokumentet

 Det första steget är att ladda PDF-dokumentet som du vill göra detta, använd`Document` klass av Aspose.PDF för .NET. Följande kodavsnitt visar hur du laddar PDF-dokumentet:

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Steg 3: Ställ in alternativet UnembedFonts

 För att få inbäddade teckensnitt från PDF-dokumentet måste du ställa in`UnembedFonts` möjlighet att`true` . Det här alternativet är tillgängligt i`OptimizationOptions` klass. Följande kodavsnitt visar hur du ställer in`UnembedFonts` alternativ:

```csharp
// Ställ in alternativet UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Steg 4: Optimera PDF-dokumentet

 Efter att ha ställt in`UnembedFonts` alternativet kan du optimera PDF-dokumentet med hjälp av`OptimizeResources` metod för`Document` klass. Följande kodavsnitt visar hur du optimerar PDF-dokumentet:

```csharp
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Steg 5: Spara det uppdaterade dokumentet

 När PDF-dokumentet är optimerat kan du spara det uppdaterade dokumentet med hjälp av`Save` metod för`Document`klass. Följande kodavsnitt visar hur du sparar det uppdaterade dokumentet:

```csharp
// Spara uppdaterat dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Steg 6: Skaffa den ursprungliga och reducerade filstorleken

 Slutligen kan du få den ursprungliga och reducerade filstorleken för PDF-dokumentet med hjälp av`FileInfo` klass av System.IO. Följande kodavsnitt visar hur du får den ursprungliga och reducerade filstorleken:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Exempel på källkod för Get Unembed Fonts med Aspose.PDF för .NET

Här är det kompletta exemplet på källkoden för att hämta inbäddade teckensnitt från ett PDF-dokument med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ställ in alternativet UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Spara uppdaterat dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Slutsats

I den här handledningen visade vi hur man använder Aspose.PDF för .NET för att hämta inbäddade teckensnitt från ett PDF-dokument. Genom att följa steg-för-steg-guiden kan du enkelt implementera den här funktionen i dina C#-applikationer. Att ta bort typsnitt kan vara fördelaktigt när du behöver arbeta med de extraherade typsnitten separat eller säkerställa konsekvent teckensnittsanvändning på olika plattformar.

## FAQ's

#### F: Vad är syftet med att ta bort typsnitt från ett PDF-dokument?

S: Om du tar bort teckensnitt från ett PDF-dokument kan du extrahera de inbäddade teckensnitten och använda dem i andra program. Detta kan vara användbart för att säkerställa konsekvent teckensnittsrendering och bevara dokumentets visuella utseende.

#### F: Hur anger jag sökvägen till dokumentkatalogen i C#-koden?

 S: För att ange sökvägen till dokumentkatalogen, ersätt`"YOUR DOCUMENT DIRECTORY"` i koden med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

####  F: Vad betyder`UnembedFonts` option do, and where is it set?

 A: Den`UnembedFonts` alternativ, tillgängligt i`OptimizationOptions` klass, aktiverar eller inaktiverar inbäddning av teckensnitt från PDF-dokumentet. För att ställa in detta alternativ till`true`, använd följande kod:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### F: Kan jag återställa ändringarna som gjordes under optimeringsprocessen?

S: Aspose.PDF för .NET gör inga permanenta ändringar i det ursprungliga PDF-dokumentet under optimering. Optimeringsprocessen utförs på en kopia av dokumentet och lämnar originalet intakt.

#### F: Hur kan jag kontrollera den ursprungliga och reducerade filstorleken efter optimering?

S: Du kan använda`FileInfo` klass av`System.IO` för att få den ursprungliga och reducerade filstorleken. Här är ett exempel på ett kodavsnitt för att uppnå detta:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```