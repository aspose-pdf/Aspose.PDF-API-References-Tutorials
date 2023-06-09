---
title: Ange sida vid visning
linktitle: Ange sida vid visning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du anger en sida när du visar en PDF med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-links-and-actions/specify-page-when-viewing/
---

Lär dig hur du anger en sida när du visar en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

## Steg 1: Sätta upp miljön

Se till att du har konfigurerat din utvecklingsmiljö med ett C#-projekt och lämpliga Aspose.PDF-referenser.

## Steg 2: Laddar PDF-filen

Ställ in katalogsökvägen för dina dokument och ladda upp PDF-filen med följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda PDF-filen
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Steg 3: Ange målsidan

Hämta målsidesinstansen med följande kod:

```csharp
Page page2 = doc.Pages[2];
```

 Du kan justera indexet`[2]` för att välja önskad sida.

## Steg 4: Konfigurera zoominställningen

Skapa en variabel för att ställa in målsidans zoomfaktor:

```csharp
double zoom = 1;
```

Du kan justera zoomvärdet efter dina behov.

## Steg 5: Skapa navigeringsåtgärden

Skapa en instans av navigeringsåtgärden med den angivna målsidan:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Steg 6: Ange destination

Ställ in destinationen för att gå till målsidan med hjälp av koordinater och zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Steg 7: Konfigurera åtgärden Dokumentöppning

Ställ in handlingen för att öppna dokumentet med den skapade navigeringsåtgärden:

```csharp
doc. OpenAction = action;
```

## Steg 8: Spara det uppdaterade dokumentet

 Spara det uppdaterade dokumentet med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Exempel på källkod för Specificera sida vid visning med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda PDF-filen
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Hämta instansen av dokumentets andra sida
Page page2 = doc.Pages[2];
// Skapa variabeln för att ställa in zoomfaktorn för målsidan
double zoom = 1;
// Skapa GoToAction-instans
GoToAction action = new GoToAction(doc.Pages[2]);
// Gå till 2 sida
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Ställ in handlingen för att öppna dokumentet
doc.OpenAction = action;
// Spara uppdaterat dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

## Slutsats

Grattis! Du vet nu hur du anger en sida när du visar en PDF med Aspose.PDF för .NET. Använd denna kunskap för att anpassa användarens visningsupplevelse i dina PDF-dokument.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.