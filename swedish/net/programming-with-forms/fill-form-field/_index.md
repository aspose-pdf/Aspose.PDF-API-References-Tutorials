---
title: Fyll i formulärfältet
linktitle: Fyll i formulärfältet
second_title: Aspose.PDF för .NET API Referens
description: Fyll enkelt i formulärfält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-forms/fill-form-field/
---

I den här handledningen kommer vi att visa dig hur du fyller i ett formulärfält med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

Öppna det befintliga PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Steg 3: Hämta Field

Hämta önskat formulärfält (i det här exemplet använder vi fältet "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Steg 4: Ändra fältvärdet

Ändra fältvärdet med önskat värde:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Steg 5: Spara det uppdaterade dokumentet

Spara det uppdaterade PDF-dokumentet:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Fyll i formulärfält med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Skaffa ett fält
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ändra fältvärdet
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man fyller i ett formulärfält med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt ändra formulärfältsvärden i dina PDF-dokument med Aspose.PDF.