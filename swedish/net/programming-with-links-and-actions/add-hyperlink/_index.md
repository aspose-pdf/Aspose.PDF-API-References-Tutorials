---
title: Lägg till hyperlänk
linktitle: Lägg till hyperlänk
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till interaktiva hyperlänkar i dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-links-and-actions/add-hyperlink/
---

Genom att lägga till hyperlänkar i ett PDF-dokument kan du skapa interaktiva hyperlänkar till andra sidor, webbplatser eller destinationer i dokumentet. Med Aspose.PDF för .NET kan du enkelt lägga till hyperlänkar genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill lägga till en hyperlänk till. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet som vi vill lägga till en hyperlänk till med hjälp av följande kod:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Steg 4: Skapa en länk

 I det här steget kommer vi att skapa en hyperlänk med hjälp av`LinkAnnotation` anteckning. Vi kommer att specificera kontaktuppgifter och område för länken, typen av länk och innehållet i länken. Här är motsvarande kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Steg 5: Lägg till ytterligare text

 Förutom hyperlänken kan vi också lägga till ytterligare text med hjälp av`FreeTextAnnotation` anteckning. Vi kommer att specificera koordinater, textens utseende och textinnehåll. Här är motsvarande kod:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Steg 6: Spara den uppdaterade filen

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`document` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Exempel på källkod för Add Hyperlink med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Skapa länk
Page page = document.Pages[1];
//Skapa länkanteckningsobjekt
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Skapa kantobjekt för LinkAnnotation
Border border = new Border(link);
// Ställ in gränsbreddsvärdet som 0
border.Width = 0;
// Ställ in gränsen för LinkAnnotation
link.Border = border;
// Ange länktypen som fjärr-URI
link.Action = new GoToURIAction("www.aspose.com");
// Lägg till länkkommentarer till anteckningssamlingen på första sidan i PDF-filen
page.Annotations.Add(link);
// Skapa fritextkommentarer
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Sträng som ska läggas till som fritext
textAnnotation.Contents = "Link to Aspose website";
// Ställ in gränsen för fritextkommentarer
textAnnotation.Border = border;
// Lägg till FreeText-kommentarer till anteckningssamlingen på första sidan i dokumentet
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Spara uppdaterat dokument
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att lägga till hyperlänkar med Aspose.PDF för .NET. Du kan använda den här koden för att skapa interaktiva länkar i dina PDF-dokument.