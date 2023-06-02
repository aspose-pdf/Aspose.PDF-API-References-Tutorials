---
title: Tillåt återanvänd sidinnehåll
linktitle: Tillåt återanvänd sidinnehåll
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du optimerar PDF-filer genom att aktivera funktionen "Tillåt återanvänd sidinnehåll" med Aspose.PDF för .NET. Minska filstorleken och förbättra prestandan.
type: docs
weight: 50
url: /sv/net/programming-with-document/allowresusepagecontent/
---

I den här handledningen kommer vi att förklara hur du aktiverar funktionen "Tillåt återanvänd sidinnehåll" med Aspose.PDF för .NET. Den här funktionen optimerar PDF-dokumentet genom att återanvända sidinnehåll, minska filstorleken och förbättra prestanda. Följ steg-för-steg-guiden nedan:

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
