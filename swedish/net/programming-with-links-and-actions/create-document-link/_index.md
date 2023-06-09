---
title: Skapa dokumentlänk
linktitle: Skapa dokumentlänk
second_title: Aspose.PDF för .NET API Referens
description: Skapa enkelt länkar till andra PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-links-and-actions/create-document-link/
---

Genom att länka till ett annat dokument i en PDF-fil kan du skapa klickbara länkar som omdirigerar användare till andra PDF-dokument. Med Aspose.PDF för .NET kan du enkelt skapa sådana länkar genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill lägga till en länk till ett annat dokument till. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet som vi vill lägga till länken till ett annat dokument med hjälp av följande kod:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Steg 4: Skapa länken till ett annat dokument

 I det här steget kommer vi att skapa länken till ett annat dokument med hjälp av`LinkAnnotation` anteckning. Vi kommer att specificera koordinaterna och området för länken, samt navigeringsåtgärden till ett externt dokument. Här är motsvarande kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Steg 5: Spara den uppdaterade filen

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`document` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Exempel på källkod för Skapa dokumentlänk med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Skapa länk
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Spara uppdaterat dokument
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att länka till andra dokument med Aspose.PDF för .NET. Du kan använda den här koden för att skapa klickbara länkar i dina PDF-filer och omdirigera användare till andra dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om de avancerade funktionerna i interaktiva länkar.