---
title: Ta bort formulärfält
linktitle: Ta bort formulärfält
second_title: Aspose.PDF för .NET API Referens
description: Ta enkelt bort oönskade formulärfält från dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-forms/delete-form-field/
---

I den här handledningen kommer vi att visa dig hur du tar bort ett formulärfält med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

Öppna det befintliga PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Steg 3: Ta bort ett visst fält

Ta bort ett visst formulärfält med dess namn:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Steg 4: Spara det redigerade dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ta bort formulärfält med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Ta bort ett visst fält efter namn
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Spara ändrat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man tar bort ett formulärfält med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt ta bort oönskade formulärfält från dina PDF-dokument med Aspose.PDF.