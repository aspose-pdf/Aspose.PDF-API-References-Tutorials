---
title: Få värde från fält i PDF-dokument
linktitle: Få värde från fält i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt värdet av ett formulärfält i PDF-dokument med Aspose.PDF för .NET.
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

I den här handledningen lärde vi oss hur man får värdet av ett formulärfält med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera värdet av ett specifikt formulärfält i dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Kan jag få värdet på ett formulärfält utan att veta dess namn i förväg?

 S: Nej, du måste känna till namnet eller delnamnet på formulärfältet för att få dess värde med Aspose.PDF för .NET. De`pdfDocument.Form["fieldname"]` syntax kräver det exakta namnet eller delnamnet på formulärfältet för att komma åt dess egenskaper, inklusive värdet.

#### F: Vad händer om formulärfältet inte finns i PDF-dokumentet?

 S: Om formulärfältet inte finns i PDF-dokumentet,`pdfDocument.Form["fieldname"]` syntax kommer tillbaka`null` . Det är viktigt att hantera sådana fall genom att kontrollera`null` innan du kommer åt egenskaperna för formulärfältet för att undvika undantag.

#### F: Hur kan jag hantera olika typer av formulärfält (t.ex. kryssrutor, alternativknappar) för att få deras värden?

 S: För att hantera olika typer av formulärfält kan du använda lämpliga fältklasser som finns tillgängliga i Aspose.PDF för .NET. Använd till exempel`CheckBoxField` att arbeta med kryssrutor och`RadioButtonField`att arbeta med radioknappar. När du har rätt fältobjekt kan du komma åt dess egenskaper, inklusive värdet.

#### F: Kan jag få värdena för flera formulärfält samtidigt?

S: Ja, du kan få värden för flera formulärfält samtidigt genom att iterera genom samlingen av formulärfält med hjälp av en loop eller LINQ-frågor. På så sätt kan du komma åt värdet för varje formulärfält i PDF-dokumentet programmatiskt.

#### F: Är det möjligt att ändra värdet på ett formulärfält och spara ändringarna i PDF-dokumentet?

 S: Ja, du kan ändra värdet på ett formulärfält med Aspose.PDF för .NET och spara ändringarna i PDF-dokumentet. Efter att ha uppdaterat`Value` egenskapen för formulärfältet kan du använda`pdfDocument.Save()` metod för att spara ändringarna i det ursprungliga PDF-dokumentet.