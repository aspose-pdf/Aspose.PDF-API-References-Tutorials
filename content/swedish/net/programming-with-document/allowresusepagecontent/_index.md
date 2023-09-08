---
title: Tillåt återanvänd sidinnehåll
linktitle: Tillåt återanvänd sidinnehåll
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du optimerar PDF-filer genom att aktivera funktionen "Tillåt återanvänd sidinnehåll" med Aspose.PDF för .NET. Minska filstorleken och förbättra prestandan.
type: docs
weight: 50
url: /sv/net/programming-with-document/allowresusepagecontent/
---
den här handledningen kommer vi att förklara hur du aktiverar funktionen "Tillåt återanvänd sidinnehåll" med Aspose.PDF för .NET. Den här funktionen optimerar PDF-dokumentet genom att återanvända sidinnehåll, minska filstorleken och förbättra prestanda. Följ steg-för-steg-guiden nedan:

## Steg 1: Ladda PDF-dokumentet

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Steg 2: Ställ in alternativet AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Steg 3: Optimera PDF-dokumentet

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Steg 4: Spara det uppdaterade dokumentet

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Steg 5: Kontrollera filstorleksminskningen

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Grattis! Du har framgångsrikt tillåtit återanvändning av sidinnehåll i ditt PDF-dokument.

### Exempel på källkod för att tillåta återanvändning av sidinnehåll med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Ställ in alternativet AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Nu kan du effektivt optimera dina PDF-dokument genom att tillåta återanvändning av sidinnehåll.

## Slutsats

den här handledningen förklarade vi hur du aktiverar funktionen "Tillåt återanvända sidinnehåll" med Aspose.PDF för .NET. Genom att följa den medföljande steg-för-steg-guiden och använda C#-källkoden kan du effektivt optimera dina PDF-dokument genom att tillåta återanvändning av sidinnehåll. Denna optimering resulterar i mindre PDF-filer, vilket kan leda till snabbare laddningstider och förbättrad prestanda vid hantering av stora PDF-dokument. Aspose.PDF för .NET tillhandahåller en robust och användarvänlig lösning för PDF-optimering, vilket gör att du enkelt kan skapa effektiva och högkvalitativa PDF-filer.

### FAQ's

#### F: Vad är syftet med att aktivera funktionen "Tillåt återanvänd sidinnehåll" i ett PDF-dokument?

S: Aktivering av funktionen "Tillåt återanvänd sidinnehåll" i ett PDF-dokument optimerar filen genom att återanvända sidinnehåll, vilket minskar filstorleken och förbättrar den övergripande prestandan. Denna optimering resulterar i mindre PDF-filer utan att kompromissa med innehållskvaliteten.

#### F: Hur fungerar funktionen "Tillåt återanvänd sidinnehåll"?

S: När funktionen "Tillåt återanvänd sidinnehåll" är aktiverad delas identiska sidobjekt i PDF-dokumentet och återanvänds istället för att dupliceras för varje förekomst. Denna delning av sidinnehåll minskar den totala filstorleken avsevärt.

#### F: Kan jag återställa optimeringen och återställa originaldokumentet?

S: Nej, när optimeringen med "Tillåt återanvänd sidinnehåll" har utförts och PDF-dokumentet har sparats är ändringarna permanenta. Det är tillrådligt att ha en säkerhetskopia av originaldokumentet innan du utför någon optimering.

#### F: Kommer aktivering av den här funktionen att påverka PDF-dokumentets visuella utseende eller innehåll?

S: Aktivering av funktionen "Tillåt återanvänd sidinnehåll" påverkar inte det visuella utseendet eller innehållet i PDF-dokumentet. Den optimerar enbart filens interna struktur för att minska redundans och förbättra effektiviteten.

#### F: Är Aspose.PDF för .NET en pålitlig lösning för PDF-optimering och -manipulation?

S: Ja, Aspose.PDF för .NET är ett pålitligt och funktionsrikt bibliotek för PDF-optimering och -manipulation. Det erbjuder omfattande alternativ för att optimera PDF-filer, inklusive att minska filstorleken, ta bort oanvända resurser och förbättra den övergripande prestandan.