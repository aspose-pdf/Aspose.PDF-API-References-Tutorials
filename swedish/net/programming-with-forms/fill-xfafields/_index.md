---
title: Fyll XFAFields
linktitle: Fyll XFAFields
second_title: Aspose.PDF för .NET API Referens
description: Fyll enkelt XFA-fält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-forms/fill-xfafields/
---

I den här handledningen kommer vi att visa dig hur du fyller i XFA-fält med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda XFA-formuläret

Ladda XFA-formuläret:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Steg 3: Skaffa XFA-fältnamn

Hämta formulärets XFA-fältnamn:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Steg 4: Ställ in fältvärden

Ställ in XFA-fältvärdena med hjälp av namnen som erhölls tidigare:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Steg 5: Spara det uppdaterade dokumentet

Spara det uppdaterade PDF-dokumentet:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Fyll XFAFields med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda XFA-formuläret
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//Hämta namn på XFA-formulärfält
string[] names = doc.Form.XFA.FieldNames;
// Ställ in fältvärden
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Spara det uppdaterade dokumentet
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man fyller i XFA-fält med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt ändra värdena för XFA-fält i dina PDF-dokument med Aspose.PDF.