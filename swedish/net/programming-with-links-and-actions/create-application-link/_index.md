---
title: Skapa applikationslänk
linktitle: Skapa applikationslänk
second_title: Aspose.PDF för .NET API Referens
description: Skapa enkelt programlänkar i dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-links-and-actions/create-application-link/
---

Genom att skapa en applikationslänk i ett PDF-dokument kan du skapa länkar till externa applikationer, till exempel körbara filer eller URL:er. Med Aspose.PDF för .NET kan du enkelt skapa applänkar genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill lägga till en applänk till. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet som vi vill lägga till en applikationslänk till med hjälp av följande kod:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Steg 4: Skapa applikationslänken

 I det här steget kommer vi att skapa applikationslänken med hjälp av`LinkAnnotation` anteckning. Vi kommer att ange koordinaterna och området för länken, samt åtgärden för att starta programmet. Här är motsvarande kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Steg 5: Spara den uppdaterade filen

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`document` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Exempel på källkod för Skapa applikationslänk med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Skapa länk
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Spara uppdaterat dokument
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att skapa applänkar med Aspose.PDF för .NET. Du kan använda den här koden för att lägga till länkar till externa applikationer i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om de avancerade funktionerna i interaktiva länkar.