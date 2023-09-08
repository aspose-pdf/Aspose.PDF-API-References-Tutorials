---
title: Ställ in mållänk i PDF-fil
linktitle: Ställ in mållänk i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in en mållänk i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-links-and-actions/set-target-link/
---
Lär dig hur du ställer in en mållänk i PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

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

### Vanliga frågor om ange mållänk i PDF-fil

#### F: Vad är en mållänk i en PDF-fil?

S: En mållänk i en PDF-fil är en klickbar länk som navigerar läsaren till en specifik destination inom samma dokument eller till en annan PDF-fil.

#### F: Varför skulle jag vilja ställa in en mållänk i en PDF-fil?

S: Genom att ställa in mållänkar kan du skapa en sömlös navigeringsupplevelse i ett PDF-dokument eller länka till specifika avsnitt eller sidor i andra PDF-filer.

#### F: Hur hjälper Aspose.PDF för .NET att sätta mållänkar?

S: Aspose.PDF för .NET tillhandahåller API:er för att manipulera olika aspekter av PDF-filer, inklusive att skapa och ändra länkar. Denna handledning visar hur man ställer in en mållänk med C#-kod.

#### F: Kan jag ställa in mållänkar för att navigera till specifika sidor i samma dokument?

S: Ja, Aspose.PDF för .NET låter dig ställa in mållänkar för att navigera till specifika sidor i samma dokument.

#### F: Kan jag ställa in mållänkar för att navigera till specifika sidor i en annan PDF-fil?

S: Ja, du kan ställa in mållänkar för att navigera till specifika sidor i en annan PDF-fil med Aspose.PDF för .NET.

#### F: Finns det några begränsningar för att ställa in mållänkar?

S: Mållänkar kan bara navigera inom samma dokument eller till specifika sidor i andra PDF-filer. De kan inte länka direkt till specifikt innehåll i andra dokument.

#### F: Hur kan jag anpassa utseendet på en mållänk?

S: Utseendet på en mållänk, såsom dess färg och stil, kan anpassas med egenskaperna som tillhandahålls av Aspose.PDF för .NET.

#### F: Kan jag ställa in flera mållänkar i samma PDF-dokument?

S: Ja, du kan ställa in flera mållänkar i samma PDF-dokument. Upprepa helt enkelt processen för varje länk du vill skapa.

#### F: Kan jag ställa in en mållänk med en specifik form eller text?

S: Ja, du kan bifoga en mållänk till specifika former eller text i PDF-dokumentet med lämpliga egenskaper och metoder som tillhandahålls av Aspose.PDF för .NET.

#### F: Hur kan jag testa om mållänken fungerar som avsett?

S: Efter att ha ställt in mållänken med den medföljande koden, öppna den modifierade PDF-filen och klicka på länken för att säkerställa att den navigerar till önskad destination.

#### F: Kan jag ställa in mållänkar i lösenordsskyddade PDF-filer?

S: Ja, du kan ställa in mållänkar i lösenordsskyddade PDF-filer så länge du tillhandahåller lämpliga referenser för att komma åt och ändra dokumentet.