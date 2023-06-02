---
title: Radio knapp
linktitle: Radio knapp
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till alternativknappar till dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 220
url: /sv/net/programming-with-forms/radio-button/
---

den här handledningen kommer vi att visa dig hur du lägger till en alternativknapp i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt

Instantiera ett dokumentobjekt för att skapa ett nytt PDF-dokument:

```csharp
Document pdfDocument = new Document();
```

## Steg 3: Lägg till en sida

Lägg till en sida i PDF-dokumentet:

```csharp
pdfDocument.Pages.Add();
```

## Steg 4: Instantiera ett RadioButtonField-objekt

Instantiera ett RadioButtonField-objekt som anger sidnumret som ett argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Steg 5: Lägg till alternativ för alternativknappar

Lägg till alternativknappsalternativ till RadioButtonField-objektet genom att ange koordinaterna för varje alternativ med ett Rectangle-objekt:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Steg 6: Lägg till alternativknappen i formuläret

Lägg till alternativknappen i dokumentets formulärobjekt:

```csharp
pdfDocument.Form.Add(radio);
```

## Steg 7: Spara PDF-dokumentet

Spara det skapade PDF-dokumentet:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för radioknapp med Aspose.Words för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantiera dokumentobjekt
	Document pdfDocument = new Document();
	// Lägg till en sida i PDF-filen
	pdfDocument.Pages.Add();
	// Instatera RadioButtonField-objekt med sidnummer som argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Lägg till första alternativknappsalternativet och ange även dess ursprung med Rectangle-objektet
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Lägg till andra alternativknapp
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Lägg till alternativknapp för att bilda objekt av dokumentobjekt
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Spara PDF-filen
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man lägger till en alternativknapp i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt skapa en alternativknapp och placera den på en specifik sida i ditt PDF-dokument.