---
title: Redigera sida
linktitle: Redigera sida
second_title: Aspose.PDF för .NET API-referens
description: Den här artikeln förklarar hur man redigerar en PDF-sida med Aspose.PDF för .NET, inklusive steg-för-steg-instruktioner och exempel på källkod.
type: docs
weight: 120
url: /sv/net/annotations/redactpage/
---
Om du vill redigera känslig information från ett PDF-dokument med Aspose.PDF för .NET, har du tur! Här är en steg-för-steg-guide för att komma igång:

## I koden anger du sökvägen till katalogen där ditt PDF-dokument finns:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Öppna PDF-dokumentet:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Skapa en RedactionAnnotation-instans för en specifik sidregion:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Ställ in fyllningsfärg, kantfärg och textfärg för redigeringskommentaren:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Ställ in texten som ska skrivas ut på redigeringskommentaren och dess justering:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Upprepa överläggstexten över redigeringskommentaren:

```csharp
annot.Repeat = true;
```

## Lägg till anteckningen i anteckningssamlingen på första sidan:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Platta ut annoteringen och redigera sidinnehållet, dvs. ta bort text och bilder under den redigerade anteckningen:

```csharp
annot.Redact();
```

## Ställ in sökvägen och namnet på den utgående PDF-filen:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Spara PDF-dokumentet med den redigerade sidan:

```csharp
doc.Save(dataDir);
```

Det är allt! Du har framgångsrikt redigerat en sida i ditt PDF-dokument med Aspose.PDF för .NET.

### Exempel på källkod för Redact Page med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document doc = new Document(dataDir + "input.pdf");

// Skapa RedactionAnnotation-instans för specifik sidregion
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Text som ska skrivas ut på redigera anteckning
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repetera överläggstext över redigera anteckning
annot.Repeat = true;
// Lägg till anteckningar i anteckningssamlingen på första sidan
doc.Pages[1].Annotations.Add(annot);
// Plattar till kommentarer och redigerar sidinnehåll (dvs. tar bort text och bild
// Under redigerad anteckning)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```