---
title: Ändra formulärfält
linktitle: Ändra formulärfält
second_title: Aspose.PDF för .NET API Referens
description: Redigera enkelt formulärfält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-forms/modify-form-field/
---

I den här handledningen kommer vi att visa dig hur du redigerar ett formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Ladda det befintliga PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Steg 3: Hämta formulärfältet

Hämta formulärfältet du vill redigera:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Steg 4: Ändra fältvärdet

Ändra formulärfältets värde:

```csharp
textBoxField.Value = "New Value";
```

## Steg 5: Redigera fältegenskaper

Ändra ytterligare formulärfältegenskaper efter behov. Du kan till exempel göra det skrivskyddat:

```csharp
textBoxField.ReadOnly = true;
```

## Steg 6: Spara det redigerade dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ändra formulärfält med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Skaffa ett fält
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ändra fältvärdet
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man redigerar ett formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt navigera till ett specifikt fält, ändra dess värde och justera dess egenskaper efter behov.