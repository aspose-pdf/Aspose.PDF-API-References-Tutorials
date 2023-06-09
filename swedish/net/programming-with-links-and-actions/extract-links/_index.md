---
title: Extrahera länkar
linktitle: Extrahera länkar
second_title: Aspose.PDF för .NET API Referens
description: Extrahera enkelt länkar från ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-links-and-actions/extract-links/
---

Genom att extrahera länkar från ett PDF-dokument kan du återställa alla hypertextlänkar som finns i dokumentet. Med Aspose.PDF för .NET kan du enkelt extrahera dessa länkar genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen från vilken du vill extrahera länkarna. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

 Vi kommer att öppna PDF-dokumentet med hjälp av`Document` klass. Här är motsvarande kod:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Steg 4: Extrahera länkar

 I det här steget kommer vi att extrahera länkarna som finns i PDF-dokumentet med hjälp av`AnnotationSelector` klass. Här är motsvarande kod:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Steg 5: Spara det uppdaterade dokumentet

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`document` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Exempel på källkod för extrahera länkar med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Extrahera åtgärder
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Spara uppdaterat dokument
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att extrahera länkar från ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här koden för att hämta alla hyperlänkar som finns i dokumentet.

Var noga med att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade länkextraktionsfunktioner.