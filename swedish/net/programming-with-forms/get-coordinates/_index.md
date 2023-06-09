---
title: Få koordinater
linktitle: Få koordinater
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt formulärfältskoordinater i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-forms/get-coordinates/
---

I den här handledningen kommer vi att visa dig hur du får formulärfältskoordinater med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ställ in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda utdokumentet

Ladda ut PDF-dokumentet:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Steg 3: Hitta tillagda fält

Hitta de tillagda formulärfälten (i det här exemplet använder vi fälten "Artikel1", "Artikel2" och "Artikel3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Steg 4: Visa underpostpositioner för varje fält

Bläddra igenom alternativen för varje fält och se koordinaterna för varje underpost:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Exempel på källkod för Get Coordinates med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda utmatningsdokumentet
	Document doc1 = new Document( dataDir + "input.pdf");
	// Hitta tillagda fält
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Och visa positioner för underobjekt för var och en av dem.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man får formulärfältskoordinater med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt hämta koordinaterna för dina formulärfälts underelement i dina PDF-dokument med Aspose.PDF.