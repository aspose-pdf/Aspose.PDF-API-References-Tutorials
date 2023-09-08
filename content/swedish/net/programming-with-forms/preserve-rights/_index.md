---
title: Bevara rättigheter
linktitle: Bevara rättigheter
second_title: Aspose.PDF för .NET API Referens
description: Bevara formulärrättigheter i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 210
url: /sv/net/programming-with-forms/preserve-rights/
---
I den här handledningen kommer vi att visa dig hur du bevarar formulärrättigheter i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna dokumentet

 Öppna PDF-källdokumentet med a`FileStream` med läs- och skrivtillstånd:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Steg 3: Redigera formulärfält

Gå igenom alla formulärfält i dokumentet och gör nödvändiga ändringar. I det här exemplet ändrar vi värdet på ett formulärfält som har "A1" i sitt namn:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Steg 4: Spara det uppdaterade dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
pdfDocument.Save();
```

##  Steg 5: Stäng`FileStream`

 Glöm inte att stänga`FileStream` invända när du är klar:

```csharp
fs. Close();
```

### Exempel på källkod för att bevara rättigheterna med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Läs käll-PDF-formuläret med FileAccess of Read and Write.
// Vi behöver ReadWrite-tillstånd eftersom efter ändring,
// Vi måste spara det uppdaterade innehållet i samma dokument/fil.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instantiera dokumentinstans
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Få värden från alla fält
foreach (Field formField in pdfDocument.Form)
{
	// Om fältets fullständiga namn innehåller A1, utför åtgärden
	if (formField.FullName.Contains("A1"))
	{
		// Cast formulärfält som TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Ändra fältvärdet
		textBoxField.Value = "Testing";
	}
}
// Spara det uppdaterade dokumentet i save FileStream
pdfDocument.Save();
// Stäng File Stream-objektet
fs.Close();
```

## Slutsats

I den här handledningen lärde vi oss hur man bevarar rättigheterna för ett formulär i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt komma åt formulärfält och göra specifika ändringar samtidigt som du behåller åtkomst- och skrivbehörigheter.


### FAQ's

#### F: Kan jag bevara rättigheterna för specifika formulärfält utan att påverka andra i PDF-dokumentet?

 S: Ja, genom att använda`FullName` egenskapen för formulärfälten kan du rikta in dig på specifika formulärfält för bevarande samtidigt som du lämnar andra opåverkade.

#### F: Kan jag bevara rättigheterna för ett formulär i ett lösenordsskyddat PDF-dokument?

S: Ja, Aspose.PDF för .NET tillåter dig att bevara rättigheterna till ett formulär även i lösenordsskyddade PDF-dokument, så länge du anger rätt lösenord för att komma åt och ändra filen.

#### F: Vad händer om jag försöker ändra formulärfält utan lämpliga åtkomsträttigheter?

S: Om du försöker ändra formulärfält utan lämpliga åtkomsträttigheter kommer ändringarna inte att sparas i PDF-dokumentet och du kan få ett undantag eller ett felmeddelande.

#### F: Är Aspose.PDF för .NET kompatibel med alla versioner av .NET Framework?

S: Ja, Aspose.PDF för .NET är kompatibel med alla versioner av .NET Framework, inklusive .NET Core och .NET Standard.

#### F: Kan jag bevara formulärrättigheter i ett PDF-dokument programmatiskt på andra programmeringsspråk än C#?

S: Ja, Aspose.PDF för .NET stöder olika programmeringsspråk, såsom VB.NET och ASP.NET, förutom C#.