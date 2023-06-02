---
title: Ställ in egenskaper för utskriftsdialog
linktitle: Ställ in egenskaper för utskriftsdialog
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in egenskaper för utskriftsdialog i Aspose.PDF för .NET med hjälp av en steg-för-steg-guide.
type: docs
weight: 320
url: /sv/net/programming-with-document/setpropertiesforprintdialog/
---
här är en steg-för-steg-guide för att ställa in egenskaper för utskriftsdialogrutan med Aspose.PDF för .NET:


## Steg 1: Definiera katalogen där ditt PDF-dokument finns:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Steg 2: Skapa en ny instans av`Document` class:

```csharp
using (Document doc = new Document())
{
  // Kod här
}
```
   
## Steg 3: Lägg till en ny sida i dokumentet:

```csharp
doc.Pages.Add();
```
   
##  Steg 4: Ställ in duplexegenskapen till`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Steg 5: Spara dokumentet med angivet filnamn och format:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### Exempel på källkod för Set Properties For Print Dialog med Aspose.PDF för .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## Slutsats

Aspose.PDF för .NET gör det enkelt att ställa in egenskaper för utskriftsdialogrutan i dina PDF-filer. Genom att följa steg-för-steg-guiden ovan kan du snabbt optimera dina PDF-filer för utskrift.