---
title: Ta bort Open Action
linktitle: Ta bort Open Action
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort den öppna åtgärden från en PDF med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-links-and-actions/remove-open-action/
---

Lär dig hur du tar bort den öppna åtgärden från en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

## Steg 1: Sätta upp miljön

Se till att du har konfigurerat din utvecklingsmiljö med ett C#-projekt och lämpliga Aspose.PDF-referenser.

## Steg 2: Laddar PDF-filen

Ställ in katalogsökvägen för dina dokument och ladda upp PDF-filen med följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Steg 3: Ta bort den öppna åtgärden

 Ta bort den öppna åtgärden från dokumentet genom att ställa in`OpenAction` egenskap att null:

```csharp
document. OpenAction = null;
```

## Steg 4: Spara det uppdaterade dokumentet

 Spara det uppdaterade dokumentet med hjälp av`Save` metod:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Steg 5: Visar resultatet

Visa ett meddelande som anger att den öppna åtgärden har tagits bort och ange platsen för den sparade filen:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Exempel på källkod för Remove Open Action med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Ta bort åtgärd för att öppna dokument
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Spara uppdaterat dokument
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Slutsats

Grattis! Nu vet du hur du tar bort den öppna åtgärden från en PDF med Aspose.PDF för .NET. Använd denna kunskap för att anpassa egenskaperna och beteendet hos PDF-filer i dina projekt.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.