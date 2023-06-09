---
title: CGM till PDF
linktitle: CGM till PDF
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt CGM-filer till PDF med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/document-conversion/cgm-to-pdf/
---

I denna handledning guidar vi dig steg för steg för att konvertera CGM till PDF med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och tillhandahålla steg-för-steg-instruktioner för att hjälpa dig att följa med på ett enkelt sätt.

## Introduktion

Genom att konvertera en CGM-fil till PDF kan du dela och se dina tekniska ritningar universellt. Med Aspose.PDF för .NET kan du enkelt utföra denna konvertering och få högkvalitativa PDF-filer.

## Miljöinställning

Innan du börjar, se till att du har konfigurerat din utvecklingsmiljö för att fungera med Aspose.PDF för .NET. Följ stegen nedan:

1. Installera Visual Studio eller annan IDE som är kompatibel med C#-utveckling.
2. Skapa ett nytt C#-projekt.
3. Installera Aspose.PDF för .NET-paketet via NuGet för att lägga till nödvändiga beroenden.

## Konvertera CGM-fil till PDF

Följ dessa steg för att konvertera en CGM-fil till PDF:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera ett LoadOption-objekt med CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instantiera ett dokumentobjekt
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Spara det resulterande PDF-dokumentet
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 Se till att ersätta i koden ovan`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där din CGM-fil som ska konverteras finns. Denna kod laddar CGM-filen med hjälp av`CgmLoadOptions` klass och skapar sedan ett PDF-dokument med hjälp av`Document` objekt. Slutligen sparas det resulterande PDF-dokumentet.

### Exempel på källkod för CGM till PDF med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera LoadOption-objekt med CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instantiera dokumentobjekt
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Spara det resulterande PDF-dokumentet
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Slutsats

Grattis! Nu vet du hur man konverterar en CGM-fil till PDF med Aspose.PDF för .NET. Vi har gått igenom varje steg i processen, från initialisering av CGM-laddningsalternativen till att spara det resulterande PDF-dokumentet. Använd de medföljande kodexemplen för att integrera denna funktion i dina egna projekt. Experimentera med Aspose.PDF för .NET och upptäck de utökade möjligheterna att manipulera PDF-filer.
