---
title: Ställ in mållänk
linktitle: Ställ in mållänk
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in en mållänk i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-links-and-actions/set-target-link/
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
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Steg 3: Redigera mållänken

Få länkkommentaren att ändra med följande kod:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Du kan justera`[1]` index för att välja en specifik sida eller anteckning.

Uppdatera sedan destinationen utan att uppdatera filen:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Och om du också vill uppdatera filen:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Steg 4: Spara dokumentet med den uppdaterade länken

Spara dokumentet med den uppdaterade länken med hjälp av`Save` metod:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Steg 5: Visar resultatet

Visa ett meddelande som anger att mållänken har konfigurerats och ange platsen för den sparade filen:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Exempel på källkod för Set Target Link med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda PDF-filen
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Nästa rad uppdatera destination, uppdatera inte filen
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Nästa rad uppdateringsfil
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Spara dokumentet med uppdaterad länk
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

Grattis! Du vet nu hur du ställer in en mållänk i en PDF-fil med Aspose.PDF för .NET. Använd denna kunskap för att anpassa länkar i dina PDF-dokument och skapa interaktiva upplevelser för användarna.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.