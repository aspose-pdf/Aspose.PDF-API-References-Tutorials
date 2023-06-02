---
title: Få värden från alla fält
linktitle: Få värden från alla fält
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt värdena för alla formulärfält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-forms/get-values-from-all-fields/
---

I den här handledningen kommer vi att visa dig hur du får värdena för alla formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna dokumentet

Öppna PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Steg 3: Hämta värden för alla fält

Gå igenom alla formulärfält i dokumentet och få deras namn och värden:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Exempel på källkod för Hämta värden från alla fält med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Få värden från alla fält
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Slutsats

den här handledningen lärde vi oss hur man får värdena för alla formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera värdena för alla formulärfält från dina PDF-dokument med Aspose.PDF.