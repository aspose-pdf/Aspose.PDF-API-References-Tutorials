---
title: Få PDF-formulärfältkoordinater
linktitle: Få PDF-formulärfältkoordinater
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt PDF-formulärfältkoordinater i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-forms/get-coordinates/
---
I den här handledningen kommer vi att visa dig hur du får PDF-formulärfältkoordinater med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ställ in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda ut dokumentet

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

### FAQ's

#### F: Kan jag använda den här metoden för att få koordinater för alla typer av formulärfält i Aspose.PDF för .NET?

S: Ja, du kan använda den här metoden för att få koordinater för olika typer av formulärfält i Aspose.PDF för .NET. Den medföljande C#-källkoden visar hur man får koordinater för RadioButton-fält, men du kan anpassa samma tillvägagångssätt för andra formulärfältstyper, såsom TextBox, CheckBox, ListBox och mer.

#### F: Hur kan jag ändra eller justera formulärfältets koordinater?

S: Formulärfältskoordinater är baserade på PDF-dokumentets koordinatsystem, där ursprunget (0,0) finns i det nedre vänstra hörnet på sidan. För att ändra eller justera formulärfältets koordinater kan du uppdatera`Rect` egenskapen för respektive formulärfält eller dess underobjekt, såsom RadioButtonOptionField.

#### F: Kan jag lägga till koordinaterna för formulärfält programmatiskt till ett PDF-dokument?

S: Ja, du kan få koordinaterna för formulärfält som lades till programmatiskt till ett PDF-dokument. Aspose.PDF för .NET låter dig lägga till formulärfält dynamiskt, och när de väl har lagts till kan du hämta deras koordinater med det tillvägagångssätt som visas i denna handledning.

#### F: Vad är syftet med att hämta formulärfältskoordinater?

S: Att hämta formulärfältskoordinater kan vara till hjälp när du behöver utföra specifika layoutrelaterade operationer eller valideringar på formulärfält i ett PDF-dokument. Det låter dig positionera och justera formulärfält exakt baserat på deras koordinater, vilket säkerställer att de visas korrekt i dokumentet och ger en sömlös användarupplevelse.

#### F: Är formulärfältets koordinater uttryckta i punkter eller en annan enhet?

S: Formulärfältets koordinater i Aspose.PDF för .NET uttrycks i punkter. En punkt motsvarar 1/72 tum, vilket gör den till en standardmåttenhet i PDF-format.