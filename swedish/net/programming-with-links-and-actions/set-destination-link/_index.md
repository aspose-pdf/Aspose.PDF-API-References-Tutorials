---
title: Ställ in destinationslänk
linktitle: Ställ in destinationslänk
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in en mållänk i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-links-and-actions/set-destination-link/
---

Lär dig hur du ställer in en mållänk i en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

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

## Steg 3: Redigera destinationslänken

Få länkkommentaren att ändra med följande kod:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Du kan justera`[1]` index för att välja en specifik sida eller anteckning.

Redigera sedan länken genom att ändra länkåtgärden och ställa in målet som en webbadress:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Steg 4: Spara dokumentet med den uppdaterade länken

Spara dokumentet med den uppdaterade länken med hjälp av`Save` metod:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Steg 5: Visar resultatet

Visa ett meddelande som anger att mållänken har konfigurerats och ange platsen för den sparade filen:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Exempel på källkod för Set Destination Link med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda PDF-filen
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Få den första länkanteckningen från första sidan i dokumentet
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Ändringslänk: ändra länkåtgärd och ange mål som webbadress
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Spara dokumentet med uppdaterad länk
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

Grattis! Du vet nu hur du ställer in en destinationslänk i en PDF-fil med Aspose.PDF för .NET. Använd denna kunskap för att anpassa länkar i dina PDF-dokument och skapa interaktiva upplevelser för användarna.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.