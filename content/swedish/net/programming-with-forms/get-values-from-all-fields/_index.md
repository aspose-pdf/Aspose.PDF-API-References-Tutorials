---
title: Få värden från alla fält i PDF-dokument
linktitle: Få värden från alla fält i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt värdena för alla formulärfält i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-forms/get-values-from-all-fields/
---
den här handledningen kommer vi att visa dig hur du får värdena för alla formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

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

### Exempel på källkod för Hämta värden från alla fält med Aspose.PDF för .NET 
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

I den här handledningen lärde vi oss hur man får värdena för alla formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera värdena för alla formulärfält från dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Kan jag ändra värdena för formulärfält samtidigt som jag hämtar dem med Aspose.PDF för .NET?

 S: Ja, du kan ändra värdena för formulärfält samtidigt som du hämtar dem med Aspose.PDF för .NET. När du väl har`Field` objekt som representerar ett formulärfält, kan du uppdatera dess`Value`fastighet med önskat värde. När du har gjort de nödvändiga ändringarna kan du spara det uppdaterade PDF-dokumentet för att återspegla ändringarna.

#### F: Hur kan jag filtrera och hämta specifika formulärfält baserat på deras typer (t.ex. textfält, kryssrutor)?

 S: För att hämta specifika formulärfält baserat på deras typer, kan du använda villkorssatser eller LINQ-frågor för att filtrera de intressanta fälten. Du kan kontrollera typen av varje formulärfält med hjälp av fältets`FieldType` egendom och hämta sedan värdena därefter.

#### F: Vad händer om PDF-dokumentet inte har några formulärfält?

 S: Om PDF-dokumentet inte innehåller några formulärfält,`pdfDocument.Form` egendom kommer att returnera en tom samling. I sådana fall kommer slingan för att hämta värden inte att köras, och inga värden kommer att visas.

#### F: Kan jag extrahera formulärfältsvärdena i en specifik ordning eller sortera dem alfabetiskt?

S: Ordningen i vilken formulärfälten hämtas beror på PDF-dokumentets underliggande struktur. Aspose.PDF för .NET returnerar formulärfälten i den ordning de lades till dokumentet. Om du vill visa eller bearbeta formulärfälten i en specifik ordning kan du implementera anpassad sorteringslogik baserat på dina krav.

#### F: Hur kan jag hantera krypterade PDF-dokument med lösenordsskyddade formulärfält?

 S: Aspose.PDF för .NET tillhandahåller funktioner för att arbeta med krypterade PDF-dokument och lösenordsskyddade formulärfält. Innan du laddar dokumentet kan du ställa in lösenordet med hjälp av`pdfDocument.Password` egendom för att komma åt det säkrade PDF-dokumentet och dess formulärfält.