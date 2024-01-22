---
title: Hämta fält från region i PDF-fil
linktitle: Hämta fält från region i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Få enkelt fält från en specifik region i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 130
url: /sv/net/programming-with-forms/get-fields-from-region/
---
I den här handledningen kommer vi att visa dig hur du får fälten för en specifik region i PDF-fil med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

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

### Exempel på källkod för Get Fields From Region med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna pdf-fil
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Skapa rektangelobjekt för att få fält i det området
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Hämta PDF-formuläret
Aspose.Pdf.Forms.Form form = doc.Form;
// Få fält i det rektangulära området
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visa fältnamn och värden
foreach (Field field in fields)
{
	// Visa bildplaceringsegenskaper för alla placeringar
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Slutsats

den här handledningen lärde vi oss hur man hämtar fälten för en specifik region i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt extrahera fälten som finns i ett givet rektangulärt område av ditt PDF-dokument med hjälp av Aspose.PDF.

### FAQ's

#### F: Kan jag använda den här metoden för att hämta fält från en icke-rektangulär region i ett PDF-dokument?

 S: Nej, den angivna metoden`GetFieldsInRect` är speciellt utformad för att hämta fält inom ett rektangulärt område i ett PDF-dokument. Om du behöver extrahera fält från en icke-rektangulär region, måste du implementera anpassad logik för att identifiera och extrahera fälten baserat på andra kriterier, såsom fältkoordinater eller namn.

#### F: Hur kan jag ändra storleken eller positionen för rektangeln för att få fält från en annan region?

 S: För att få fält från en annan region kan du ändra`Aspose.Pdf.Rectangle` objektets parametrar som används för att definiera den avgränsande rektangeln. De`Rectangle` konstruktorn tar fyra parametrar:`x`, `y`, `width` , och`height`som representerar de övre vänstra hörnets koordinater och rektangelns dimensioner. Om du justerar dessa parametrar ändras regionen från vilken fälten extraheras.

#### F: Vad händer om det inte finns några fält inom det angivna rektangulära området?

 S: Om det inte finns några fält inom det angivna rektangulära området,`GetFieldsInRect` metod returnerar en tom array. Du kan kontrollera längden på arrayen för att avgöra om det finns några fält inom regionen.

#### F: Kan jag hämta fält från överlappande regioner i ett PDF-dokument?

 S: Ja, du kan hämta fält från överlappande regioner i ett PDF-dokument genom att skapa flera`Aspose.Pdf.Rectangle` objekt och ringer till`GetFieldsInRect` metod för var och en av dem. Överlappande regioner kommer att hanteras oberoende, och du kommer att få separata uppsättningar av fält för varje region.

#### F: Är det möjligt att hämta fält från en specifik sida eller flera sidor i PDF-dokumentet?

S: Ja, du kan hämta fält från en specifik sida eller flera sidor i ett PDF-dokument. För att uppnå detta kan du ladda PDF-dokumentet, komma åt önskade sidor med hjälp av`doc.Pages` insamling och tillämpa sedan`GetFieldsInRect` metod för varje sidas specifika region.