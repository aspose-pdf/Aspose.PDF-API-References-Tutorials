---
title: Hämta fält från regionen
linktitle: Hämta fält från regionen
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt fält från en specifik region till dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 130
url: /sv/net/programming-with-forms/get-fields-from-region/
---

den här handledningen kommer vi att visa dig hur du får fälten för en specifik region i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-filen

Öppna PDF-filen:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Steg 3: Skapa ett rektangelobjekt för att avgränsa området

Skapa ett rektangelobjekt för att avgränsa regionen där du vill hämta fälten:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Steg 4: Skaffa PDF-formuläret

Hämta PDF-formuläret för dokumentet:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Steg 5: Hämta fälten i det rektangulära området

Hämta fälten i det angivna rektangulära området:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Steg 6: Visa fältnamn och värden

Iterera genom de resulterande fälten och visa deras namn och värden:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Exempel på källkod för Get Fields From Region med Aspose.Words för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna pdf-fil
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Skapa rektangelobjekt för att få fält i det området
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Hämta PDF-formuläret
Aspose.Pdf.Forms.Form form = doc.Form;
//Få fält i det rektangulära området
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visa fältnamn och värden
foreach (Field field in fields)
{
	// Visa bildplaceringsegenskaper för alla placeringar
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man hämtar fälten för en specifik region i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera fälten som finns i ett givet rektangulärt område av ditt PDF-dokument med hjälp av Aspose.PDF.