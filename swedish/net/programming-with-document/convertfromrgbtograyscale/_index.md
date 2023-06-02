---
title: Konvertera från RGB till gråskala
linktitle: Konvertera från RGB till gråskala
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du konverterar PDF-filer från RGB till gråskala med Aspose.PDF för .NET. Förbättra utskriftskvaliteten och minska filstorleken.
type: docs
weight: 60
url: /sv/net/programming-with-document/convertfromrgbtograyscale/
---

I den här handledningen guidar vi dig genom processen att konvertera ett PDF-dokument från RGB-färgrymd till gråskala med Aspose.PDF för .NET. Denna konvertering kan vara användbar för olika ändamål, som att minska filstorleken eller förbereda dokument för utskrift. Följ steg-för-steg-guiden nedan:

## Steg 1: Ladda käll-PDF-filen

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Din kod här...
}
```

## Steg 2: Ställ in konverteringsstrategin

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Steg 3: Konvertera varje sida till gråskala

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Steg 4: Spara den resulterande filen

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Grattis! Du har framgångsrikt konverterat PDF-dokumentet från RGB till gråskala med Aspose.PDF för .NET.

### Exempel på källkod för konvertera från RGB till gråskala med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda käll-PDF-fil
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Nu kan du enkelt konvertera dina PDF-dokument från RGB till gråskala med Aspose.PDF för .NET.

