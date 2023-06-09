---
title: Uppdatera länkar
linktitle: Uppdatera länkar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du uppdaterar länkar i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-links-and-actions/update-links/
---

Lär dig hur du uppdaterar länkar i en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

## Steg 1: Sätta upp miljön

Se till att du har konfigurerat din utvecklingsmiljö med ett C#-projekt och lämpliga Aspose.PDF-referenser.

## Steg 2: Laddar PDF-filen

Ställ in katalogsökvägen för dina dokument och ladda upp PDF-filen med följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda PDF-filen
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Steg 3: Redigera länken

Få länkkommentaren att ändra med följande kod:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Du kan justera`[1]` index för att välja en specifik sida eller anteckning.

Ändra sedan länken genom att ändra destinationen:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

Den första parametern representerar dokumentets ämne, den andra är målsidans nummer. Det femte argumentet är zoomfaktorn vid visning av respektive sida. När den är inställd på 2 kommer sidan att visas med 200 % zoom.

## Steg 4: Spara dokumentet med den uppdaterade länken

Spara dokumentet med den uppdaterade länken med hjälp av`Save` metod:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Steg 5: Visar resultatet

Visa ett meddelande som indikerar att länkarna har uppdaterats och ange platsen för den sparade filen:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Exempel på källkod för uppdateringslänkar med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda PDF-filen
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Få den första länkanteckningen från första sidan i dokumentet
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Ändringslänk: ändra länkdestination
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Ange destinationen för länkobjektet
	// Den första parametern är dokumentobjekt, den andra är destinationssidans nummer.
	// Argumentet 5ht är zoomfaktor vid visning av respektive sida. När du använder 2 kommer sidan att visas med 200 % zoom
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Spara dokumentet med uppdaterad länk
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

Grattis! Du vet nu hur du uppdaterar länkar i en PDF-fil med Aspose.PDF för .NET. Använd denna kunskap för att anpassa länkar i dina PDF-dokument och skapa interaktiva upplevelser för användarna.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.