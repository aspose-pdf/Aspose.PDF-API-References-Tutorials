---
title: Välj alternativknapp i PDF-dokument
linktitle: Välj alternativknapp i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du väljer en alternativknapp i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 250
url: /sv/net/programming-with-forms/select-radio-button/
---
Här är en detaljerad handledning om hur du väljer en alternativknapp med Aspose.PDF för .NET. Följ dessa steg:

##  Steg 1: Börja med att definiera katalogen för dina dokument genom att ange sökvägen i`dataDir` variable.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Steg 2: Öppna PDF-dokumentet med hjälp av`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Steg 3: Hämta alternativknappsfältet från dokumentformuläret.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Steg 4: Ange index för alternativknappen att välja från gruppen.

```csharp
radioField. Selected = 2;
```

## Steg 5: Ställ in utdatasökvägen för den redigerade PDF-filen.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Steg 6: Spara den ändrade PDF-filen.

```csharp
pdfDocument.Save(dataDir);
```

## Steg 7: Visa ett bekräftelsemeddelande och platsen för den sparade filen.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Exempel på källkod för Välj radioknapp med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Skaffa ett fält
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Ange indexet för alternativknappen från gruppen
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Spara PDF-filen
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man väljer en alternativknapp med Aspose.PDF för .NET. Genom att följa stegen som beskrivs ovan kan du manipulera och ändra alternativknappar i dina PDF-dokument med Aspose.PDF för .NET.


### FAQ's

#### F: Kan jag välja flera alternativknappar i en grupp med Aspose.PDF för .NET?

S: Nej, alternativknappar i en grupp är utformade för att utesluta varandra. Du kan bara välja en alternativknapp åt gången inom en grupp, och om du väljer en avmarkeras alla tidigare valda alternativknappar i samma grupp automatiskt.

#### F: Hur hämtar jag den valda alternativknappen i en grupp med Aspose.PDF för .NET?

 S: För att hämta den valda alternativknappen i en grupp kan du använda`Selected` egendom av`RadioButtonField` klass. Det kommer att returnera indexet för den valda alternativknappen inom gruppen.

#### F: Kan jag anpassa utseendet på den valda alternativknappen i PDF-dokumentet?

S: Ja, du kan anpassa utseendet på den valda alternativknappen med Aspose.PDF för .NET. Du kan ändra dess färg, storlek, kantstil och andra visuella attribut för att matcha ditt önskade utseende.

#### F: Är det möjligt att skapa nya alternativknappsgrupper programmatiskt med Aspose.PDF för .NET?

S: Ja, du kan skapa nya alternativknappsgrupper programmatiskt med Aspose.PDF för .NET. Du kan lägga till nya alternativknappar i dokumentets formulär och ange samma gruppnamn för varje alternativknapp för att skapa en ny grupp.

#### F: Stöder Aspose.PDF för .NET arbete med interaktiva PDF-formulär?

S: Ja, Aspose.PDF för .NET stöder fullt ut arbete med interaktiva PDF-formulär, inklusive radioknappar, textfält, kryssrutor och andra formulärelement. Du kan enkelt läsa, ändra och skapa interaktiva PDF-formulär med hjälp av biblioteket.