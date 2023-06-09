---
title: Få värde från fältet
linktitle: Få värde från fältet
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt värdet av ett formulärfält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-forms/get-value-from-field/
---

I den här handledningen kommer vi att visa dig hur du får värdet av ett formulärfält med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna dokumentet

Öppna PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Steg 3: Hämta Field

Hämta önskat formulärfält (i det här exemplet använder vi fältet "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Steg 4: Hämta fältvärde

 Få fältvärdet med hjälp av`Value` fast egendom:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Exempel på källkod för Get Value From Field med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Skaffa ett fält
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Få fältvärde
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Slutsats

den här handledningen lärde vi oss hur man får värdet av ett formulärfält med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera värdet av ett specifikt formulärfält i dina PDF-dokument med Aspose.PDF.